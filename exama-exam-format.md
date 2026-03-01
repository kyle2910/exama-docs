# Exama Exam Package Specification

> **Audience:** AI coding agents. This document is the authoritative reference for generating, parsing, and validating Exama exam packages. Follow it exactly. Do not infer structure beyond what is defined here.

---

## 1. Package Overview

An Exama exam is a single `.zip` file with the following structure:

```
exam.zip
├── metadata.yaml       # required
├── content.yaml        # required
└── media/              # optional
    ├── image1.png
    ├── audio1.mp3
    └── video1.mp4
```

**Rules:**
- `metadata.yaml` and `content.yaml` are always required.
- `media/` is optional. If present, it must be flat (no subdirectories).
- All media references in content use relative paths: `media/filename.ext`.

---

## 2. metadata.yaml

```yaml
version: 1                        # required — integer, increment on breaking change
exam_id: "math-midterm-2026"      # required — unique string identifier
title: "Midterm Exam - Grade 11"  # required — display title

subject: "Mathematics"            # optional
grade: 11                         # optional — integer
duration_minutes: 90              # optional — integer
total_points: 10                  # optional — number
author: "Teacher Name"            # optional
created_at: "2026-03-01"          # optional — ISO 8601 date
language: "vi"                    # optional — BCP 47 language tag
```

**Required fields:** `version`, `exam_id`, `title`  
**All other fields:** optional

---

## 3. content.yaml

### 3.1 Root Structure

```yaml
version: 3          # required — integer
title: "Exam Title" # optional

blocks:
  - <block>
  - <block>
```

### 3.2 Block Tree Model

The exam is a recursive tree. Every node is a **block**. There are three block types:

| Type       | Has `children` | Has `question_type` |
|------------|----------------|----------------------|
| `section`  | optional       | ❌                   |
| `group`    | optional       | ❌                   |
| `question` | ❌ forbidden   | ✅ required          |

Sections and groups without `children` are valid — they can serve as pure informational blocks (instructions, passages, announcements).

### 3.3 Common Block Fields

```yaml
type: section | group | question   # required
id: string                         # required — unique across entire exam
title: string                      # optional
description: string                # optional — Markdown, rendered before content
content: string                    # optional — Markdown (supports LaTeX via $...$ and $$...$$)
media: []                          # optional — array of media file paths; see Section 8
points: number                     # optional — see Section 5 for resolution rules
config: {}                         # optional — type-specific settings
children: []                       # optional for section and group; forbidden for question
```

**Rendering order** (when fields are present):
1. `description`
2. `content`
3. `media`
4. `children`

---

## 4. Block Types

### 4.1 Section

Top-level divisions of the exam (e.g., Part 1 — Physics, Part 2 — Essay). May contain `children`, or exist as a pure informational block with no questions.

```yaml
- type: section
  id: part1
  title: "Part 1 — Multiple Choice"
  points: 5
  children:
    - <block>

# Informational section (no children required)
- type: section
  id: intro
  content: |
    Welcome to the exam. Read each question carefully before answering.
  media:
    - "media/instructions.png"
```

### 4.2 Group

Groups related questions that share context, instructions, or a shared reading passage. `children` is optional.

```yaml
- type: group
  id: g1
  title: "Question 1"
  description: |
    Read the passage below, then answer the questions.
  content: |
    *"To be or not to be, that is the question..."*
  media:
    - "media/passage_audio.mp3"
  points: 4
  config:
    scoring_mode: partial   # "partial" (default) | "all_or_nothing"
  children:
    - <question>
    - <question>
```

**`scoring_mode` behavior:**
- `partial` (default): each correct child earns its share of points independently.
- `all_or_nothing`: all children must be correct to receive any points; otherwise score = 0.

### 4.3 Question

A leaf node. Cannot have `children`.

```yaml
- type: question
  id: q1
  question_type: single_choice   # see Section 6
  points: 1
  content: |
    What is $2^3$?
  # solution and blanks fields depend on question_type — see Section 6
  config: {}
```

---

## 5. Scoring Rules

### 5.1 Points Resolution (evaluated top-down)

