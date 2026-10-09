# Copilot instructions

## Project overview

Orbit Academy is a standalone, client-side space quiz. The complete application lives in `index.html`: semantic page structure, responsive and theme-aware CSS, quiz question data, interaction logic, feedback, and results. There is no build pipeline or server; the page is opened directly in a browser.

The quiz is data-driven. Each entry in the `questions` array supplies a category, prompt, four options, the zero-based correct option index, and an explanatory fact. `renderQuestion()` updates the current question and resets its answer state; `selectAnswer()` locks the choices, updates the score and progress, and shows feedback; `showResults()` selects the end-of-quiz reaction. The replay handler resets state and renders the first question.

## Commands and checks

There are no package manifest, build, test, or lint configuration files, so the repository defines no build, test, lint, or single-test commands. No dependencies need installing. Open `index.html` directly in a browser to exercise the quiz.

## Project conventions

- Keep the app dependency-free and self-contained in `index.html`; preserve direct `file://` use and avoid relying on a server, network requests, or external assets.
- Keep quiz content in the `questions` array and follow its existing object shape. Update the question count through `questions.length` rather than duplicating a fixed total in application logic.
- Keep state changes in the existing quiz flow (`renderQuestion`, `selectAnswer`, `showResults`, and the event handlers) so score, progress, feedback, and replay remain in sync.
- Use the existing CSS custom properties for colors and surfaces, with corresponding `prefers-color-scheme: dark` values. Keep layout changes responsive and honor `prefers-reduced-motion`.
- Preserve semantic buttons and the existing live announcements, keyboard focus behavior, and visible focus styles when changing quiz interactions.
