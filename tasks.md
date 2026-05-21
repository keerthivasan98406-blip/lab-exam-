# Tasks: Lab Exam Reference Website

## Task List

- [ ] 1. Create the HTML skeleton
  - Create `index.html` with `<!DOCTYPE html>`, `<html>`, `<head>`, and `<body>` tags
  - Add `<meta charset="UTF-8">` and `<meta name="viewport">` tags
  - Add `<title>Lab Exam Reference</title>`
  - Add empty `<style>` block in `<head>`
  - Add a `<header>` with the page title inside `<body>`
  - Add a `<main class="grid">` container inside `<body>`
  - Add empty `<script>` block before `</body>`
  - _Requirements: 1.1, 1.2, 1.3, 5.4_

- [ ] 2. Add the 10 code cards to the HTML
  - Inside `<main class="grid">`, add 10 `<div class="card">` elements
  - Each card must contain: `<h2 class="card-title">`, `<div class="code-wrapper">`, `<pre><code class="code-block">`, and `<button class="copy-btn" onclick="copyCode(this)">Copy</button>`
  - Fill each card with a meaningful heading and a relevant code snippet (e.g., Hello World, for loop, function, array, string operations, etc.)
  - Use HTML entities (`&lt;`, `&gt;`) where needed inside `<code>` blocks
  - _Requirements: 2.1, 2.2, 2.3, 2.4, 3.3_

- [ ] 3. Write the CSS styles
  - Inside the `<style>` block, add a CSS reset (`* { box-sizing: border-box; margin: 0; padding: 0; }`)
  - Style `body`: white background, dark text, readable font, padding
  - Style `header`: simple title, bottom border or margin
  - Style `.grid`: CSS grid layout (`grid-template-columns: repeat(auto-fill, minmax(340px, 1fr))`), gap between cards
  - Style `.card`: white or light background, 1px solid border, padding, border-radius (subtle)
  - Style `.card-title`: bold, readable font size (18px+), bottom margin
  - Style `.code-wrapper`: position relative (to allow absolute button positioning)
  - Style `pre` and `code`: monospace font, light grey background, padding, `overflow-x: auto`, font size 13–14px
  - Style `.copy-btn`: small button, positioned top-right of code wrapper, neutral colors, cursor pointer
  - Style `.copy-btn.copied`: green text or background to indicate success
  - _Requirements: 3.1, 3.2, 3.4, 3.5, 5.1, 5.2, 5.3, 5.5, 5.6_

- [ ] 4. Write the JavaScript copy handler
  - Inside the `<script>` block, define `async function copyCode(btn)`
  - Get the `<code>` element: `const code = btn.parentElement.querySelector('code')`
  - Get the text: `const text = code.innerText`
  - Call `await navigator.clipboard.writeText(text)` inside a `try/catch`
  - On success: set `btn.textContent = 'Copied!'`, add class `copied`
  - After 2000ms via `setTimeout`: reset `btn.textContent = 'Copy'`, remove class `copied`
  - In `catch`: silently ignore the error (no UI change)
  - _Requirements: 4.1, 4.2, 4.3, 4.4, 4.5, 4.6, 4.7, 4.8_

- [ ] 5. Verify and test the complete page
  - Open `index.html` in a browser and confirm all 10 cards render
  - Confirm each card has a heading, code block, and Copy button
  - Click each Copy button and paste into a text editor to verify the copied text matches the code block exactly
  - Confirm the button shows "Copied!" then reverts to "Copy" after 2 seconds
  - Confirm clicking one card's button does not affect other cards
  - Confirm no console errors appear on load or on button click
  - Confirm the layout is readable at 1280px width
  - _Requirements: 2.1–2.5, 3.1–3.5, 4.1–4.8, 5.1–5.6, 6.1–6.4_