1. If a block defines `points`, use it.
2. If not defined, inherit from parent; divide remaining points equally among siblings without explicit points.
3. If no `points` exist anywhere in the ancestry, default = 1 point per question.

### 5.2 Group Scoring

- If `scoring_mode: all_or_nothing`, the group scores either full points or 0.
- If `scoring_mode: partial`, each child question scores independently.
- Children without explicit `points` share the group's remaining points equally.

---

## 6. Question Types

### Auto-Graded Types

---

#### `single_choice`

One correct answer from a list of options.

```yaml
- type: question
  id: q1
  question_type: single_choice
  content: "Which planet is closest to the Sun?"
  options:
    - key: A
      value: "Mercury"
    - key: B
      value: "Venus"
    - key: C
      value: "Earth"
  solution:
    correct: "A"   # must match an option key exactly
```

---

#### `multiple_choice`

One or more correct answers.

```yaml
- type: question
  id: q2
  question_type: multiple_choice
  content: "Select all prime numbers."
  options:
    - key: A
      value: "2"
    - key: B
      value: "3"
    - key: C
      value: "4"
  solution:
    correct: ["A", "B"]   # array of option keys
  config:
    scoring_mode: partial   # "partial" (default) | "all_or_nothing"
```

---

#### `true_false`

A single statement judged as true or false. For multiple statements, wrap in a `group`.

```yaml
- type: question
  id: q3
  question_type: true_false
  content: "The Earth revolves around the Sun."
  solution:
    correct: true   # boolean: true | false
```

**Multiple statements pattern:**

```yaml
- type: group
  id: g1
  title: "Mark each statement True or False."
  children:
    - type: question
      id: q3a
      question_type: true_false
      content: "The Earth revolves around the Sun."
      solution:
        correct: true
    - type: question
      id: q3b
      question_type: true_false
      content: "The Moon is a planet."
      solution:
        correct: false
```

---

#### `ordering`

Arrange items in the correct sequence.

```yaml
- type: question
  id: q4
  question_type: ordering
  content: "Order the steps of the scientific method."
  items:
    - id: i1
      value: "Form a hypothesis"
    - id: i2
      value: "Observe"
    - id: i3
      value: "Experiment"
    - id: i4
      value: "Conclude"
  solution:
    correct_order: ["i2", "i1", "i3", "i4"]   # array of item ids in correct order
  config:
    scoring_mode: partial   # "partial" (default) | "all_or_nothing"
```

---

#### `matching`

Match items from a left column to items in a right column.

```yaml
- type: question
  id: q5
  question_type: matching
  content: "Match each country to its capital."
  left:
    - id: l1
      value: "France"
    - id: l2
      value: "Japan"
  right:
    - id: r1
      value: "Paris"
    - id: r2
      value: "Tokyo"
    - id: r3
      value: "Berlin"   # distractor — more right items than left is allowed
  solution:
    matches:
      l1: r1
      l2: r2
  config:
    scoring_mode: partial   # "partial" (default) | "all_or_nothing"
```

---

#### `fill_blank`

A single blank in the question. The blank is implied; no placeholder needed in `content`.

```yaml
- type: question
  id: q6
  question_type: fill_blank
  content: "The capital of France is ___."
  solution:
    answers:
      - value: "Paris"
        case_sensitive: false   # default: false
        trim: true              # default: true
      - value: "paris"          # alternative accepted answer
        case_sensitive: false
        trim: true
```

---

#### `fill_blank_multi`

Multiple blanks in a single question. Use `{{blank_id}}` as placeholders in `content`.

```yaml
- type: question
  id: q7
  question_type: fill_blank_multi
  content: "{{b1}} is the largest planet and {{b2}} is the smallest."
  blanks:
    b1:
      answers:
        - value: "Jupiter"
          case_sensitive: false
          trim: true
    b2:
      answers:
        - value: "Mercury"
          case_sensitive: false
          trim: true
```

---

#### `fill_blank_dropdown`

Multiple blanks where each blank provides a dropdown of choices instead of free text.

```yaml
- type: question
  id: q8
  question_type: fill_blank_dropdown
  content: "Water boils at {{b1}} degrees Celsius at {{b2}} pressure."
  blanks:
    b1:
      options: ["50", "100", "150"]
      correct: "100"
    b2:
      options: ["low", "standard", "high"]
      correct: "standard"
```

