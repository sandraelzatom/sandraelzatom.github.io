# Personal Portfolio – Implementation Spec

## Project Overview

This project is a **single-page personal portfolio** built using **Plain HTML and Tailwind CSS (via CDN)**. The goal is to implement a **Hybrid Editorial / Product Designer style** portfolio that emphasizes **clarity, typography, and structured case study presentation**.

The implementation intentionally minimizes technical complexity to ensure:

* fast setup
* easy updates
* reliable GitHub Pages deployment

This site will be hosted on **GitHub Pages** and will consist of **one `index.html` file**.

---

# 1. Technical Stack

**Core technologies**

* HTML5
* Tailwind CSS via CDN
* Google Fonts

**Deployment**

* GitHub Pages
* Repository format: `username.github.io`

**No build step required.**

Example base setup:

```html
<link href="https://cdn.jsdelivr.net/npm/tailwindcss@3.4.0/dist/tailwind.min.css" rel="stylesheet">
```

---

# 2. Core Structure

The entire site is implemented in a **single file**:

```
/portfolio
    index.html
```

High-level structure:

```
index.html
 ├── Head (fonts + Tailwind)
 ├── Header / Intro Section
 ├── Selected Work Section
 │     ├── Project Card 1
 │     ├── Project Card 2
 │     └── Project Card 3
 └── Footer / Contact
```

---

# 3. Design System

## Spacing System

Use **Tailwind's default spacing scale**, which follows the **4px / 8px rhythm**.

Key spacing tokens used in layout:

| Purpose         | Tailwind Class |
| --------------- | -------------- |
| Section padding | `py-16` (64px) |
| Content spacing | `space-y-6`    |
| Card padding    | `p-6`          |
| Grid gap        | `gap-8`        |

**Rule:**
All major sections must use **64px vertical spacing (`py-16`)**.

---

## Typography

Two Google Fonts will be used.

### Serif (Headings)

Used for editorial tone.

Example:

```
Playfair Display
```

### Sans-serif (Body)

Used for readability.

Example:

```
Inter
```

Font setup:

```html
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500&family=Playfair+Display:wght@500;600&display=swap" rel="stylesheet">
```

Font usage rules:

| Element      | Font       |
| ------------ | ---------- |
| H1 / H2 / H3 | Serif      |
| Body text    | Sans-serif |
| Metadata     | Sans-serif |

Tailwind examples:

```
font-serif
font-sans
```

---

## Typography Hierarchy

Recommended sizes:

| Element         | Tailwind Class          |
| --------------- | ----------------------- |
| Hero Title      | `text-4xl md:text-5xl`  |
| Section Heading | `text-2xl md:text-3xl`  |
| Project Title   | `text-xl`               |
| Body Text       | `text-base`             |
| Meta Text       | `text-sm text-gray-500` |

Line length should stay around **60–75 characters**.

Use a container width:

```
max-w-3xl
```

---

# 4. Layout Specification

## 4.1 Intro / Positioning Statement

Purpose: Immediately communicate **who you are and what you design**.

Structure:

```
Header
  Name
  Positioning statement
  Optional short intro paragraph
```

Example content:

```
Product Designer focused on complex digital systems.

I design clear interfaces and structured user experiences.
Currently studying at NJIT.
```

Tailwind layout:

```
section
container
max-w-3xl
py-16
space-y-6
```

---

## 4.2 Selected Work (3 Project Grid)

Purpose: Showcase **three strong projects only**.

Grid rules:

* Mobile: 1 column
* Tablet: 2 columns
* Desktop: 3 columns

Tailwind example:

```
grid
grid-cols-1
md:grid-cols-2
lg:grid-cols-3
gap-8
```

Each project card includes:

```
Project image
Project title
1 line summary
Role + year
```

Example structure:

```
article
 ├── image
 ├── title
 ├── description
 └── metadata
```

Card padding:

```
p-6
```

---

## 4.3 Contact Footer

Purpose: Provide a **simple way to reach you**.

Content includes:

* Email
* LinkedIn
* GitHub

Example layout:

```
Footer
  Short message
  Email link
  Social links
```

Tailwind spacing:

```
py-16
space-y-4
text-center
```

---

# 5. Mobile Responsiveness

The layout must be **mobile-first**.

Required behavior:

### Grid

```
mobile: 1 column
tablet: 2 columns
desktop: 3 columns
```

### Typography

Hero text scales:

```
text-4xl md:text-5xl
```

### Container width

Use:

```
max-w-5xl
mx-auto
px-6
```

This prevents content from touching screen edges.

---

# 6. Semantic HTML Requirements

Use proper HTML5 semantic tags.

Required structure:

```
<header>
<main>
<section>
<article>
<footer>
```

Example outline:

```
<header>Intro</header>
<main>
  <section>Selected Work</section>
</main>
<footer>Contact</footer>
```

Accessibility considerations:

* meaningful alt text for images
* visible link states
* readable font sizes

---

# 7. GitHub Pages Deployment

Deployment process:

1. Create repository

```
username.github.io
```

2. Add `index.html`

3. Commit and push to `main`.

4. GitHub Pages automatically serves:

```
https://username.github.io
```

No additional configuration required.

---

# 8. Acceptance Criteria

The project is complete when:

### Structure

* Site consists of **a single `index.html` file**
* Uses **Tailwind CSS via CDN**

### Layout

* Includes **intro section**
* Includes **3-project grid**
* Includes **contact footer**

### Design

* Uses **two Google Fonts (serif + sans-serif)**
* Uses **consistent 64px section spacing (`py-16`)**
* Uses **Tailwind spacing system**

### Accessibility

* Semantic HTML structure
* Images include alt text

### Responsiveness

* Layout works on **mobile, tablet, desktop**

### Deployment

* Site loads successfully via **GitHub Pages**

---

# 9. Sprint Map

Development will occur in **three small sprints**.

---

## Sprint 1 — Structure

Goal: Build the layout skeleton.

Tasks:

* Create repository
* Add `index.html`
* Load Tailwind CDN
* Add semantic HTML structure
* Create sections:

  * Header
  * Work grid
  * Footer

Deliverable:

A **functional page layout without real content**.

---

## Sprint 2 — Content

Goal: Populate the portfolio.

Tasks:

* Add positioning statement
* Add project titles and descriptions
* Add placeholder project images
* Add contact information
* Add alt text for images

Deliverable:

A **complete portfolio with real content**.

---

## Sprint 3 — Style & Polish

Goal: Apply typography and design system.

Tasks:

* Add Google Fonts
* Apply font classes
* Adjust spacing using Tailwind
* Refine grid layout
* Verify responsive behavior
* Check section spacing (`py-16`)
* Test GitHub Pages deployment

Deliverable:

A **finished portfolio ready for public viewing**.

---

# 10. Non-Goals

This project intentionally avoids additional complexity.

The following are **out of scope**:

* JavaScript frameworks (React, Vue, etc.)
* Static site generators
* build tools
* Tailwind compilation
* multi-page routing
* CMS integrations
* animations or complex interactions

Future improvements may revisit these if necessary.

---

# 11. Guiding Design Principles

The portfolio should emphasize:

* **clarity over decoration**
* **strong typography**
* **structured presentation of work**
* **fast loading and reliability**

The visual tone should feel closer to **editorial design and product documentation** rather than a flashy design showcase.

---

End of Spec
