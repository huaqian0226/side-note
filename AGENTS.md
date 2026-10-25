# SideNote Personal Fork — Agent Rules

This is a personal fork of `mofukuru/side-note`.

## Development

- `main` follows upstream; integrated personal changes live on `my-features`.
- Edit TypeScript source, never the generated `main.js`. Use `npm ci`, `npm test`,
  `npx eslint src --ext .ts`, `npm run build`, and `node --check main.js`.
- Keep bug fixes and regression tests in focused commits. Prepare upstream PR branches from
  `upstream/main` and cherry-pick only relevant fixes; exclude personal release metadata and docs.
- The local parent project's `../AGENTS.md` owns cross-plugin workflow and the single Tracker.
  Do not add a child Tracker. Keep `AGENTS.md` and `CLAUDE.md` bodies identical apart from titles.
- Preserve the upstream MIT license and author. Keep fork additions and installation steps in
  both `README.md` and `README.zh-CN.md`.

## Releases and installation

- Personal versions use `<upstream-version>-hq.N`; release tags equal the manifest version.
- Keep source changes and release-version commits separate. Verify build, tests, release assets,
  and the actual tag before publishing within the user's authorization.
- Attach `main.js`, `manifest.json`, and `styles.css` to the GitHub Release. Use BRAT for the fork,
  give the user its repository and Release URLs, and verify the actual BRAT registration/version.
- The fork retains plugin ID `side-note`. Back up settings and comments before replacing a build.
  Never commit private vault data, settings, tokens, local installation paths, or generated bundles.
- Test lifecycle changes with a rendered table open, including disable -> enable. Use synthetic
  annotations to check content, highlighting, persistence, and Resolve without editing real notes.
- Publishing a personal release does not authorize an upstream PR or message.
