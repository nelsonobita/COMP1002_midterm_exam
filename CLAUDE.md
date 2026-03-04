# CLAUDE.md — AI Assistant Guide for COMP1002_midterm_exam

## Project Overview

This is an **educational HTML/CSS project** submitted as a midterm exam for **COMP1002** (Introduction to Web Development or similar). The project consists of a single-page user registration form demonstrating fundamental web development concepts: semantic HTML5 structure, CSS3 styling, and HTML5 form validation.

**Author:** NelsonObita
**Course:** COMP1002
**Purpose:** Midterm exam assignment

---

## Repository Structure

```
COMP1002_midterm_exam/
├── .git/               # Git metadata
├── .gitattributes      # Line ending normalization (text=auto)
├── .gitignore          # Visual Studio-focused ignore patterns
├── README.md           # Minimal project title only
├── Midterm.html        # Main HTML registration form (89 lines)
└── Midterm.css         # CSS stylesheet (77 lines)
```

No build system, no package manager, no backend, no JavaScript, no test suite.

---

## Files

### `Midterm.html`

An HTML5 registration form titled "Login Page Registration" with two `<fieldset>` sections:

**Account Info fieldset:**
- Full Name — `<input type="text">`, `required`, `minlength="2"`
- Email — `<input type="email">`, `required`
- Password — `<input type="password">`, `required`, `minlength="8"`
- Date of Birth — `<input type="date">`, `required`

**Preferences fieldset:**
- Gender — radio buttons (`male`, `female`, `other`), first is `required`
- Country — `<select>` dropdown (`Canada`, `USA`, `UK`), `required`
- Terms agreement — `<input type="checkbox">`, `required`

Submit button with class `btn` and `type="submit"`.

**Known issue:** Line 7 links `href="styles.css"` but the actual file is `Midterm.css`. This stylesheet reference is broken and must be corrected to `href="Midterm.css"`.

### `Midterm.css`

Stylesheet covering: body layout, header/footer, main container, labels, form groups, the registration form, text inputs, focus states, inline radio/checkbox layout, and button styling.

**This file contains intentional syntax errors** that appear to be part of the exam exercise. A student or AI assistant working on this project should be aware of (but not automatically fix) these errors unless explicitly asked:

| Line(s) | Broken syntax | Correct syntax |
|---------|---------------|----------------|
| 3 | `font - family` | `font-family` |
| 11 | `text - align` | `text-align` |
| 27 | `margin - bottom` | `margin-bottom` |
| 31 | `.form - group` | `.form-group` |
| 32 | `margin - bottom` | `margin-bottom` |
| 36 | `# registration-form` | `#registration-form` |
| 42–45 | `input[type = "text"]` (spaces around `=`) | `input[type="text"]` |
| 47 | `width: 100 %` | `width: 100%` |
| 50 | `border - radius` | `border-radius` |
| 54 | `input: focus, select: focus` | `input:focus, select:focus` |
| 60 | `display: inline - flex` | `display: inline-flex` |
| 62 | `margin - right` | `margin-right` |
| 75 | `.btn: hover` | `.btn:hover` |

---

## Known Bugs

1. **Broken stylesheet link** — `Midterm.html:7` references `styles.css`; the file is `Midterm.css`.
2. **CSS syntax errors** — See table above. All errors involve extra whitespace in property names, class/ID selectors, pseudo-class selectors, attribute selectors, and property values.

---

## Development Workflow

This is a static HTML/CSS project. There is no build step.

### Viewing the project
Open `Midterm.html` directly in any modern browser. Because the stylesheet link is broken, styles will not load until the href is corrected.

### Editing
- Edit `Midterm.html` and `Midterm.css` directly with any text editor.
- No compilation, transpilation, or bundling is required.
- No dependencies to install.

### Testing
There is no automated test suite. Verification is manual:
- Open the file in a browser and inspect rendering.
- Use browser DevTools to check for CSS parse errors.
- Submit the form to verify HTML5 validation constraints fire correctly.

### Git workflow
The repository uses a single `master` branch for the main work. Feature/AI branches follow the pattern `claude/<description>-<id>`.

```bash
# Typical workflow
git checkout -b claude/<feature-name>
# make changes
git add <files>
git commit -m "Descriptive message"
git push -u origin claude/<feature-name>
```

---

## Code Conventions

### HTML
- HTML5 doctype, UTF-8 charset, viewport meta tag.
- Semantic elements: `<header>`, `<main>`, `<footer>`, `<form>`, `<fieldset>`, `<legend>`.
- Each input is wrapped in `<div class="form-group">` with an associated `<label for="...">`.
- Inline elements (radio buttons, checkboxes) use `<label class="inline">` wrapping the input directly.
- All required fields carry the `required` attribute; length constraints use `minlength`.

### CSS
- Comment-annotated sections for each selector type (element, class, ID, attribute, pseudo-class) — this is intentional for educational clarity.
- BEM-inspired flat class names: `.form-group`, `.btn`, `.inline`.
- Color palette: black (`#000`, `#333`), white (`#fff`), light gray background (`#f4f4f4`), border gray (`#ccc`, `#999`), focus blue (`dodgerblue`).
- No media queries; layout is constrained via `max-width: 600px` on `<main>`.

---

## AI Assistant Instructions

- **Do not auto-fix the CSS syntax errors** unless the user explicitly asks for a bug fix. They exist as part of the exam exercise.
- **Do not add JavaScript** unless explicitly requested.
- **Do not restructure the file layout** or rename files without being asked.
- When asked to fix the stylesheet link, change `href="styles.css"` → `href="Midterm.css"` in `Midterm.html:7`.
- Keep changes minimal and scoped to what is asked — this is a simple, intentionally constrained learning project.
- Commit messages should be short, imperative, and descriptive (e.g. `Fix stylesheet href reference`).
- Always push to the designated feature branch (pattern: `claude/<description>-<session-id>`), never directly to `master`.

---

## Branches

| Branch | Purpose |
|--------|---------|
| `master` | Student's submitted work |
| `claude/add-claude-documentation-U4Ew4` | AI documentation additions |