---

#### `cloze`

A passage with multiple inline blanks. Structurally identical to `fill_blank_multi`, but semantically represents a fill-in-the-gaps reading exercise. An optional shared `word_pool` may include distractors.

```yaml
- type: question
  id: q9
  question_type: cloze
  content: |
    She {{b1}} to school yesterday because it {{b2}} raining.
  blanks:
    b1:
      answers:
        - value: "went"
          case_sensitive: false
          trim: true
    b2:
      answers:
        - value: "was"
          case_sensitive: false
          trim: true
  config:
    word_pool:
      - went
      - was
      - because
      - rained   # distractor
```

**Note:** `word_pool` is optional. When present, it is used by the renderer to display a shared bank of words for the student to choose from. Grading is still resolved per blank via `blanks`.

---

### Manual / AI-Assisted Types

---

#### `short_answer`

Free-text short response. Primarily manual-graded. AI assistance is advisory only.

```yaml
- type: question
  id: q10
  question_type: short_answer
  content: "Explain Newton's first law in your own words."
  config:
    ai_assist: true             # optional — default: false
    expected_keywords:          # optional — heuristic hints for AI grading, not authoritative
      - "inertia"
      - "rest"
      - "motion"
```

---

#### `essay`

Extended free-text response. Graded manually; AI may suggest a score but does not determine it.

```yaml
- type: question
  id: q11
  question_type: essay
  content: "Discuss the causes and effects of World War I."
  config:
    rubric: |
      - **Causes (4 pts):** Identifies at least 3 root causes (alliance systems, nationalism, assassination).
      - **Effects (4 pts):** Covers political, economic, and social consequences.
      - **Clarity (2 pts):** Logical structure, coherent argument.
```

**Note:** `rubric` is a Markdown string. Exama does not parse rubric structure — it is display-only. AI scoring based on the rubric is advisory and non-authoritative.

---

## 7. Blank Placeholder Convention

For `fill_blank_multi` and `cloze`, blanks in `content` must use the format:

```
{{blank_id}}
```

The `blank_id` inside the braces must exactly match a key in the `blanks` map. No other placeholder format is valid.

**Valid:**
```
The {{b1}} jumped over the {{b2}}.
```

**Invalid:**
```
The [b1] jumped over the __b2__.   ❌
The {b1} jumped over the {b2}.    ❌
```

---

## 8. Content, Media, and Rendering

### 8.1 Renderable Fields

Every node in the tree — blocks (`section`, `group`, `question`) and sub-nodes (`option`, `item`, `left`, `right`, `blank`) — MAY carry any of these fields:

| Field         | Type     | Description                                      |
|---------------|----------|--------------------------------------------------|
| `description` | string   | Markdown rendered first. Use for framing/instructions. |
| `content`     | string   | Markdown rendered after `description`.           |
| `media`       | string[] | Array of media file paths, rendered after `content`. |

All three fields are optional everywhere. Both `description` and `content` support Markdown and LaTeX (display only — see Section 8.3).

### 8.2 Media Field

`media` is a flat array of relative file path strings. No metadata, no type, no alt, no caption.

```yaml
media:
  - "media/diagram.png"
  - "media/audio_prompt.mp3"
  - "media/explainer.mp4"
```

**Rules:**
- Each entry is a string: a path relative to the zip root.
- All files must reside directly inside `media/` — no subdirectories.
- File type is inferred from extension by the renderer.
- Rendering order follows array order.
- Do not add any extra metadata fields (`type`, `alt`, `caption`, etc.) — they are not part of this spec.

### 8.3 Rendering Order

For any node, render in this fixed order (skip absent fields):

```
1. description   (if present)
2. content       (if present)
3. media         (if present, in array order)
4. children      (if present)
```

### 8.4 Media on Sub-Nodes

`description`, `content`, and `media` are valid on sub-nodes too:

