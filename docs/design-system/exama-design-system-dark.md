# Exama Design System — Dark Mode

**Version 1.0** · Online Examination Platform · Dark Mode Only

---

## Table of Contents

1. [Overview & Philosophy](#1-overview--philosophy)
2. [Design Principles](#2-design-principles)
3. [Foundations](#3-foundations)
   - 3.1 [Color](#31-color)
   - 3.2 [Typography](#32-typography)
   - 3.3 [Spacing](#33-spacing)
   - 3.4 [Border Radius](#34-border-radius)
   - 3.5 [Shadows & Elevation](#35-shadows--elevation)
   - 3.6 [Iconography](#36-iconography)
4. [Components](#4-components)
   - 4.1 [Buttons](#41-buttons)
   - 4.2 [Form Controls](#42-form-controls)
   - 4.3 [Badges & Tags](#43-badges--tags)
   - 4.4 [Cards](#44-cards)
   - 4.5 [Alerts & Callouts](#45-alerts--callouts)
   - 4.6 [Progress Indicators](#46-progress-indicators)
   - 4.7 [Tooltips](#47-tooltips)
   - 4.8 [Modals & Dialogs](#48-modals--dialogs)
   - 4.9 [Tables](#49-tables)
   - 4.10 [Navigation — Breadcrumb](#410-navigation--breadcrumb)
   - 4.11 [Navigation — Pagination](#411-navigation--pagination)
   - 4.12 [Navigation — Tabs](#412-navigation--tabs)
   - 4.13 [Empty States](#413-empty-states)
5. [Patterns](#5-patterns)
   - 5.1 [Sidebar Layout](#51-sidebar-layout)
   - 5.2 [Dashboard Header](#52-dashboard-header)
   - 5.3 [Data Filters](#53-data-filters)
6. [Exam UI](#6-exam-ui)
   - 6.1 [Exam Topbar](#61-exam-topbar)
   - 6.2 [Question Map — Desktop (Left Panel)](#62-question-map--desktop-left-panel)
   - 6.3 [Question Panel](#63-question-panel)
   - 6.4 [Answer Options](#64-answer-options)
   - 6.5 [Timer](#65-timer)
   - 6.6 [Result Screen](#66-result-screen)
   - 6.7 [Review Mode](#67-review-mode)
   - 6.8 [Display Mode: Paged vs Continuous Scroll](#68-display-mode-paged-vs-continuous-scroll)
7. [Mobile Design System](#7-mobile-design-system)
   - 7.1 [Breakpoints & Responsive Strategy](#71-breakpoints--responsive-strategy)
   - 7.2 [Mobile Typography](#72-mobile-typography)
   - 7.3 [Mobile Spacing & Touch Targets](#73-mobile-spacing--touch-targets)
   - 7.4 [Mobile Navigation — Bottom Tab Bar](#74-mobile-navigation--bottom-tab-bar)
   - 7.5 [Mobile Navigation — Hamburger Drawer](#75-mobile-navigation--hamburger-drawer)
   - 7.6 [Mobile Cards & Lists](#76-mobile-cards--lists)
   - 7.7 [Mobile Forms](#77-mobile-forms)
   - 7.8 [Mobile Tables → List View](#78-mobile-tables--list-view)
   - 7.9 [Mobile Modals → Bottom Sheet](#79-mobile-modals--bottom-sheet)
   - 7.10 [Mobile Exam UI — Topbar](#710-mobile-exam-ui--topbar)
   - 7.11 [Mobile Exam UI — Question Map Drawer](#711-mobile-exam-ui--question-map-drawer)
   - 7.12 [Mobile Exam UI — Question Panel](#712-mobile-exam-ui--question-panel)
   - 7.13 [Mobile Exam UI — Continuous Scroll Mode](#713-mobile-exam-ui--continuous-scroll-mode)
   - 7.14 [Mobile Exam UI — Result Screen](#714-mobile-exam-ui--result-screen)
8. [Motion & Interaction](#8-motion--interaction)
9. [Accessibility](#9-accessibility)
10. [Writing Style](#10-writing-style)
11. [Token Reference](#11-token-reference)

---

## 1. Overview & Philosophy

Exama là nền tảng thi trực tuyến và LMS (Learning Management System) dành cho giáo viên và học sinh. Hệ thống thiết kế tồn tại để đảm bảo mọi tương tác đều **rõ ràng, bình tĩnh và đáng tin cậy** — cho phép người dùng tập trung hoàn toàn vào nhiệm vụ trước mắt thay vì giao diện.

### The Dark Slate Metaphor

Phiên bản dark mode của Exama thay thế ẩn dụ "tờ giấy trắng" bằng ẩn dụ **bảng đen học đường** — nền sẫm màu, chữ sáng, tương phản rõ ràng, gợi lên không gian học tập nghiêm túc trong môi trường ánh sáng thấp. Nguyên tắc dịch chuyển:

- **Nền sẫm ấm** thay vì xám lạnh hay đen thuần túy — giữ lại nhiệt độ màu của hệ thống gốc.
- **Chữ off-white có độ ấm** thay vì trắng tuyệt đối — tránh mỏi mắt trên nền tối.
- **Accent sáng hơn** để đảm bảo tương phản và dễ nhận biết trên nền tối.
- **Không có glassmorphism**, không gradient nặng, không độ trong suốt — giao diện đục và dễ đọc như phấn viết trên bảng.
- **Elevation thể hiện qua độ sáng** của bề mặt thay vì đổ bóng (bóng gần như vô hình trên nền tối).

### Single Mode

Exama Dark Mode là **dark mode only**. Đây là quyết định có chủ ý. Phiên bản này phục vụ các bối cảnh thi trong môi trường ánh sáng thấp (phòng tối, thi ban đêm, học muộn) hoặc theo sở thích cá nhân giảm ánh sáng màn hình. Duy trì một chế độ visual duy nhất đảm bảo tính nhất quán màu sắc tuyệt đối, giảm phức tạp triển khai, và giữ nguyên ẩn dụ "bảng đen" xuyên suốt.

---

## 2. Design Principles

### 1. Clarity over Cleverness
Mọi element phải truyền đạt mục đích ngay lập tức. Nhãn phải rõ ràng. Trạng thái phải không mơ hồ. Chúng ta không bao giờ hy sinh khả năng đọc vì thẩm mỹ — đặc biệt quan trọng trên nền tối nơi độ tương phản dễ bị hy sinh cho cái đẹp.

### 2. Calm by Default
Giao diện không cố gắng gây ấn tượng. Nó là một công cụ. Tone màu trung tính, độ sâu đổ bóng khiêm tốn, và chuyển động có kiểm soát ngăn UI cạnh tranh sự chú ý của người dùng trong những khoảnh khắc căng thẳng cao như khi đang thi.

### 3. Structured Hierarchy
Thông tin được phân lớp rõ ràng: nền trang → bề mặt card → element tương tác → trạng thái focused/active. Trên dark mode, hierarchy được thể hiện qua **độ sáng của bề mặt** (surface lightness) thay vì đổ bóng — bề mặt nằm cao hơn trong z-stack sẽ sáng hơn một chút.

### 4. Educational Context Respect
Typography dùng serif cho heading để truyền đạt sự nghiêm túc học thuật. Mật độ nội dung phù hợp — không quá thưa (có vẻ coi thường) và không quá dày đặc (choáng ngợp). Chúng ta đối xử với người dùng như những người lớn thông minh.

### 5. Reliability over Delight
Hệ thống này ưu tiên **tính dự đoán được** hơn bất ngờ. Trạng thái hover tinh tế. Chuyển đổi nhanh. Phản hồi tức thì và không mơ hồ. Sự tin tưởng được xây dựng qua tính nhất quán, không phải animation.

---

## 3. Foundations

### 3.1 Color

Palette được tổ chức thành bốn nhóm: **Slate** (bề mặt tối), **Glow** (chữ sáng), **Accent**, và **Semantic**.

#### Slate — Surface Colors

Dùng cho nền trang, bề mặt card, divider và nền input. Tone ấm nhẹ (hơi nâu-xám) được duy trì để tránh cảm giác lạnh lẽo của grey thuần.

| Token | Hex | Usage |
|---|---|---|
| `slate-900` | `#16140f` | Page background (body) — tối nhất |
| `slate-800` | `#1e1c16` | Sidebar background, primary card surface |
| `slate-700` | `#272419` | Secondary card surface, hover states, input background |
| `slate-600` | `#312e22` | Prominent borders, elevated panel background |
| `slate-500` | `#3d392c` | Dividers, border tích cực, active nav background |

Tone ấm (nâu-đen) trong tất cả giá trị slate là có chủ ý — nó giữ nguyên nhiệt độ màu của hệ thống gốc thay vì chuyển sang xám lạnh. Không bao giờ dùng `#000000` thuần.

#### Glow — Text & Foreground Colors

Dùng cho tất cả nội dung typography và iconography. Tên "Glow" phản ánh bản chất của chữ sáng trên nền tối.

| Token | Hex | Usage |
|---|---|---|
| `glow-100` | `#2e2b22` | Rất subtle — shadow trên text, chi tiết decoration |
| `glow-200` | `#4a4638` | Disabled text, placeholder |
| `glow-300` | `#6b6555` | Secondary labels, helper text, captions |
| `glow-400` | `#9e9784` | Secondary body text, nav items resting |
| `glow-500` | `#cec7b5` | Primary body text |
| `glow-600` | `#e2ddd1` | Headings, strong content |
| `glow-700` | `#f2ede4` | Maximum contrast — display headings only |

Trắng thuần (`#fff`) không bao giờ được dùng. Tone sáng nhất `glow-700` giữ lại độ ấm.

#### Accent — Interactive Blue

Màu tương tác duy nhất trong hệ thống. Sáng hơn so với light mode để đảm bảo đủ tương phản trên nền tối.

| Token | Hex | Usage |
|---|---|---|
| `accent-900` | `#0d2035` | Answered question bubble background |
| `accent-800` | `#112b47` | Border on info alerts and selected tags |
| `accent-700` | `#1a4268` | Hover border on interactive cards |
| `accent-600` | `#2d6899` | Pressed state, darkest interactive accent |
| `accent-500` | `#4e84b4` | Primary button background, active state |
| `accent-400` | `#7aa3c8` | Outline button text, secondary accent, links |
| `accent-300` | `#adc5df` | Subtle accent tints, icon fills |

Accent đã được đảo chiều so với light mode — các số nhỏ hơn giờ là tối hơn (dùng cho nền), số lớn hơn là sáng hơn (dùng cho text/icon trên nền tối).

#### Semantic — Status Colors

Bốn màu semantic, mỗi màu có dải tint tối (900) đến sáng (300) phù hợp với nền dark.

| Role | Base Hex (text/icon) | Background Hex | Usage |
|---|---|---|---|
| **Success** | `#6ec46e` | `#0d200d` | Correct answers, submitted exams, passing scores |
| **Warning** | `#e8b84b` | `#221800` | Expiring timers, flagged questions, draft status |
| **Danger** | `#e07272` | `#220d0d` | Wrong answers, violations, failed submissions |
| **Info** | `#7aa3c8` | `#0d1e2d` | Informational callouts (shares accent palette) |

Mỗi màu semantic được dùng ở ba mức tonal:
- **Background tint** — nền alert/callout (rất tối, bão hòa thấp)
- **Border tint** — viền alert hoặc tag (trung bình)
- **Base** — icon, text hoặc fill thanh tiến trình (sáng nhất, đủ tương phản trên nền tối)

Màu semantic **không bao giờ dùng cho mục đích trang trí**, chỉ để truyền đạt trạng thái.

#### Color Contrast & Accessibility

- Tất cả body text (`glow-500` trên `slate-900`) đạt tỉ lệ tương phản tối thiểu **8.2:1** (WCAG AAA).
- Primary button (white `glow-700` trên `accent-500`) đạt **4.8:1** (WCAG AA).
- Semantic badge text (`danger` base trên `danger` background) đạt tối thiểu **5.0:1**.

---

### 3.2 Typography

Hệ thống type dùng hai typeface: một serif cho authority và hierarchy, một sans-serif cho khả năng đọc ở kích thước nhỏ. **Hoàn toàn giống light mode** — typography không thay đổi giữa hai chế độ, chỉ màu sắc thay đổi.

#### Typefaces

| Face | Family | Role |
|---|---|---|
| **Display & Headings** | Noto Serif | Serif — academic, authoritative, traditional |
| **Body & UI** | DM Sans | Sans-serif — geometric, neutral, functional |

**Noto Serif** được chọn vì duy trì legibility ở kích thước heading nhỏ hơn trong khi vẫn thể hiện sự đáng tin cậy học thuật. Các letterform của nó render sạch trên màn hình và hỗ trợ đầy đủ tiếng Việt.

**DM Sans** được chọn vì x-height rộng rãi, counter mở và tính cách gần như vô hình — lý tưởng cho đọc dài trong khi thi và cho UI label cần lùi vào nền.

#### Type Scale

| Name | Font | Size | Weight | Line Height | Usage |
|---|---|---|---|---|---|
| Display | Noto Serif | 48px / 3rem | 700 | 1.15 | Hero titles, landing |
| H1 | Noto Serif | 30px / 1.875rem | 700 | 1.25 | Page titles |
| H2 | Noto Serif | 24px / 1.5rem | 700 | 1.3 | Section headings |
| H3 | Noto Serif | 20px / 1.25rem | 700 | 1.4 | Card/panel headings |
| H4 | DM Sans | 16px / 1rem | 600 | 1.4 | Subheadings, group labels |
| Body Large | DM Sans | 16px / 1rem | 400 | 1.6 | Primary body content |
| Body | DM Sans | 14px / 0.875rem | 400 | 1.6 | Default body, descriptions |
| Body Small | DM Sans | 13px / 0.8125rem | 400 | 1.5 | Helper text, captions |
| Label | DM Sans | 11px / 0.6875rem | 600 | 1 | UI labels, all-caps only |
| Mono | System Mono | 14px / 0.875rem | 400 | 1 | Timer display, codes |

#### Label Convention

Labels (table headers, section identifiers, metadata) dùng **DM Sans 11px, font-weight 600, letter-spacing 0.07em, uppercase**. Tạo sự tách biệt visual với nội dung mà không cần màu khác hay size khác.

#### Question Text

Exam question body text dùng **Noto Serif at 18px, glow-700, line-height 1.7**. Mặt serif báo hiệu "đây là nội dung cần đọc cẩn thận." Line-height rộng rãi giảm lỗi theo dõi mắt trên các câu hỏi toán học hoặc khoa học dày đặc.

---

### 3.3 Spacing

Scale spacing dựa trên **đơn vị cơ sở 4px**. Tất cả giá trị padding, margin và gap của component đều là bội số của 4. **Hoàn toàn giống light mode.**

| Token | Value | Common Usage |
|---|---|---|
| `space-1` | 4px | Icon-to-label gap, tight inline spacing |
| `space-2` | 8px | Input padding vertical, compact component gaps |
| `space-3` | 12px | Badge padding, small component internal padding |
| `space-4` | 16px | Card padding (compact), section gutters |
| `space-5` | 20px | Default component padding |
| `space-6` | 24px | Card padding (standard), section spacing |
| `space-8` | 32px | Large section separation |
| `space-10` | 40px | Page-level vertical rhythm |
| `space-12` | 48px | Major section breaks |
| `space-16` | 64px | Page top/bottom padding |

**Grid:** The main content grid uses a 12-column system with a `24px` gutter and `24px` column padding. The max content width is `1280px` (`max-w-7xl`).

---

### 3.4 Border Radius

Giá trị border radius hoàn toàn giống light mode — không thay đổi giữa hai chế độ.

| Token | Value | Usage |
|---|---|---|
| `radius-sm` | 4px | Badges, tags, small chips, table header cells |
| `radius-base` | 6px | Inputs, selects, buttons, answer options |
| `radius-md` | 8px | Cards, panels, modals |
| `radius-lg` | 12px | Large cards, dialogs |
| `radius-xl` | 16px | Feature panels, illustration frames |
| `radius-full` | 9999px | Avatars, pill buttons, circular icon buttons |

`radius-base` (6px) là giá trị được dùng nhiều nhất. Nó cung cấp đủ độ mềm mại để cảm giác thân thiện mà không trông như một consumer app.

---

### 3.5 Shadows & Elevation

Trên dark mode, đổ bóng gần như vô hình vì nền đã tối. **Elevation được thể hiện chủ yếu qua độ sáng của bề mặt (surface lightness)** — bề mặt cao hơn trong z-stack dùng token `slate` sáng hơn. Bóng nhẹ được dùng để hỗ trợ thêm tính tách biệt khi cần.

| Token | CSS Value | Surface Token | Usage |
|---|---|---|---|
| `shadow-flat` | none + `border: 1px solid slate-600` | `slate-800` | Table rows, inactive elements |
| `shadow-dark` | `0 1px 3px rgba(0,0,0,0.30)` | `slate-800` | Default card elevation |
| `shadow-dark-md` | `0 3px 8px rgba(0,0,0,0.40)` | `slate-700` | Hover card state, dropdowns |
| `shadow-dark-lg` | `0 8px 20px rgba(0,0,0,0.50)` | `slate-600` | Modals, floating panels |
| `shadow-inset` | `inset 0 1px 3px rgba(0,0,0,0.30)` | — | Input fields, inset elements |

**Elevation Rule:** Mỗi layer z-stack dùng token slate sáng hơn một bậc. Ví dụ: nền trang dùng `slate-900`, card dùng `slate-800`, modal dùng `slate-700`. Viền (`slate-600`) vẫn cần thiết để xác định hình dạng element — không bao giờ dùng shadow một mình.

---

### 3.6 Iconography

Icons được lấy từ **Heroicons (outline)**, 24px viewBox, render ở 16px hoặc 20px tùy context. Line weight là `stroke-width: 1.5` cho UI icons và `stroke-width: 2` cho status icons.

**Quy tắc màu (dark mode):**
- Navigation icons: `glow-400` (resting), `accent-400` (active)
- Action icons trong button: kế thừa từ màu text button
- Status icons: dùng màu semantic tương ứng (base sáng, e.g. `#6ec46e`, `#e07272`)
- Decorative/empty-state icons: `glow-300` hoặc `glow-400`

Icons **không bao giờ dùng một mình** mà không có accessible label (visible text hoặc ARIA label).

---

## 4. Components

### 4.1 Buttons

Buttons là trigger action chính. Hệ thống định nghĩa sáu variant, bốn size và bốn trạng thái tương tác.

#### Variants

| Variant | Background | Text | Border | Usage |
|---|---|---|---|---|
| **Primary** | `accent-500` | `glow-700` | None | Main CTA — submit exam, create exam, save |
| **Secondary** | `slate-700` | `glow-500` | `slate-500` | Supporting actions — cancel, back, export |
| **Outline** | Transparent | `accent-400` | `accent-500` | Alternate primary action in a secondary position |
| **Ghost** | Transparent | `glow-500` | None | Low-priority actions in content areas |
| **Success** | `#0d200d` | `#6ec46e` | `#1a4a1a` | Confirming correct state, approve |
| **Danger** | `#220d0d` | `#e07272` | `#4a1a1a` | Destructive actions — delete, disqualify |

#### Sizes

| Size | Padding | Font size | Usage |
|---|---|---|---|
| `xs` | `10px 10px` | 12px | Inline within table cells, tight contexts |
| `sm` | `6px 12px` | 12px | Sidebar actions, secondary toolbar |
| `md` (default) | `9px 16px` | 14px | Default for all standalone buttons |
| `lg` | `10px 20px` | 16px | Primary CTA on landing/hero sections |

#### States

- **Resting:** Định nghĩa bởi variant ở trên.
- **Hover:** Background sáng hơn một bậc token (e.g., `accent-500` → `accent-400`). Không có scale transform.
- **Active/Pressed:** Background sáng hơn hai bậc. `box-shadow: inset 0 1px 2px rgba(0,0,0,0.20)`.
- **Disabled:** `opacity: 0.4`, `cursor: not-allowed`. Không thay đổi màu.
- **Loading:** Spinner icon (16px, `animate-spin`) đặt trước, text button giữ nguyên, button bị disabled. Spinner kế thừa màu text button.

#### Icon Buttons

Square icon-only button dùng equal padding để tạo hình vuông hoàn hảo (`w-8 h-8` / `w-9 h-9`). Phải luôn có thuộc tính `title` và ARIA label. Theo cùng variant system như text button.

#### Button Groups

Khi hai hoặc nhiều button chia sẻ context (e.g., modal footer, question navigation), chúng được đặt trong một hàng `flex` với khoảng cách `gap-3` (12px). Action chính luôn ở **bên phải**. Action hủy phá (destructive) luôn ở **bên trái** hoặc tách biệt bằng khoảng cách bổ sung.

---

### 4.2 Form Controls

#### Text Input

```
border: 1px solid slate-500
border-radius: 6px
padding: 9px 13px
font: DM Sans 14px, glow-500
background: slate-700
```

**Focus state:** `border-color: accent-400`, `box-shadow: 0 0 0 3px rgba(78,132,180,0.20)`
**Error state:** `border-color: #e07272`, `box-shadow: 0 0 0 3px rgba(224,114,114,0.18)`
**Success state:** `border-color: #6ec46e`, optional checkmark icon bên phải
**Disabled state:** `background: slate-800`, `color: glow-300`, `cursor: not-allowed`

Error messages xuất hiện **bên dưới input** với màu `#e07272`, 12px, DM Sans. Không bao giờ bên trong input hoặc dưới dạng tooltip.

#### Textarea

Giống text input. `resize: vertical` được phép nhưng `resize: horizontal` bị vô hiệu hóa. Chiều cao tối thiểu: 3 hàng (~72px).

#### Select

Border/radius/padding giống text input. Mũi tên native `<select>` được giữ nguyên nhưng có thể thay bằng SVG chevron tùy chỉnh. `cursor: pointer` là bắt buộc.

#### Checkbox

Custom checkbox 16×16px với viền tròn 3px (`radius-sm`). Trạng thái checked dùng nền `accent-500` với SVG checkmark màu `glow-700`. Trạng thái indeterminate dùng thanh ngang trong `accent-400`.

```
Unchecked:  border: 1.5px solid glow-300, background: slate-700
Checked:    border: none, background: accent-500, checkmark: glow-700
Disabled:   background: slate-800, border: slate-500
```

#### Radio Button

Custom radio button hình tròn 16×16px. Trạng thái selected hiển thị chấm tròn 8px trong `accent-500`.

```
Unselected:  border: 1.5px solid glow-300, background: slate-700
Selected:    border: 1.5px solid accent-500, inner dot: accent-500
Disabled:    background: slate-800, border: slate-500
```

#### Search Input

Text input chuẩn với icon `search` (`glow-400`, 16px) được positioned tuyệt đối tại `left: 12px`. Input padding-left tăng lên 36px để tránh text bị chồng lên.

#### Form Label

Labels nằm **phía trên** control, không bao giờ bên trong (placeholder không phải label). Typography: DM Sans 14px, `font-weight: 500`, `glow-500`. Required fields thêm `*` màu `#e07272`.

Section labels (gộp các input liên quan) dùng Label convention: DM Sans 11px, 600 weight, uppercase, `letter-spacing: 0.07em`, `glow-300`.

---

### 4.3 Badges & Tags

#### Status Badges

Dùng độc quyền cho **machine states** — trạng thái kỳ thi, trạng thái nộp bài, phân loại điểm số. Không tương tác.

```
font: DM Sans 11px, font-weight: 600, uppercase, letter-spacing: 0.06em
padding: 2px 8px
border-radius: 4px
border: 1px solid (semantic border tint)
```

| Status | Background | Text | Border |
|---|---|---|---|
| Active / Open | `#0d200d` | `#6ec46e` | `#1a4a1a` |
| Upcoming | `#221800` | `#e8b84b` | `#4a3200` |
| Ended / Closed | `#220d0d` | `#e07272` | `#4a1a1a` |
| Draft | `slate-700` | `glow-400` | `slate-500` |
| Grading | `accent-900` | `accent-400` | `accent-800` |

Tiền tố chấm màu (`●`) có thể đứng trước nhãn cho các trạng thái "live" (Active, Grading) để phân biệt thêm.

#### Score Badges

Dùng để hiển thị điểm số dạng số thoáng qua. Spec visual giống status badge nhưng font size là 12px và không uppercase.

| Score Range | Background | Text |
|---|---|---|
| ≥ 8.0 | `#0d200d` | `#6ec46e` |
| 5.0 – 7.9 | `#221800` | `#e8b84b` |
| < 5.0 | `#220d0d` | `#e07272` |

#### Subject/Category Tags

Tags tương tác hoặc có thể lọc dùng để phân loại nội dung. Hỗ trợ icon xóa tùy chọn (`×`).

```
font: DM Sans 12px, font-weight: 500
padding: 3px 9px
border-radius: 4px
border: 1px solid (matching dark tint)
```

Tags dùng màu để phân biệt category môn học nhưng mapping category-to-color phải được áp dụng nhất quán xuyên suốt sản phẩm, dùng các tint tối phù hợp dark background.

---

### 4.4 Cards

Cards là container nội dung chính. Tất cả cards chia sẻ:

```
background: slate-800
border: 1px solid slate-600
border-radius: 8px
box-shadow: shadow-dark
```

#### Card Variants

**Default Card** — Container chuẩn cho data, form và nội dung nhóm.

**Hoverable Card** (`card-hover`) — Dùng khi card có thể click (e.g., danh sách kỳ thi). On hover: `border-color: accent-600`, `background: slate-700`, `box-shadow: shadow-dark-md`. Không có transform hoặc scale effect.

**Stat Card** — Hiển thị một KPI metric duy nhất. Cấu trúc: label (Label style, `glow-300`) → số lớn (Noto Serif, 36px, `glow-700`) → supporting text (12px, `glow-300`). Có thể có thanh tiến trình nhỏ bên dưới.

**Accent Border Card** — Thêm viền trái `3px solid accent-500` cho nội dung informational hoặc nổi bật (e.g., card "Note"). Thay thế viền 1px mặc định ở cạnh trái.

**Semantic Border Card** — Giống trên nhưng dùng viền màu semantic tương ứng (`#6ec46e`, `#e8b84b`, hoặc `#e07272`) cho cạnh trái để truyền đạt context trạng thái.

#### Card Anatomy

```
[Card]
  ├── [Header] (optional) — title, subtitle, action button
  ├── [Divider] — 1px, slate-600
  ├── [Body] — primary content
  └── [Footer] (optional) — metadata, action row
```

Card padding nội bộ là `p-5` (20px) cho compact cards hoặc `p-6` (24px) cho standard cards.

---

### 4.5 Alerts & Callouts

Alerts truyền đạt phản hồi cấp hệ thống. Chúng full-width trong container và không thể dismiss theo mặc định (biến thể dismissible phải được implement rõ ràng).

#### Structure

```
[Icon 16px] + [Message text 14px] + [optional action link]
padding: 16px
border-radius: 6px
border: 1px solid (semantic border tint)
background: (semantic background tint — rất tối)
```

#### Variants

| Variant | Background | Border | Icon color | Text color |
|---|---|---|---|---|
| Info | `#0d1e2d` | `accent-800` | `accent-400` | `accent-300` |
| Success | `#0d200d` | `#1a4a1a` | `#6ec46e` | `#8ed98e` |
| Warning | `#221800` | `#4a3200` | `#e8b84b` | `#f0cc72` |
| Danger | `#220d0d` | `#4a1a1a` | `#e07272` | `#ea9090` |

Alert messages dùng câu hoàn chỉnh với dấu chấm. Mô tả **tình huống** tiếp theo là **những gì người dùng nên làm**, khi áp dụng.

> ✅ "Bài thi của bạn đã được nộp thành công lúc 09:42."
> ✅ "Còn 5 phút. Xem lại các câu hỏi chưa trả lời."
> ❌ "Đã nộp" (quá ngắn gọn)
> ❌ "LỖI: nộp bài thất bại!!!" (tone báo động)

---

### 4.6 Progress Indicators

#### Linear Progress Bar

Dùng để hiển thị hoàn thành kỳ thi, số học sinh đã nộp, hoặc phần trăm điểm.

```
Track:  background: slate-600, border-radius: 99px, height: 6px hoặc 8px
Fill:   border-radius: 99px, height: 100%
```

Fill colors: `accent-500` (mặc định / tiến trình trung tính), `#6ec46e` (metric tích cực), `#e8b84b` (metric cần chú ý).

Progress bars luôn kèm theo một hàng label phía trên hiển thị giá trị hiện tại và tổng (e.g., "18 / 25 đã trả lời").

#### Circular / Spinner

Chỉ dùng trong trạng thái loading của button và async data loading. 16px, `stroke-width: 3`, `stroke-dasharray: 30 60`, với animation xoay 1s linear infinite. Màu kế thừa từ context.

**Hệ thống không dùng skeleton loader.** Trạng thái loading được xử lý bằng spinner trong button kích hoạt hoặc text "Đang tải..." tối giản trong content area.

---

### 4.7 Tooltips

Tooltips cung cấp context bổ sung khi hover. Chúng không quan trọng — nội dung thiết yếu phải hiển thị mặc định.

```
background: slate-600
color: glow-600
font: DM Sans 12px
padding: 4px 10px
border-radius: 4px
border: 1px solid slate-500
arrow: 5px triangle pointing down
position: above the trigger (bottom: calc(100% + 6px))
delay: 200ms appear, instant disappear
```

Tooltips xuất hiện trên icon `?` help, text bị cắt ngắn và icon-only button. Không chứa element tương tác (link, button). Chiều rộng tối đa: 240px với text wrapping.

---

### 4.8 Modals & Dialogs

Modals ngắt luồng hiện tại để yêu cầu quyết định hoặc hiển thị nội dung focused.

**Overlay:** `background: rgba(0, 0, 0, 0.60)` — tối hơn so với light mode để tạo đủ tương phản.

**Dialog card:**
```
background: slate-800
border: 1px solid slate-600
border-radius: 8px
box-shadow: shadow-dark-lg
max-width: 480px (confirmation), 640px (form), 800px (content)
padding: 24px
```

**Modal anatomy:**
```
[Header row]
  ├── Title (H3, Noto Serif, glow-700)
  └── Close button (top-right, Ghost icon button)
[Divider] — slate-600 (optional)
[Body] — description, form, or content
[Footer row] — right-aligned, Secondary + Primary button
```

**Usage rules:**
- Tối đa một modal mở tại một thời điểm. Không có nested modal.
- Tất cả modal phải có `aria-modal="true"` và focus-trap behavior.
- Đóng bằng: nút ✕, phím Escape, click overlay (trừ khi action là destructive — thì click overlay bị vô hiệu hóa).
- Destructive confirmation modal (xóa, kết thúc thi) phải yêu cầu click button rõ ràng. Không thể dismiss bằng cách click overlay.

---

### 4.9 Tables

Tables hiển thị data có cấu trúc — danh sách học sinh, kết quả thi, ngân hàng câu hỏi.

#### Header Row

```
background: slate-700
font: DM Sans 11px, weight 600, uppercase, letter-spacing: 0.07em
color: glow-400
padding: 10px 14px
border-bottom: 1px solid slate-600
```

#### Data Row

```
font: DM Sans 14px, glow-500
padding: 12px 14px
border-bottom: 1px solid slate-700
vertical-align: middle
```

Row hover state: `background: slate-700`. Tinh tế — đủ để thấy ranh giới hàng mà không gây mất tập trung.

Hàng cuối cùng không có bottom border (kết thúc visual).

#### Column Types

- **Identity column** (tên học sinh): Avatar (28px circle, initials, accent tint) + tên trong `glow-600 font-medium`.
- **Date/Time column:** `glow-400`, monospace nếu cần độ chính xác.
- **Score column:** Màu theo ngưỡng semantic — `#6ec46e` (≥ 8.0), `#e8b84b` (5.0–7.9), `#e07272` (< 5.0).
- **Status column:** Status badge.
- **Action column:** Text links trong `accent-400`, right-aligned, 14px. Không bao giờ icon-only trong table (accessibility).

#### Empty Table

Khi không có data, table body được thay thế bằng empty state component căn giữa trong một hàng kéo dài qua tất cả cột.

#### Sortable Columns

Sortable headers thêm icon chevron nhỏ (16px). Cột sort đang active: text `glow-600`, chevron đặc. Cột không active: text `glow-400`, chevron mờ.

---

### 4.10 Navigation — Breadcrumb

Breadcrumbs hiển thị vị trí trang hiện tại trong phân cấp ứng dụng.

```
font: DM Sans 14px
separator: chevron-right SVG, 14px, glow-400
ancestor links: accent-400, no underline mặc định, underline on hover
current page: glow-500, không phải link
```

Độ sâu tối đa: 4 cấp. Nếu điều hướng sâu hơn, các cấp trung gian bị cắt ngắn bằng `…`.

---

### 4.11 Navigation — Pagination

```
button size: 32px × 32px
border-radius: 6px
font: DM Sans 14px

Resting:   background transparent, glow-400
Active:    background accent-500, text glow-700
Hover:     background slate-700
Previous/Next: background slate-700, border slate-500
Ellipsis:  glow-300, không tương tác
```

Luôn hiển thị: Previous, trang đầu, neighborhood hiện tại (±1), trang cuối, Next. Ellipsis lấp đầy khoảng trống.

---

### 4.12 Navigation — Tabs

Tabs chuyển đổi giữa các view song song của cùng một context nội dung (không phải giữa các trang).

```
Tab strip: border-bottom: 1px solid slate-600 (full width)
Tab item:  padding 12px 20px, DM Sans 14px

Resting:  glow-400, border-bottom: 2px solid transparent
Active:   accent-400, font-weight 600, border-bottom: 2px solid accent-500
Hover:    glow-600
Disabled: glow-200, cursor not-allowed
```

Tab content area có `padding-top: 20px`. Số tab tối đa khuyến nghị: 6. Vượt quá 6, dùng Select dropdown.

---

### 4.13 Empty States

Empty states được hiển thị khi một data container không có item nào — tài khoản mới, kết quả lọc không khớp, hoặc data đã xóa.

#### Anatomy

```
[Icon container] — 48×48px, border-radius: 8px, slate-700 hoặc semantic background tint
    └── [Icon] — 24px, glow-300 hoặc semantic base color
[Heading] — Noto Serif, 18px, glow-600
[Description] — DM Sans 14px, glow-400, max-width 280px, centered
[CTA Button] (optional) — Primary hoặc Outline variant
```

Căn giữa trong container. Chiều cao container tối thiểu để empty state có không gian thở: 200px.

**Copy cho empty state nên:**
- Thân thiện, không xin lỗi ("Chưa có kỳ thi" không phải "Không tìm thấy dữ liệu")
- Hướng action khi một user action giải quyết được trạng thái
- Cụ thể với context ("Chưa có kỳ thi" không chỉ "Trống")

---

## 5. Patterns

### 5.1 Sidebar Layout

Shell ứng dụng chính cho teacher dashboard.

```
[Shell]
  ├── [Sidebar]   width: 208px, fixed, height: 100vh
  │     ├── [Branding area] — logo + product name, border-bottom: slate-600
  │     ├── [Navigation items]
  │     │     ├── Nav item — 40px height, 12px 16px padding, gap-2.5
  │     │     └── Active item — nav-active style (see below)
  │     └── [User profile row] — bottom, border-top: slate-600
  └── [Main content area] — flex-1, overflow-y-auto, padding: 20px–24px
```

**Background sidebar:** `slate-800`
**Background main content:** `slate-900`

**Active nav item style:**
```
background: slate-700
border-left: 3px solid accent-500
color: accent-400
font-weight: 600
```
Viền trái 3px là active indicator chính. Nó thay thế left padding, vì vậy căn chỉnh icon/text giữ nguyên nhất quán.

**Nav item structure:** `[Icon 16px] [Label 14px]` — icon luôn có để hỗ trợ scanning và nhận biết nhanh.

**User profile row:** Avatar (28px) + tên (12px, `glow-600`, truncated) + email (11px, `glow-300`, truncated). Overflow menu (⋮) cho phép truy cập logout và settings.

---

### 5.2 Dashboard Header

Mỗi trang trong teacher dashboard có header row nhất quán ở đầu main content area.

```
[Page Header]
  ├── [Left]
  │     ├── Breadcrumb (nếu độ sâu > 1)
  │     ├── Page title (H1, Noto Serif, glow-700)
  │     └── Subtitle / context (14px, glow-400)
  └── [Right]
        └── Primary action button (e.g., "+ Kỳ thi mới")
```

Page title dùng sizing H1 (`30px`), nhưng căn chỉnh visual với card content bên dưới bằng left padding nhất quán. Không có decorative lines hoặc underlines bên dưới title.

---

### 5.3 Data Filters

Đặt ngay phía trên table hoặc card list.

```
[Filter bar]
  ├── [Search input] — flex-1, max-width 320px
  ├── [Select dropdowns] — cho category/status/class filters
  └── [Right-aligned] — Sort control, Export button (Ghost)
```

Active filter xuất hiện dưới dạng **removable tags** bên dưới filter bar, dùng Tag component với icon `×`.

---

## 6. Exam UI

Giao diện thi là một visual context riêng biệt so với teacher dashboard. Nó được thiết kế để tối đa hóa sự tập trung cho học sinh và giảm thiểu cognitive load trong đánh giá có rủi ro cao.

### Desktop Layout Overview

Exama hỗ trợ hai **display mode** để render câu hỏi thi. Mode được giáo viên thiết lập khi tạo bài thi và không thể thay đổi bởi học sinh giữa phiên.

| Mode | Mặc định | Mô tả |
|---|---|---|
| **Paged** | Không | Một câu hỏi mỗi lần. Điều hướng bằng nút ← Trước / Tiếp theo →. |
| **Continuous Scroll** | **Có** | Tất cả câu hỏi trong một cột cuộn. Điều hướng bằng cuộn hoặc jump-link Question Map. |

Trên desktop (≥ 1024px), cả hai mode chia sẻ cùng shell ba vùng:

```
┌─────────────────────────────────────────────────────────────┐
│                      EXAM TOPBAR (56px)                     │
├──────────────────┬──────────────────────────────────────────┤
│  QUESTION MAP    │                                          │
│  (left panel)    │         QUESTION PANEL                   │
│  width: 220px    │         (main content area)              │
│  fixed height    │         flex-1, scrollable               │
│  scrolls indep.  │                                          │
│                  │  — Paged:  một câu + Prev/Next           │
│  [Nộp bài]       │  — Scroll: tất cả câu hỏi xếp chồng     │
└──────────────────┴──────────────────────────────────────────┘
```

Question Map được đặt ở **bên trái** vì nó phục vụ vai trò điều hướng — tương tự mục lục. Người dùng đọc trái-qua-phải; đặt map ở trái nghĩa là nó được nhìn thấy đầu tiên, cung cấp context trước khi tương tác với nội dung câu hỏi.

---

### 6.1 Exam Topbar

Thanh cố định ở đầu màn hình thi trong suốt phiên.

```
height: 56px
background: slate-800
border-bottom: 1px solid slate-600
padding: 0 20px
position: sticky, top: 0, z-index: 40
```

**Bên trái:** Logo sản phẩm (Noto Serif, `glow-700`) + separator (`slate-600`, 1px vertical) + tên kỳ thi (DM Sans 14px, `glow-500`).
**Bên phải:** Timer component + progress indicator ("18 / 25 đã trả lời").

Topbar không chứa nút Nộp bài hoặc navigation link. Nó chỉ truyền đạt identity, thời gian và tiến độ. Action Nộp bài nằm độc quyền trong Question Map panel nơi nó yêu cầu điều hướng không gian có chủ đích để đạt đến.

---

### 6.2 Question Map — Desktop (Left Panel)

Question Map là **left panel có độ rộng cố định** (220px) tồn tại song song với vùng câu hỏi có thể cuộn. Nó phục vụ cả vai trò điều hướng và tổng quan tiến trình visual.

```
width: 220px
height: calc(100vh - 56px)
position: sticky
top: 56px
border-right: 1px solid slate-600
background: slate-800
padding: 16px
overflow-y: auto
display: flex
flex-direction: column
gap: 16px
```

**Section header:** Label style ("QUESTION MAP"), `glow-300`, `letter-spacing: 0.07em`.

**Question bubbles:** Hình vuông 32×32px trong grid dùng `grid-template-columns: repeat(auto-fill, minmax(32px, 1fr))`, `gap: 6px`. Mỗi bubble là click target điều hướng trực tiếp đến câu hỏi đó.

| State | Background | Text color | Border |
|---|---|---|---|
| Unanswered | `slate-700` | `glow-300` | None |
| Answered | `accent-900` | `accent-400` | None |
| Current | `accent-500` | `glow-700` | None |
| Flagged | `#221800` | `#e8b84b` | `1.5px solid #4a3200` |
| Flagged + Answered | `#2a1e00` | `#f0cc72` | `1.5px solid #4a3200` |

Chấm tròn nhỏ (6px, fill `#e8b84b`) xuất hiện ở góc trên-phải của bất kỳ bubble nào đang flagged để vẫn hiển thị kể cả khi bubble ở trạng thái Answered.

**Legend:** Khối legend nhỏ gọn bên dưới grid. Bốn hàng, mỗi hàng có swatch 12×12px và label (DM Sans 12px, `glow-400`).

**Spacer:** `flex: 1` giữa legend và nút nộp bài, đẩy nút xuống cuối panel.

**Submit button:** Full-width, Danger variant, `margin-top: auto`, ghim xuống đáy panel. Khi click, kích hoạt Confirmation Modal trước khi nộp.

```
[Submit button]
  └── onClick → opens Confirmation Modal
        ├── Title: "Nộp bài"
        ├── Body: "Bạn còn X câu chưa trả lời. Hành động này không thể hoàn tác."
        └── Actions: [Quay lại] (Secondary)  [Nộp ngay] (Danger)
```

---

### 6.3 Question Panel

Vùng đọc và trả lời chính. Chiếm toàn bộ không gian ngang còn lại sau left panel.

```
flex: 1
padding: 28px 32px
overflow-y: auto
height: calc(100vh - 56px)
background: slate-900
max-width: none
```

Nội dung nội bộ (thân câu hỏi + lựa chọn đáp án) bị giới hạn `max-width: 680px` cho độ dài dòng thoải mái, nhưng ràng buộc này nằm trên content wrapper bên trong panel — không phải trên panel.

#### Paged Mode

Một câu hỏi được hiển thị mỗi lần. Panel render một khối câu hỏi duy nhất và navigation footer.

**Question header row:**
- Number badge: 28×28px vuông, `border-radius: 6px`, `background: accent-500`, `glow-700`, DM Sans 14px bold
- "Câu X / Y" theo Label style (`glow-400`, uppercase, `letter-spacing: 0.07em`)
- Flag toggle button (Ghost, icon-only): Toggle trạng thái flagged. Icon: flag outline → flag filled (`#e8b84b`) khi active.

**Question body:** Noto Serif 18px, `glow-700`, `line-height: 1.7`. Max content width: `680px`.

**Answer options area:** Ngay bên dưới question body, `margin-top: 24px`.

**Navigation footer:** Divider `border-top: 1px solid slate-600`, `margin-top: 32px`, phía trên hàng `flex justify-between`:
- Trái: "← Trước" (Secondary button) — disabled và mờ trên câu hỏi 1
- Phải: "Tiếp theo →" (Primary button) — label đổi thành "Kết thúc" ở câu hỏi cuối

#### Continuous Scroll Mode *(mặc định)*

Tất cả câu hỏi được render như một tài liệu xếp dọc duy nhất.

**Question block:**
```
padding: 28px 32px
border-bottom: 1px solid slate-600
max-width: 680px
```

Khối câu hỏi cuối không có `border-bottom`. Không có card border hoặc shadow trên các khối câu hỏi riêng lẻ — chúng chỉ được phân cách bằng divider line.

**Question block anatomy:**
```
[Question block]
  ├── [Header row]  number badge + "Q X / Y" + flag button
  ├── [Question body]  Noto Serif 18px, glow-700
  ├── [Answer options]  margin-top: 24px
  └── [Block footer]  border-top slate-600, padding-top: 20px
                       "Đánh dấu xem lại" ghost button (left)
```

**Scroll-linked Question Map:** Trong continuous scroll mode, Question Map theo dõi câu hỏi đang hiển thị khi người dùng cuộn bằng `IntersectionObserver`.

**Anchor navigation:** Click bubble trong Question Map smooth-scroll panel đến khối câu hỏi đó bằng `element.scrollIntoView({ behavior: 'smooth', block: 'start' })` với `scroll-padding-top` offset cho topbar height.

```css
.question-panel {
  scroll-padding-top: 56px;
}
```

---

### 6.4 Answer Options

#### Multiple Choice (Single Answer)

Mỗi lựa chọn là full-width clickable row với custom radio button, nhãn chữ cái và text đáp án.

```
border: 1.5px solid slate-500
border-radius: 6px
padding: 12px 16px
background: slate-800
cursor: pointer
gap: 12px
```

| State | Border | Background | Radio |
|---|---|---|---|
| Default | `slate-500` | `slate-800` | Unchecked |
| Hover | `accent-600` | `slate-700` | Unchecked |
| Selected | `accent-500` | `accent-900` | Checked (accent dot) |
| Correct (review) | `#1a4a1a` | `#0d200d` | Checked (green dot) |
| Wrong (review) | `#4a1a1a` | `#220d0d` | Checked (red dot), text struck through |
| Unselected correct (review) | `#1a4a1a` | `#0d200d` | Unchecked |

Trong review mode, các lựa chọn sai không được chọn xuất hiện với opacity giảm (`0.5`) để de-emphasize.

#### Multiple Choice (Multiple Answers)

Layout giống single-answer nhưng dùng Checkbox component thay vì Radio. Hướng dẫn nêu rõ "Chọn tất cả đáp án đúng." bằng DM Sans 13px, `glow-400`, italic, ngay trên danh sách lựa chọn.

#### Short Answer / Essay

Full-width Textarea với chỉ báo đếm ký tự/từ (DM Sans 12px, `glow-400`) ở dưới-phải. Không thay đổi viền ở trạng thái answered — sự hiện diện của text ngụ ý đã trả lời.

---

### 6.5 Timer

Timer component được hiển thị trong Exam Topbar.

**Default state (> 5 phút):**
```
background: slate-700
border: 1px solid slate-500
padding: 6px 12px
border-radius: 6px
icon: clock, glow-400
font: system monospace, 14px, font-weight 700, glow-600
```

**Warning state (≤ 5 phút):**
```
background: #221800
border: #4a3200
icon: clock, #e8b84b
font: #f0cc72
```

**Critical state (≤ 1 phút):**
```
background: #220d0d
border: #4a1a1a
icon: clock, #e07272
font: #ea9090
```

Timer chuyển state đúng lúc 5:00 và 1:00. Không có animation khi chuyển state — sự thay đổi màu sắc là thông tin truyền đạt. Định dạng timer là `MM:SS`. Giờ được hiển thị (`HH:MM:SS`) chỉ cho kỳ thi dài hơn 60 phút.

---

### 6.6 Result Screen

Hiển thị sau khi bài thi được nộp hoặc sau khi timer hết giờ. Đây là trang focused, căn giữa.

**Score circle:** Đường tròn 80×80px. Viền: `4px solid` theo màu semantic (success, warning hoặc danger dựa trên ngưỡng điểm). Bên trong: điểm số dưới dạng `font-serif text-3xl font-bold` bằng màu text semantic tương ứng. Background của vòng tròn là semantic background tint.

**Score thresholds:**
- ≥ 8.0 → Success (xanh lá)
- 5.0–7.9 → Warning (vàng)
- < 5.0 → Danger (đỏ)

**Stat row:** Ba ô bằng nhau — Đúng, Sai, Bỏ qua. Mỗi ô hiển thị số lớn (Noto Serif 28px, `glow-700`) với label (12px, `glow-300`).

**Progress bar:** Full-width, hiển thị phần trăm điểm với fill color semantic.

**Actions:** Hai button — "Xem lại đáp án" (Secondary) và "Về trang chủ" (Primary).

---

### 6.7 Review Mode

Sau khi nộp bài, học sinh (và giáo viên) có thể review kỳ thi với các trạng thái đúng/sai được hiển thị.

**Correct answer (học sinh chọn đúng):**
- Viền xanh lá + nền xanh lá tối trên lựa chọn (`border: #1a4a1a`, `background: #0d200d`)
- Icon checkmark bên phải (`#6ec46e`)
- Text đáp án: `#6ec46e`, font-weight: 500

**Wrong answer (học sinh chọn sai):**
- Viền đỏ + nền đỏ tối trên lựa chọn (`border: #4a1a1a`, `background: #220d0d`)
- Icon X bên phải (`#e07272`)
- Text đáp án: `#e07272`, `text-decoration: line-through`

**Correct answer (học sinh không chọn):**
- Viền xanh lá + nền xanh lá tối
- Không có icon (để phân biệt với học sinh-chọn-đúng)

**Explanation callout:** Bên dưới answer options, một `Info` callout hiển thị giải thích. Label: "Giải thích" trong `glow-500 font-semibold`. Body: DM Sans 14px, `glow-400`.

---

### 6.8 Display Mode: Paged vs Continuous Scroll

Phần này tổng hợp tất cả sự khác biệt về hành vi giữa hai display mode để tham khảo khi implement.

#### Mode Selection

Giáo viên chọn display mode trong exam creation settings. Mặc định là **Continuous Scroll**.

```
[Exam Settings — Display Mode]
  ● Cuộn liên tục (mặc định)
    "Tất cả câu hỏi trên một trang. Học sinh cuộn tự do."
  ○ Phân trang
    "Một câu hỏi mỗi màn hình. Học sinh điều hướng bằng Trước / Tiếp theo."
```

#### Behavioral Comparison

| Behavior | Paged | Continuous Scroll |
|---|---|---|
| Câu hỏi được render | Từng câu một | Tất cả cùng lúc |
| Điều hướng | ← Trước / Tiếp theo → | Cuộn + jump-link Question Map |
| Theo dõi "Current" trong Question Map | Set rõ ràng bằng navigation | Set bằng scroll position (IntersectionObserver) |
| Navigation footer | Có | Không |
| Học sinh xem trước câu hỏi tương lai | Không | Có |
| Scroll khi nhảy Map | Trang thay thế câu hỏi hiện tại | Smooth scroll đến anchor |
| Auto-save câu trả lời | Khi click lựa chọn | Khi click lựa chọn (giống) |
| Cập nhật progress bar | Khi điều hướng đến câu đã trả lời | Ngay khi click lựa chọn |
| Bước tóm tắt trước nộp bài | Có (sau Next → cuối cùng) | Không — nộp trực tiếp từ Map panel |
| Browser back-button | Quay lại câu hỏi trước | Thoát kỳ thi (cảnh báo người dùng) |

#### Question Divider in Continuous Scroll

Mỗi khối câu hỏi được ngăn cách bằng rule `border-bottom: 1px solid slate-600`. Nhãn số câu hỏi nổi nhẹ ở left margin của mỗi khối dùng `position: relative` + pseudo-element `::before`, styled theo Label (`glow-300`, 11px, uppercase) để hoạt động như margin note anchor.

```css
.question-block::before {
  content: 'C' attr(data-question-number);
  position: absolute;
  left: -48px;
  top: 28px;
  font-size: 11px;
  font-weight: 600;
  letter-spacing: 0.07em;
  text-transform: uppercase;
  color: var(--color-glow-300);
}
```

#### Summary Screen (Paged Mode Only)

Trong Paged mode, click "Kết thúc" ở câu hỏi cuối điều hướng đến summary screen trước khi nộp:

```
[Summary screen]
  ├── Title: "Xem lại trước khi nộp"
  ├── Subtitle: "X trong Y câu đã trả lời."
  ├── [Summary table]
  │     Columns: Câu | Trạng thái | Nhảy đến
  │     Rows: mỗi câu một hàng
  │       Status: "Đã trả lời" (success), "Chưa trả lời" (glow-400), "Đã đánh dấu" (warning)
  │       Nhảy: text link → quay lại câu đó trong paged view
  └── [Footer]
        [Quay lại] (Secondary)    [Nộp bài] (Danger)
```

---

## 7. Mobile Design System

Mobile là context first-class trong Exama. Học sinh thường truy cập kỳ thi trên điện thoại, đặc biệt trong bối cảnh lớp học không có laptop. Giáo viên dùng mobile để theo dõi phiên thi trực tiếp và kiểm tra kết quả khi di chuyển.

### 7.1 Breakpoints & Responsive Strategy

Exama dùng bốn breakpoint:

| Breakpoint | Range | Context |
|---|---|---|
| `xs` | 0 – 479px | Điện thoại nhỏ (iPhone SE, Android cũ) |
| `sm` | 480 – 767px | Điện thoại lớn, phablet hẹp |
| `md` | 768 – 1023px | Tablet, phablet lớn (portrait) |
| `lg` | 1024 – 1279px | Tablet (landscape), laptop nhỏ |
| `xl` | 1280px+ | Desktop, full layout |

**Mobile** chỉ `xs` và `sm`. **Tablet** chỉ `md`. **Desktop** chỉ `lg` và `xl`.

#### Strategy: Mobile-First

Tất cả base styles nhắm đến mobile. Desktop styles được thêm bằng media query `min-width`. Điều này đảm bảo bundle cơ sở không bao giờ tải CSS desktop-only không dùng trên mobile.

#### Layout Shifts by Breakpoint

| Feature | Mobile (xs/sm) | Tablet (md) | Desktop (lg+) |
|---|---|---|---|
| Sidebar | Ẩn → Bottom tab bar | Collapsible icon-rail (48px) | Fixed sidebar (220px) |
| Exam Question Map | Expandable top drawer | Collapsible left panel (180px) | Fixed left panel (220px) |
| Exam layout | Single column, full-width | Two column (map 180px + content) | Two column (map 220px + content) |
| Cards | Full-width, không margin ngang | 2-column grid | 3-column grid |
| Tables | Thay bằng list-card view | Horizontal scroll hoặc list-card | Full table |
| Modals | Bottom sheet (full width, partial height) | Centered dialog | Centered dialog |
| Pagination | Prev / Next only, không page numbers | Condensed (3 trang + ellipsis) | Full |

---

### 7.2 Mobile Typography

Tất cả type sizes giảm vừa phải trên mobile. Line-height tăng nhẹ cho context đọc trên màn hình cảm ứng.

| Style | Desktop | Mobile (xs/sm) | Change |
|---|---|---|---|
| Display | 48px / lh 1.15 | 32px / lh 1.2 | −16px |
| H1 | 30px / lh 1.25 | 24px / lh 1.3 | −6px |
| H2 | 24px / lh 1.3 | 20px / lh 1.35 | −4px |
| H3 | 20px / lh 1.4 | 18px / lh 1.4 | −2px |
| H4 | 16px / lh 1.4 | 15px / lh 1.45 | −1px |
| Body Large | 16px / lh 1.6 | 16px / lh 1.65 | không đổi |
| Body | 14px / lh 1.6 | 14px / lh 1.65 | không đổi |
| Body Small | 13px / lh 1.5 | 13px / lh 1.55 | không đổi |
| Label | 11px, uppercase | 11px, uppercase | không đổi |
| **Question body** | **18px / lh 1.7** | **16px / lh 1.75** | −2px |

---

### 7.3 Mobile Spacing & Touch Targets

#### Touch Target Minimum

Tất cả element tương tác phải đáp ứng **touch target tối thiểu 44×44px** (Apple HIG) bất kể kích thước visual của chúng. Element visual nhỏ được bao quanh bởi padding vô hình để đạt mức tối thiểu này.

```css
/* Example: icon button visual 32px, touch target 44px */
.icon-button-sm {
  width: 32px;
  height: 32px;
  position: relative;
}
.icon-button-sm::before {
  content: '';
  position: absolute;
  inset: -6px;   /* mở rộng vùng click lên 44px */
}
```

#### Mobile Spacing Adjustments

Trên mobile, `p-6` chuẩn (24px) card padding giảm xuống `p-4` (16px). Section gap giảm từ `space-8` (32px) xuống `space-6` (24px). Page horizontal padding giảm từ `px-6` (24px) xuống `px-4` (16px).

| Token | Desktop | Mobile |
|---|---|---|
| Card padding | 24px (`p-6`) | 16px (`p-4`) |
| Page horizontal padding | 24px (`px-6`) | 16px (`px-4`) |
| Section gap | 32px | 24px |
| Form field gap | 20px | 16px |
| Button height (md) | 38px | 44px (touch minimum) |
| Input height | 38px | 44px (touch minimum) |

---

### 7.4 Mobile Navigation — Bottom Tab Bar

Trên mobile, teacher dashboard dùng **bottom tab bar** thay vì desktop sidebar.

```
position: fixed
bottom: 0
left: 0
right: 0
height: 56px (+ safe-area-inset-bottom cho notch/home indicator)
background: slate-800
border-top: 1px solid slate-600
display: flex
z-index: 50
```

**Tab items:** Cột bằng nhau (thường 4–5 tab). Mỗi tab chứa:
- Icon (20px, căn giữa ngang)
- Label (DM Sans 10px, căn giữa, `letter-spacing: 0.03em`)
- `gap: 3px` giữa icon và label

```
[Tab item]
  ├── Icon (20px)
  │     Resting: glow-400
  │     Active:  accent-400
  └── Label (10px)
        Resting: glow-400
        Active:  accent-400, font-weight: 600
```

Tab active: Icon và label đều trong tone accent. Không có background pill hoặc underline — màu sắc là đủ.

**Tab items cho teacher role:**

| Tab | Icon | Label |
|---|---|---|
| Home | house | Tổng quan |
| Exams | document-text | Kỳ thi |
| Students | users | Học sinh |
| Results | chart-bar | Kết quả |
| More | ellipsis-horizontal | Thêm |

Tab "Thêm" mở **bottom sheet** liệt kê các item ít truy cập (Cài đặt, Hồ sơ, Trợ giúp, Đăng xuất).

**Page content** phải tính cho bottom tab bar. Thêm `padding-bottom: calc(56px + env(safe-area-inset-bottom))` cho tất cả page content container.

---

### 7.5 Mobile Navigation — Hamburger Drawer

Trên tablet (`md`), sidebar icon-rail thu gọn (48px wide, chỉ icon) được dùng. Tap icon mở rộng full sidebar overlay (220px) trượt vào từ trái.

Trên mobile, **hamburger menu** (`☰`) trong top-left của mobile topbar mở cùng full-width drawer để truy cập deep link (Cài đặt, Hồ sơ, v.v.) không thể đến qua bottom tab bar.

**Mobile Topbar (Dashboard):**
```
height: 48px
background: slate-800
border-bottom: 1px solid slate-600
padding: 0 16px
display: flex, align-items: center, justify-content: space-between

Left:  [☰ icon button, 44×44px touch target] + [Product name, Noto Serif 18px, glow-700]
Right: [Avatar, 32px circle] (tap để vào Profile)
```

**Drawer:**
```
position: fixed
top: 0, left: 0, bottom: 0
width: min(80vw, 280px)
background: slate-800
border-right: 1px solid slate-600
box-shadow: shadow-dark-lg
z-index: 60
transform: translateX(-100%)   /* closed */
transform: translateX(0)       /* open */
transition: transform 200ms ease-out
```

**Overlay phía sau drawer:** `background: rgba(0,0,0,0.60)`, tap để đóng drawer.

---

### 7.6 Mobile Cards & Lists

#### Exam Cards

Trên mobile, exam card **full-width** (không grid). Stack dọc với `gap: 12px`. Page container horizontal padding (`px-4`) tạo không gian thở.

Card internal layout chuyển từ multi-column header phức tạp sang linear stack đơn giản:

```
[Card]  background: slate-800
  ├── [Top row] Subject tag (left) + Status badge (right)
  ├── [Title] H3 (18px, Noto Serif, glow-700)
  ├── [Subtitle] Tên lớp · Số học sinh (13px, glow-400)
  └── [Footer row] Số câu · Thời gian (left) + Số đã nộp (right)
```

Min-height: `80px`. Card không hiển thị hover state trên mobile. Thay vào đó, toàn bộ card có `active:` state — `background: slate-700` — để cung cấp press feedback.

#### Stat Cards

Trên mobile, stat card sắp xếp trong **2-column grid** với padding giảm (`p-4`). Kích thước số lớn giảm từ `text-4xl` (36px) xuống `text-3xl` (30px).

---

### 7.7 Mobile Forms

Form layout luôn là **single-column** trên mobile. Multi-column form layouts từ desktop thu gọn thành sequential stacked fields.

**Input fields:** Chiều cao tăng lên 44px tối thiểu (từ 38px trên desktop). Padding điều chỉnh phù hợp: `padding: 10px 13px`.

**Keyboard-aware layout:** Các trang chứa form phải được wrap trong scroll container vẫn dùng được khi virtual keyboard xuất hiện. Input đang focused phải được scroll vào view và không bị keyboard che. Dùng `scroll-padding-bottom: 16px` trên scroll container.

**Select trên mobile:** Native `<select>` được ưu tiên trên mobile vì dùng native picker của nền tảng, được tối ưu cho ngón cái và accessible. Custom select dropdown chỉ dùng khi cần lọc hoặc search trong danh sách (> 10 lựa chọn).

**Date/time pickers:** Luôn dùng native `<input type="date">` và `<input type="time">` trên mobile để tận dụng native date picker UI của nền tảng.

---

### 7.8 Mobile Tables → List View

Full table (nhiều cột) không dùng được trên màn hình nhỏ. Trên mobile (`xs`/`sm`), tất cả table được thay bằng **list-card view**.

Mỗi table row trở thành một card:

```
[Row Card]  padding: 14px 16px, border-bottom: 1px solid slate-700
            background: slate-800
  ├── [Top row]
  │     ├── [Left] Identity (avatar + tên, font-weight: 500, glow-600)
  │     └── [Right] Primary value (điểm, status badge)
  └── [Bottom row]  margin-top: 6px
        ├── [Left] Secondary info (lớp, ngày) — 13px, glow-400
        └── [Right] Action link — accent-400, 13px
```

List-card view không hiển thị table header. Thay vào đó, **sort/filter bar** (hàng ngang cuộn được của compact filter chip) nằm phía trên list.

Trên tablet (`md`), full table được phép nếu column count ≤ 4. Table rộng hơn nên scroll ngang trong container với `-webkit-overflow-scrolling: touch`.

---

### 7.9 Mobile Modals → Bottom Sheet

Trên mobile, tất cả modal chuyển thành **bottom sheet** — panel trượt lên từ đáy màn hình.

```
position: fixed
bottom: 0, left: 0, right: 0
background: slate-800
border-radius: 12px 12px 0 0
border-top: 1px solid slate-600
padding: 20px 16px
padding-bottom: calc(20px + env(safe-area-inset-bottom))
box-shadow: 0 -4px 24px rgba(0,0,0,0.50)
z-index: 60
max-height: 90vh
overflow-y: auto
```

**Drag handle:** Pill 36×4px, `background: slate-600`, `border-radius: 2px`, căn giữa ngang ở đầu sheet với margin 12px bên dưới.

**Overlay:** `rgba(0,0,0,0.60)`. Tap overlay để dismiss bottom sheet.

**Confirmation bottom sheet** (e.g., nộp bài, xóa kỳ thi) giới hạn `max-height: 50vh` và chỉ chứa title, mô tả ngắn và hai action button xếp dọc (Danger/Destructive ở trên, Secondary cancel ở dưới).

---

### 7.10 Mobile Exam UI — Topbar

Trên mobile, exam topbar thích nghi để vừa với thông tin quan trọng trong 48px height.

```
height: 48px
background: slate-800
border-bottom: 1px solid slate-600
padding: 0 12px
position: sticky, top: 0, z-index: 40
```

```
[Left]   [☰ Map icon] (44×44px, mở Question Map Drawer)
[Center] Tên kỳ thi (DM Sans 14px, glow-500, truncated)
[Right]  Timer component (compact)
```

Map icon là affordance chính để mở Question Map drawer. Touch target 44×44px. Badge hiển thị số câu chưa trả lời xuất hiện phía trên khi còn câu chưa trả lời.

**Badge on map icon:**
```
position: absolute, top-right của icon
background: #e8b84b
color: slate-900
font: DM Sans 10px, font-weight: 700
border-radius: full
min-width: 16px, height: 16px
padding: 0 4px
```

Progress bar (thanh 4px mỏng hiển thị answered/total) nằm ở cạnh dưới cùng của topbar — full width, `slate-600` track, `accent-500` fill.

---

### 7.11 Mobile Exam UI — Question Map Drawer

Trên mobile, Question Map không phải panel cố định. Nó là **collapsible top drawer** được kích hoạt bằng tap Map icon trong topbar.

**Closed state:** Drawer ẩn hoàn toàn. Progress bar trong topbar truyền đạt tiến trình tổng thể thụ động.

**Open state:** Drawer trượt xuống từ bên dưới topbar, overlay lên nội dung câu hỏi.

```
position: fixed
top: 48px   /* ngay dưới topbar */
left: 0, right: 0
background: slate-800
border-bottom: 1px solid slate-600
box-shadow: shadow-dark-md
padding: 16px
z-index: 39
max-height: calc(60vh)
overflow-y: auto

open:  transform: translateY(0),   opacity: 1
closed: transform: translateY(-8px), opacity: 0
transition: 200ms ease-out
```

**Drawer contents:**

```
[Header row]
  ├── "QUESTION MAP" label (glow-300, uppercase)
  └── [✕ Close button] (Ghost, 44×44px, right-aligned)

[Bubble grid]
  └── grid-template-columns: repeat(auto-fill, minmax(40px, 1fr))
      gap: 8px
      Bubble size: 40×40px (lớn hơn desktop cho touch)
      Màu trạng thái giống desktop

[Legend row]
  └── Horizontal flex, gap: 16px (compact horizontal legend)
      Mỗi item: swatch 10×10px + label 12px

[Submit button]
  └── Full-width, Danger variant, margin-top: 16px
```

Bubble grid dùng `repeat(auto-fill, minmax(40px, 1fr))` — số cột tự động từ độ rộng drawer sau khi trừ horizontal padding. Trên điện thoại 360px với padding 16px mỗi bên (328px usable), cho ~7 cột; trên 430px (~398px usable) cho ~9 cột. Bubble size **40×40px** trên mobile (vs 32×32px trên desktop) để đáp ứng touch target minimum.

Tap bất kỳ bubble nào sẽ đóng drawer và scroll đến câu hỏi đó.

**Overlay:** `rgba(0,0,0,0.40)` (nhạt hơn modal overlay) phía sau drawer. Tap overlay để đóng drawer.

---

### 7.12 Mobile Exam UI — Question Panel

Trên mobile, Question Panel full-width và scrollable. Không có persistent sidebar.

```
padding: 16px
padding-bottom: 80px   /* space cho fixed navigation footer */
background: slate-900
```

**Question header:** Number badge (24×24px, `background: accent-500`, `glow-700`) + nhãn "C X / Y", hàng ngang.

**Flag button:** Đặt inline trong header row, right-aligned. Touch target 44×44px.

**Question body:** Noto Serif 16px, `glow-700`, `line-height: 1.75`.

**Answer options:** Full-width. Padding tăng lên `14px 16px` cho touch thoải mái. Gap giữa lựa chọn: `10px`.

**Fixed navigation footer:** Điều hướng Trước/Tiếp theo được **ghim xuống đáy** màn hình.

```
position: fixed
bottom: 0, left: 0, right: 0
height: 56px
padding: 8px 16px
padding-bottom: calc(8px + env(safe-area-inset-bottom))
background: slate-800
border-top: 1px solid slate-600
display: flex, gap: 12px, align-items: center
z-index: 30
```

```
[← Trước]    flex: 1, Secondary button, height: 40px
[Tiếp theo →] flex: 1, Primary button, height: 40px
```

---

### 7.13 Mobile Exam UI — Continuous Scroll Mode

Continuous Scroll là mode mặc định và hoạt động đặc biệt tốt trên mobile. Layout tuyến tính, top-to-bottom khớp với gesture tự nhiên của cuộn màn hình điện thoại.

**Layout:** Question panel là single tall scroll container. Không có fixed navigation footer. Các element cố định duy nhất là topbar (trên) và safe-area-aware padding ở đáy.

```
padding: 16px
padding-bottom: calc(32px + env(safe-area-inset-bottom))
```

**Question blocks trên mobile:**

```
padding-bottom: 24px
border-bottom: 1px solid slate-600
margin-bottom: 24px
```

Không có left-margin question number pseudo-element trên mobile (không đủ không gian ngang). Number badge bên trong block header là identifier câu hỏi duy nhất.

**Scroll-linked Question Map:** Logic `IntersectionObserver` tương tự áp dụng trên mobile. Khi học sinh cuộn, active bubble trong Question Map drawer cập nhật. Khi drawer mở giữa scroll, active bubble được hiển thị ngay lập tức.

**Anchor jump:** Tap bubble trong Question Map drawer đóng drawer, sau đó smooth-scroll question panel đến khối target. Giá trị `scroll-padding-top` trên mobile phải tính cho topbar height (`48px`):

```css
.question-panel-mobile {
  scroll-padding-top: 48px;
}
```

**"Back to top" affordance:** Trong continuous scroll mode trên mobile, một khi học sinh đã cuộn qua câu 5, nút Ghost nhỏ "↑ Đầu trang" xuất hiện ghim ở `bottom: calc(16px + env(safe-area-inset-bottom))`, `right: 16px`. Nút này smooth-scroll về câu 1. Không xuất hiện trong Paged mode.

```
position: fixed
bottom: calc(16px + env(safe-area-inset-bottom))
right: 16px
padding: 8px 12px
background: slate-700
border: 1px solid slate-500
border-radius: 6px
font: DM Sans 12px, glow-400
box-shadow: shadow-dark-md
z-index: 20
```

**Paged mode trên mobile:** Khi giáo viên đã chọn Paged mode, mobile question panel hành xử giống spec §7.12 — một câu hỏi mỗi màn hình, fixed navigation footer ở đáy.

---

### 7.14 Mobile Exam UI — Result Screen

Result screen trên mobile là single full-page scroll. Các element xếp dọc.

```
padding: 24px 16px
padding-bottom: calc(24px + env(safe-area-inset-bottom))
background: slate-900
```

**Score circle:** Giảm từ 80px xuống 72px đường kính. Vẫn căn giữa ở trên cùng. Background vòng tròn là semantic background tint tối.

**Stat row:** Trên mobile, ba thống kê (Đúng / Sai / Bỏ qua) xếp thành hàng ngang bằng nhau. Nếu không đủ chỗ (< 360px), chúng xếp dọc.

**Progress bar:** Full-width, 8px height (dày hơn dashboard progress bar một chút).

**Action buttons:** Xếp dọc — "Xem lại đáp án" ở trên, "Về trang chủ" ở dưới. Mỗi button full-width, 44px height.

---

## 8. Motion & Interaction

Exama cố ý **ít motion**. Bối cảnh thi đòi hỏi sự tập trung, và animation không cần thiết là sự phân tâm.

### Permitted Transitions

| Element | Property | Duration | Easing |
|---|---|---|---|
| Button hover | `background-color`, `border-color` | 120ms | `ease-out` |
| Card hover | `border-color`, `box-shadow`, `background-color` | 150ms | `ease-out` |
| Answer option hover/select | `background-color`, `border-color` | 100ms | `ease-out` |
| Input focus | `border-color`, `box-shadow` | 120ms | `ease-out` |
| Timer state change | `background-color`, `color` | 300ms | `ease` |
| Modal open (desktop) | `opacity` (overlay) | 180ms | `ease-out` |
| Tab switch | `border-color` (active indicator) | 120ms | `ease` |
| Bottom sheet open (mobile) | `transform: translateY` | 250ms | `ease-out` |
| Question Map drawer open (mobile) | `transform: translateY`, `opacity` | 200ms | `ease-out` |
| Sidebar drawer open (mobile) | `transform: translateX` | 200ms | `ease-out` |
| Bottom tab bar active change | `color` | 100ms | `ease` |

### Mobile-Specific Motion Notes

Trên mobile, transition phục vụ mục đích khác: chúng truyền đạt quan hệ không gian (drawer trượt từ hướng phù hợp với nguồn gốc của chúng) và xác nhận touch event. Các nguyên tắc vẫn giống nhau — transition nhanh và có chức năng, không trang trí.

`prefers-reduced-motion: reduce` phải được tôn trọng. Tất cả transition phải được wrap:

```css
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    transition-duration: 0.01ms !important;
    animation-duration: 0.01ms !important;
  }
}
```

### Prohibited

- Scale transform khi hover hoặc active (desktop hoặc mobile)
- Slide-in/slide-out transition cho page navigation (dùng instant swap)
- Scroll-triggered animation
- Parallax effect
- Loading skeleton pulse animation
- Easing curve nảy hoặc đàn hồi
- Spring physics trong drawer hoặc sheet

### Loading State

Spinner xoay trên button là animation kéo dài duy nhất trong hệ thống. Tất cả trạng thái loading khác được biểu diễn bằng UI tĩnh: spinner trong button, hoặc text "Đang tải…" trong content area.

---

## 9. Accessibility

### Color

- Tất cả text đáp ứng WCAG AA (4.5:1) tối thiểu; primary text đáp ứng AAA (7:1).
- Trạng thái **không bao giờ chỉ truyền đạt bằng màu** — icon, label hoặc pattern đi kèm với tất cả semantic color use.
- Focus ring dùng `box-shadow: 0 0 0 3px rgba(78,132,180,0.35)` — hiển thị trên cả nền `slate-800` và `slate-900`.

### Keyboard Navigation

- Tất cả element tương tác có thể đến bằng Tab theo thứ tự DOM logic.
- Modal trap focus trong khi mở.
- Question Map bubble có thể điều hướng bằng arrow key (role: `grid`).
- Nộp bài yêu cầu click button rõ ràng — không có keyboard shortcut kích hoạt nộp bài.

### Touch & Mobile Accessibility

- Tất cả element tương tác đáp ứng **touch target tối thiểu 44×44px** (Apple HIG / WCAG 2.5.5).
- Touch target trông nhỏ hơn visual dùng invisible padding extension.
- Bottom sheet và drawer có thể dismiss bằng vuốt xuống hoặc tap overlay.
- Question Map drawer trên mobile nhận focus khi mở; focus trả về Map icon khi đóng.
- Bottom tab bar item có `role="tab"` và `aria-selected` để truyền đạt trạng thái active cho screen reader.

### Screen Readers

- Tất cả icon-only button có `aria-label`.
- Status badge có `role="status"` hoặc được wrap trong `aria-live="polite"` region khi cập nhật động.
- Timer thông báo thời gian còn lại ở ngưỡng 5 phút và 1 phút qua `aria-live="assertive"`.
- Form error được liên kết với control qua `aria-describedby`.
- Question Map drawer có `aria-expanded` trên trigger và `role="dialog"` trên drawer panel.
- Badge đếm trên Map icon được thông báo qua `aria-label="X câu chưa trả lời"`.

### Focus Management

- Khi modal hoặc bottom sheet mở, focus di chuyển đến element tương tác đầu tiên của panel.
- Khi modal hoặc bottom sheet đóng, focus trả về element trigger.
- Khi Question Map drawer mở trên mobile, focus di chuyển đến bubble đầu tiên hoặc nút đóng.
- Page navigation không scroll về đầu — focus được đặt trên `<h1>` chính của view mới.

---

## 10. Writing Style

Copy của Exama **rõ ràng, trực tiếp và tôn trọng**. Người dùng đang chịu áp lực thời gian; mỗi từ phải xứng đáng với vị trí của nó.

### Voice Attributes

- **Calm** — Không bao giờ báo động, kể cả cho trạng thái lỗi.
- **Direct** — Câu hành động đứng đầu.
- **Respectful** — Không coi thường. Đối xử với người dùng như người lớn thông minh.
- **Specific** — Tránh thông báo mơ hồ như "Đã xảy ra lỗi."

### Copy Conventions

| Context | Style |
|---|---|
| Page titles | Title case, Noto Serif |
| Button labels | Title case, động từ mệnh lệnh đứng đầu ("Nộp bài", "Thêm câu hỏi") |
| Status badges | Title case ("Đang diễn ra", "Nháp") |
| Table column headers | Title case |
| Label/section headers | CHỮ HOA |
| Alert messages | Sentence case, kết thúc bằng dấu chấm |
| Error messages | Sentence case, action cụ thể ("Nhập địa chỉ email hợp lệ.") |
| Empty states | Thân thiện, không có dấu chấm trên heading |
| Tooltips | Sentence case, không có dấu chấm |

### Numbers

- Điểm số hiển thị với một chữ số thập phân: `8.5`, không phải `8.50` hay `8`.
- Thời gian hiển thị `MM:SS` trong kỳ thi, `09:38 SA` trong danh sách kết quả.
- Số lớn dùng dấu cách làm dấu phân cách hàng nghìn: `20 000`, không phải `20,000`.
- Phân số (câu đã trả lời): `18 / 25`, không phải `18/25` — dấu cách quanh dấu gạch chéo giúp dễ đọc hơn.

---

## 11. Token Reference

Token design đầy đủ để implement.

### Breakpoint Tokens

```css
:root {
  --bp-xs: 0px;
  --bp-sm: 480px;
  --bp-md: 768px;
  --bp-lg: 1024px;
  --bp-xl: 1280px;
}
```

### Touch Target Token

```css
:root {
  --touch-target-min: 44px;
}
```

### Color Tokens

```css
:root {
  /* Slate — Surface Colors */
  --color-slate-900: #16140f;
  --color-slate-800: #1e1c16;
  --color-slate-700: #272419;
  --color-slate-600: #312e22;
  --color-slate-500: #3d392c;

  /* Glow — Text & Foreground */
  --color-glow-100: #2e2b22;
  --color-glow-200: #4a4638;
  --color-glow-300: #6b6555;
  --color-glow-400: #9e9784;
  --color-glow-500: #cec7b5;
  --color-glow-600: #e2ddd1;
  --color-glow-700: #f2ede4;

  /* Accent */
  --color-accent-900: #0d2035;
  --color-accent-800: #112b47;
  --color-accent-700: #1a4268;
  --color-accent-600: #2d6899;
  --color-accent-500: #4e84b4;
  --color-accent-400: #7aa3c8;
  --color-accent-300: #adc5df;

  /* Success */
  --color-success-bg:     #0d200d;
  --color-success-border: #1a4a1a;
  --color-success-base:   #6ec46e;
  --color-success-light:  #8ed98e;

  /* Warning */
  --color-warning-bg:     #221800;
  --color-warning-border: #4a3200;
  --color-warning-base:   #e8b84b;
  --color-warning-light:  #f0cc72;

  /* Danger */
  --color-danger-bg:     #220d0d;
  --color-danger-border: #4a1a1a;
  --color-danger-base:   #e07272;
  --color-danger-light:  #ea9090;

  /* Info (shares accent) */
  --color-info-bg:     #0d1e2d;
  --color-info-border: #112b47;
  --color-info-base:   #7aa3c8;
  --color-info-light:  #adc5df;
}
```

### Spacing Tokens

```css
:root {
  --space-1:  4px;
  --space-2:  8px;
  --space-3:  12px;
  --space-4:  16px;
  --space-5:  20px;
  --space-6:  24px;
  --space-8:  32px;
  --space-10: 40px;
  --space-12: 48px;
  --space-16: 64px;
}
```

### Typography Tokens

```css
:root {
  --font-serif: 'Noto Serif', Georgia, serif;
  --font-sans:  'DM Sans', system-ui, sans-serif;
  --font-mono:  ui-monospace, 'Cascadia Code', monospace;

  --text-xs:      11px;
  --text-sm:      13px;
  --text-base:    14px;
  --text-body:    16px;
  --text-h4:      16px;
  --text-h3:      20px;
  --text-h2:      24px;
  --text-h1:      30px;
  --text-display: 48px;

  --leading-tight:   1.25;
  --leading-snug:    1.4;
  --leading-normal:  1.5;
  --leading-relaxed: 1.6;
  --leading-loose:   1.7;
}
```

### Shadow Tokens

```css
:root {
  --shadow-dark:    0 1px 3px 0 rgba(0,0,0,0.30), 0 1px 2px -1px rgba(0,0,0,0.20);
  --shadow-dark-md: 0 3px 8px 0 rgba(0,0,0,0.40), 0 1px 3px -1px rgba(0,0,0,0.25);
  --shadow-dark-lg: 0 8px 20px 0 rgba(0,0,0,0.50), 0 2px 6px -1px rgba(0,0,0,0.30);
  --shadow-inset:   inset 0 1px 3px rgba(0,0,0,0.30);
  --shadow-focus:   0 0 0 3px rgba(78,132,180,0.35);
}
```

### Border Radius Tokens

```css
:root {
  --radius-sm:   4px;
  --radius-base: 6px;
  --radius-md:   8px;
  --radius-lg:   12px;
  --radius-xl:   16px;
  --radius-full: 9999px;
}
```

---

*Exama Design System Dark Mode v1.0 — Maintained by [kyle2910 (Github)](https://github.com/kyle2910). Covers desktop and mobile.*
