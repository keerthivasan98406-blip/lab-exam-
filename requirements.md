# Requirements Document: Lab Exam Reference Website

## Introduction

This document defines the requirements for a static, single-page lab exam reference website. The site displays 10 code snippet cards, each with a heading, a code block, and a copy-to-clipboard button. It is built with plain HTML, CSS, and JavaScript — no frameworks or external dependencies.

---

## Requirements

### Requirement 1: Single-File Static Website

**User Story**: As a student, I want to open a single HTML file in my browser and immediately see all reference code, so that I don't need a server or internet connection during a lab exam.

**Acceptance Criteria**:

- 1.1 The entire website MUST be contained in a single `index.html` file.
- 1.2 All CSS MUST be embedded in a `<style>` tag within the HTML file.
- 1.3 All JavaScript MUST be embedded in a `<script>` tag within the HTML file.
- 1.4 The file MUST NOT reference any external stylesheets, scripts, fonts, or images.
- 1.5 The file MUST open and render correctly when opened directly in a browser via `file://` protocol.

---

### Requirement 2: Ten Code Cards

**User Story**: As a student, I want to see 10 separate code reference cards on the page, so that I can quickly find the snippet I need.

**Acceptance Criteria**:

- 2.1 The page MUST display exactly 10 cards.
- 2.2 Each card MUST be visually distinct and contained within its own box/container.
- 2.3 Each card MUST have a top heading that describes the code snippet.
- 2.4 Each card MUST contain a code block that displays the code snippet.
- 2.5 The cards MUST be arranged in a grid or column layout that is easy to scan.

---

### Requirement 3: Code Block Display

**User Story**: As a student, I want the code in each card to be clearly readable with preserved formatting, so that I can read and understand it at a glance.

**Acceptance Criteria**:

- 3.1 Each code block MUST use a monospace font (e.g., `monospace`, `Courier New`, or `Consolas`).
- 3.2 Each code block MUST preserve whitespace and indentation exactly as authored.
- 3.3 Each code block MUST be wrapped in `<pre><code>` tags.
- 3.4 If the code is wider than the card, the code block MUST scroll horizontally rather than wrapping.
- 3.5 The code block MUST have a visually distinct background (e.g., light grey) to differentiate it from the card background.

---

### Requirement 4: Copy Button

**User Story**: As a student, I want to click a "Copy" button on each card to copy the code to my clipboard, so that I can paste it directly into my editor without retyping.

**Acceptance Criteria**:

- 4.1 Each card MUST have exactly one "Copy" button.
- 4.2 The button MUST be labeled "Copy" by default.
- 4.3 Clicking the button MUST copy the full text content of that card's code block to the system clipboard.
- 4.4 After a successful copy, the button label MUST change to "Copied!" to confirm the action.
- 4.5 The button label MUST revert to "Copy" after 2 seconds.
- 4.6 Clicking the copy button on one card MUST NOT affect the state of any other card's button.
- 4.7 The copy operation MUST use `navigator.clipboard.writeText()`.
- 4.8 If the clipboard API is unavailable, the failure MUST be handled gracefully (no unhandled errors, no broken UI).

---

### Requirement 5: Clean and Minimal Design

**User Story**: As a student, I want the page to look clean and simple, so that it is easy to read under exam conditions without visual distractions.

**Acceptance Criteria**:

- 5.1 The design MUST use a neutral color palette (white, light grey, dark grey/black text).
- 5.2 The design MUST NOT use decorative gradients, shadows, animations, or ornamental styling.
- 5.3 Each card MUST have a visible border or background contrast to separate it from the page background.
- 5.4 The page MUST have a simple header displaying the site title.
- 5.5 Font sizes MUST be readable at standard screen resolution (minimum 14px for body text, 16px+ for headings).
- 5.6 The layout MUST be usable on a standard laptop screen (1280px wide) without horizontal scrolling of the page itself.

---

### Requirement 6: No Framework Dependencies

**User Story**: As a student, I want the site to work without any build tools or package managers, so that I can use it on any computer without setup.

**Acceptance Criteria**:

- 6.1 The implementation MUST use only plain HTML5, CSS3, and vanilla JavaScript.
- 6.2 The implementation MUST NOT use any JavaScript frameworks (React, Vue, Angular, etc.).
- 6.3 The implementation MUST NOT use any CSS frameworks (Bootstrap, Tailwind, etc.).
- 6.4 The implementation MUST NOT require Node.js, npm, or any build step to run.