```yaml
# option with media
options:
  - key: A
    content: "Option A text"
    media:
      - "media/option_a_diagram.png"

# item with media
items:
  - id: i1
    content: "Step one"
    media:
      - "media/step1.png"

# left/right with media (matching)
left:
  - id: l1
    content: "France"
    media:
      - "media/france_flag.png"

# blank with media
blanks:
  b1:
    description: "Hint: think about boiling point."
    answers:
      - value: "100"
```

### 8.5 LaTeX Policy

| Feature                              | Status       |
|--------------------------------------|--------------|
| LaTeX display (`$...$`, `$$...$$`)  | ✅ Supported |
| Math input field                     | ❌ Not supported |
| Symbolic grading                     | ❌ Not supported |
| Algebraic equivalence                | ❌ Not supported |
| Exact string grading                 | ✅ Supported |

**Rules AI coders must follow:**
- LaTeX in any `content` or `description` field is for visual rendering only. It has zero impact on grading logic.
- Do not implement any symbolic comparison, normalization, or equivalence checking.
- There is no CAS engine. Do not assume one exists or will be provided.

### 8.6 Auto-Grading Math Answers

If a math answer must be auto-graded, use `fill_blank`, `fill_blank_multi`, or `fill_blank_dropdown` with exact string matching.

Grading compares the student's raw string input against `answers[].value` after applying `trim` and `case_sensitive`. No algebraic transformation occurs.

**Critical:** `"1/2"` and `"0.5"` are treated as different answers. To accept both, list both explicitly.

```yaml
- type: question
  question_type: fill_blank_multi
  content: |
    Solve: $2x = 4$. Then $x = {{b1}}$.
  blanks:
    b1:
      answers:
        - value: "2"
          case_sensitive: false
          trim: true
        - value: "2.0"   # explicitly add all acceptable forms
          case_sensitive: false
          trim: true
```

---

## 9. Validation Rules

A valid Exama package must satisfy all of the following:

- `metadata.yaml` exists and contains `version`, `exam_id`, and `title`.
- `content.yaml` exists and contains `version` and `blocks`.
- All `id` values are unique across the entire exam (across all blocks at all depths).
- `section` and `group` blocks must not have `children` set to an empty array — omit the field entirely if there are no children.
- `question` blocks must not have `children`.
- `question` blocks must have a valid `question_type` from the supported list.
- Every entry in any `media` array must be a string matching `media/<filename>.<ext>` — no subdirectory separators, no absolute paths.
- All files referenced in `media` arrays must exist inside the `media/` folder in the zip.
- No circular nesting (a block cannot be its own ancestor).
- Blank placeholders in `fill_blank_multi` and `cloze` must have a matching key in `blanks`.
- Option keys in `single_choice` and `multiple_choice` `solution` must match defined option keys.

---

## 10. Supported Question Types — Reference Table

| question_type         | Auto-graded | Key fields                               |
|-----------------------|-------------|------------------------------------------|
| `single_choice`       | ✅          | `options`, `solution.correct` (string)   |
| `multiple_choice`     | ✅          | `options`, `solution.correct` (array)    |
| `true_false`          | ✅          | `solution.correct` (boolean)             |
| `ordering`            | ✅          | `items`, `solution.correct_order`        |
| `matching`            | ✅          | `left`, `right`, `solution.matches`      |
| `fill_blank`          | ✅          | `solution.answers[]`                     |
| `fill_blank_multi`    | ✅          | `blanks.<id>.answers[]`                  |
| `fill_blank_dropdown` | ✅          | `blanks.<id>.options`, `.correct`        |
| `cloze`               | ✅          | `blanks.<id>.answers[]`, `config.word_pool` (optional) |
| `short_answer`        | ❌ manual   | `config.expected_keywords` (optional)    |
| `essay`               | ❌ manual   | `config.rubric` (optional Markdown)      |

---

## 11. Versioning

Both `metadata.yaml` and `content.yaml` include a `version` integer. Increment `version` on any breaking structural change. Non-breaking additions (new optional fields) do not require a version bump.

Current versions: `metadata.yaml` → `1`, `content.yaml` → `3`.

---

## 12. Reserved for Future Versions

The following types are not yet implemented and must not be generated:

- `file_upload`
- `code_execution`
- `interactive_graph`
- Randomized question pools
- Adaptive scoring
- Symbolic math expression evaluation
