# Contact Us — Horizon College

A contact page for a fictional college, built with **vanilla HTML, CSS, and JavaScript** (no frameworks). The project started as a front-end exercise to practice semantic markup, responsive styling, and basic interactivity.

🔗 **Live demo:** https://eumarllonln.github.io/college-contact-form/

## Features

- Form split into two sections: **About you** and **Your message**
- Native browser validation (required fields, email format, minimum length)
- Error messages shown only after the user interacts with a field, linked to it via `aria-describedby` for screen readers
- Chip-style profile selector (Prospective student, Current student, etc.)
- Real-time character counter for the message field
- Automatic phone input mask in Brazilian format: `(00) 00000-0000`
- Submit button switches to "Sending…" to prevent duplicate submissions
- Thank-you page that greets the user by name
- Responsive layout (mobile-friendly)
- Automatic dark mode that follows the system theme
- Honors the "reduce motion" accessibility setting

## Tech Stack

| Technology | Used for |
| --- | --- |
| HTML5 | Semantic structure and form validation |
| CSS3 | Custom properties, Grid, Flexbox, `clamp()`, media queries, and pseudo-classes |
| JavaScript | Event handling, DOM manipulation, and `sessionStorage` |
| Google Fonts | Fraunces (headings) and Inter (body text) |

## Project Structure

```
.
├── index.html       # Contact form page
├── thank-you.html   # Page shown after submission
├── css/
│   └── styles.css   # All styles
└── js/
    └── main.js      # Character counter, phone mask, and submission
```

## Getting Started

No installation required:

1. Download or clone the repository
   ```bash
   git clone https://github.com/eumarllonln/college-contact-form.git
   ```
2. Open `index.html` in your browser

> Tip: in VS Code, the **Live Server** extension automatically reloads the page on every change.

## What I Learned

### HTML

- Structured the form with **semantic** tags: `<main>`, `<form>`, `<fieldset>`, and `<legend>` to group related fields.
- Associated each `<label>` with its field using `for` and `id`, which improves accessibility and lets users click the label text to focus the field.
- Grouped the profile chips in their own `<fieldset>` with a `<legend>`, the native way to label a group of radio buttons.
- Linked each error message to its field with `aria-describedby` so screen readers announce it.
- Used the appropriate input types (`email`, `tel`, `radio`, `checkbox`) and attributes such as `required`, `minlength`, `maxlength`, and `autocomplete`, so the browser itself validates input and assists the user.
- Learned the difference between using `<br>` for spacing and leaving spacing to CSS.

### CSS

- Organized colors and sizes into **CSS custom properties** (`:root`), so the theme can be changed by editing just a few values.
- Added **dark mode** with `prefers-color-scheme` by redefining only those variables, and disabled transitions with `prefers-reduced-motion`.
- Used `:is()` to share a rule across multiple selectors and `clamp()` for a heading that scales with the viewport.
- Used **Grid** to place fields side by side and **Flexbox** to align labels, chips, and the checkbox.
- Made the layout **responsive** with `@media`: on mobile, fields stack into a single column and the button spans the full width.
- Styled interaction states: `:hover`, `:focus-visible`, `:checked`, and `:user-invalid`.
- Turned radio buttons into chips by visually hiding the input and styling the adjacent `<span>` with the `+` combinator.
- **A bug that taught me a lot:** I left out a `;` and a `}` in one rule, and all the CSS below it stopped working. I learned to check that braces are properly closed and to pay attention to editor warnings.

### JavaScript

- Split the script into small, clearly named functions (`formatPhone`, `saveName`, `retrieveName`, `setupContactForm`, `setupThankYouPage`) so each one has a single responsibility.
- Selected elements with `getElementById` and `form.elements`, and handled user actions with `addEventListener`.
- Built a **character counter** updated on the `input` event.
- Built a **phone mask** using a regular expression (`/\D/g`) to keep only digits before formatting them.
- On submit, called `event.preventDefault()`, disabled the button, stored the name in `sessionStorage`, and redirected to the page set in the form's `action`.
- Used `try/catch` so the page keeps working even if the browser blocks storage.
- Learned to use **a single JS file across two pages** by checking that each element exists before using it.

## Roadmap

- [ ] Submit the data to a real back end or form service (e.g., Formspree)
- [x] Add dark mode with `prefers-color-scheme`
- [x] Link error messages to fields with `aria-describedby`
- [x] Move the chip group into its own `<fieldset>`
- [ ] Add a button to manually toggle between light and dark themes

## Author

Built by **Marllon Lorran** — [LinkedIn](https://www.linkedin.com/in/eumarllonln/) · [GitHub](https://github.com/eumarllonln)
