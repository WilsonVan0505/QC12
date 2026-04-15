# Vibe: GitHub Pages Deployment

This skill sets the standard for any web development intended to be hosted via GitHub Pages from the repository root.

## Rules for GitHub Pages

1. **Root Deployment**:
   Assume the static application is deployed from the `[repository]/root` directory.

2. **Relative Pathing**:
   - Always use relative paths for internal assets (e.g., `./css/style.css`, `../image/picture.png`, `./js/app.js`).
   - Do NOT use absolute paths that start with `/` for local assets, as GitHub Pages often deploys under `https://<username>.github.io/<repository-name>/`. An absolute path would incorrectly target the root of `github.io`.
   - Asset loading must be resilient and dynamic where needed, taking into account depth from the project root.

3. **CORS and Fetch APIs**:
   - If utilizing `fetch()` to load local JSON files, write defensive code to handle network errors smoothly.
   - Using relative paths in `fetch()` works smoothly on GitHub Pages environments.

4. **SEO and Performance**:
   - Pages must include standard semantic `<head>` tags (charset, viewport).
   - Scripts should generally be deferred (`defer`) and load at the bottom of the body.
