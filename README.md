# PhotoEditor

A browser-based image editor built with React, TypeScript, and [OpenCV.js](https://docs.opencv.org/4.x/d5/d10/tutorial_js_root.html). Load an image, apply pixel-level transformations, and save the result — all client-side, no server or install required.

**Live demo:** https://luci-dot-exe.github.io/photo-editor/

This project started as coursework for INF01046 – Fundamentos de Processamento de Imagens (UFRGS), implementing classic image-processing operations from scratch on top of OpenCV.js instead of the traditionally-recommended C/C++. Implementation notes and rationale for that choice are in [relatórios/parte 1/relatorio.md](<relatórios/parte 1/relatorio.md>).

## Features

- **Load / save images** — read a JPEG (or other browser-supported format) from disk and download the edited result.
- **Vertical & horizontal mirroring** — flip the image along either axis.
- **Grayscale conversion** — convert to luminance (`L = 0.299R + 0.587G + 0.114B`).
- **Shade quantization** — reduce a grayscale image to a chosen number of tonal levels (2–256).

## Tech stack

- [React](https://reactjs.org/) + [TypeScript](https://www.typescriptlang.org/), bootstrapped with [Create React App](https://github.com/facebook/create-react-app)
- [OpenCV.js](https://docs.opencv.org/4.x/d5/d10/tutorial_js_root.html) (via `opencv-ts`) for image I/O and pixel access
- [Bootstrap](https://getbootstrap.com/) + [Font Awesome](https://fontawesome.com/) for the UI

## Getting started

Install dependencies and start the dev server:

```bash
yarn install
yarn start
```

Open [http://localhost:3000](http://localhost:3000) — the page reloads on edits.

### Other scripts

| Command | Description |
| --- | --- |
| `yarn test` | Run the test suite in watch mode |
| `yarn build` | Build a production bundle to `build/` |
| `yarn deploy` | Build and publish `build/` to GitHub Pages |

## Deployment

The app is a static site deployed to GitHub Pages via [`gh-pages`](https://github.com/tschaub/gh-pages):

```bash
yarn deploy
```

This runs `predeploy` (`yarn build`) automatically, then pushes the `build/` folder to the `gh-pages` branch, publishing to the `homepage` URL configured in `package.json`.
