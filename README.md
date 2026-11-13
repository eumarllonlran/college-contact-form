# Contact Us — Horizonte College

A contact page for a fictional college, built with **vanilla HTML, CSS and JavaScript** (no frameworks). The project started as a front-end exercise to practice semantic markup, responsive styling and basic interactivity.

🔗 **Live demo:** https://eumarllonlran.github.io/college-contact-form/

## Features

- Form split into two sections: **About you** and **Your message**
- Native browser validation (required fields, email format, minimum length)
- Error messages shown only after the user interacts with a field, linked to it via `aria-describedby` for screen readers
- Profile selector styled as "chips" (Prospective student, Current student, etc.)
- Live character counter on the message field
- Automatic phone mask in Brazilian format: `(00) 00000-0000`
- Submit button switches to "Sending…" to prevent duplicate submissions
- Thank-you page that greets the user by name
- Responsive layout (works well on mobile)
- Automatic dark mode that follows the system theme
- Respects the "reduce motion" accessibility setting

## Tech stack

| Technology | Used for |
| --- | --- |
| HTML5 | Semantic structure and form validation |
| CSS3 | Custom properties, Grid, Flexbox, `clamp()`, media queries and pseudo-classes |
| JavaScript | Event handling, DOM manipulation and `sessionStorage` |
| Google Fonts | Fraunces (headings) and Inter (body text) |

## Project structure

```
.
├── index.html         # Contact form page
├── obrigado.html      # Page shown after submission
├── css/
│   └── estilos.css    # All styles
└── js/
    └── principal.js   # Character counter, phone mask and form submission
```

## Getting started

No installation needed:

1. Download or clone the repository
   ```bash
   git clone https://github.com/eumarllonlran/college-contact-form.git
   ```
2. Open `index.html` in your browser

> Tip: in VS Code, the **Live Server** extension reloads the page automatically on every change.

## What I learned

### HTML

- Structured the form with **semantic** tags: `<main>`, `<form>`, `<fieldset>` and `<legend>` to group related fields.
- Linked each `<label>` to its field with `for` and `id`, which improves accessibility and lets users click the label to focus the field.
- Grouped the profile chips in their own `<fieldset>` with a `<legend>`, the native way to label a group of radio buttons.
- Linked each error message to its field with `aria-describedby`, so screen readers announce it.
- Used the right input types (`email`, `tel`, `radio`, `checkbox`) and attributes such as `required`, `minlength`, `maxlength` and `autocomplete`, so the browser itself validates the data and helps the user.
- Learned the difference between using `<br>` for spacing and leaving spacing to CSS.

### CSS

- Organized colors and sizes in **CSS custom properties** (`:root`), so the theme can be changed by editing just a few values.
- Added **dark mode** with `prefers-color-scheme` by redefining only those variables, and disabled transitions with `prefers-reduced-motion`.
- Used `:is()` to apply one rule to several selectors and `clamp()` for a heading that scales with the screen size.
- Used **Grid** to place fields side by side and **Flexbox** to align labels, chips and the checkbox.
- Made the layout **responsive** with `@media`: on mobile, fields stack in a single column and the button spans the full width.
- Styled interaction states: `:hover`, `:focus-visible`, `:checked` and `:user-invalid`.
- Turned radio buttons into chips by visually hiding the input and styling the adjacent `<span>` with the `+` combinator.
- **A bug that taught me a lot:** I forgot a `;` and a `}` in one rule, and all the CSS below it stopped working. I learned to check that braces are properly closed and to pay attention to editor warnings.

### JavaScript

- Split the script into small, clearly named functions (`formatarTelefone`, `salvarNome`, `recuperarNome`, `configurarFormulario`, `configurarPaginaObrigado`), each with a single responsibility.
- Selected elements with `getElementById` and `form.elements`, and handled user actions with `addEventListener`.
- Built a **character counter** updated on the `input` event.
- Built a **phone mask** using a regular expression (`/\D/g`) to keep only digits before formatting them.
- On submit, called `event.preventDefault()`, disabled the button, saved the name to `sessionStorage` and redirected to the page set in the form's `action`.
- Used `try/catch` so the page keeps working even if the browser blocks storage.
- Learned to use **a single JS file across two pages** by checking that each element exists before using it.

## Next steps

- [ ] Send the data to a real backend or a form service (e.g., Formspree)
- [x] Add dark mode with `prefers-color-scheme`
- [x] Link error messages to fields with `aria-describedby`
- [x] Put the chip group in its own `<fieldset>`
- [ ] Add a button to manually toggle between light and dark themes

## Author

Built by **Marllon Lorran** — [LinkedIn](https://www.linkedin.com/in/eumarllonlran/) · [GitHub](https://github.com/eumarllonlran)
