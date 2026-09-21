# OvalOasis Website Render Fix — 2026-09-21

## Symptom
The live marketing website rendered the fixed header/navigation but the entire page body appeared blank.

## Root cause
The marketing page uses `.reveal` on the main content. The stylesheet originally set every `.reveal` element to `opacity: 0` by default, while JavaScript was responsible for adding `.visible` through `IntersectionObserver`.

If `script.js` failed to load/execute, or the observer was unavailable, the page content remained permanently invisible. The screenshot matched this failure mode exactly: the header rendered, while all `.reveal` content was blank.

## Fix
- `.reveal` is now visible by default.
- The hidden/animated state is enabled only after a working `IntersectionObserver` is initialized via `html.reveal-ready`.
- If `IntersectionObserver` is unavailable, all `.reveal` elements are explicitly made visible.
- Existing reveal animations and page design are preserved when JavaScript works normally.

## Changed files
- `website/styles.css`
- `website/script.js`

No website content/design assets were replaced or reconstructed.
