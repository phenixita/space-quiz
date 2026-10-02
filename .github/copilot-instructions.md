# Repository instructions

## Build and verification

- The app is the self-contained `index.html`; open it directly in a browser. No installation, server, build, or external dependency is needed.
- There is no configured package manager, build command, test runner, or linter in this repository, so there is no single-test command.
- For a browser smoke check, use the integrated browser to complete all 10 questions with Tab and Enter. Verify the score and progress update, correct and incorrect answers show their respective feedback, and the results screen reports the final score. Check both light and dark themes and reduced-motion behavior when changing styles or animations.

## Architecture

- `PRODUCT.md` is the product brief: audience, purpose, and functional and visual constraints. Keep the implementation aligned with it.
- `index.html` is the complete application. Its inline CSS defines the design tokens, responsive layout, visual themes, focus states, and animations; its inline JavaScript owns the question data and quiz lifecycle. Keep the app self-contained when changing it.
- The question data drives each rendered question, feedback explanation, score, and results stamps. `renderQuestion`, `selectAnswer`, `advance`, and `renderResults` handle the transition from question to answer feedback to results.

## Project conventions

- Keep each question in the `questions` array with four answer strings, a zero-based `answer` index, a short `hint`, and an explanatory `fact`. Keep the answer index within the four options.
- Render answer choices and primary actions as native buttons. Preserve the quiz's accessible question heading, announced feedback and score, progress-bar value, and programmatic focus movement when re-rendering a question or showing results.
- Theme colors come from CSS custom properties. Light and dark palettes are defined separately; check both when changing shared UI colors.
- Honor `prefers-reduced-motion` for decorative and feedback animation. Keep reduced-motion behavior and visible keyboard focus intact when adding transitions or interactive controls.
- Keep styling and script inline in `index.html`; do not introduce network-loaded fonts, scripts, stylesheets, or other runtime dependencies.
