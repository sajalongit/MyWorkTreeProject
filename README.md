# MyWorkTreeProject

A React application scaffolded with [Vite](https://vite.dev/).

## Prerequisites

| Tool | Version | Check with |
| --- | --- | --- |
| Node.js | 20.19+ or 22.12+ | `node --version` |
| npm | 10+ (ships with Node) | `npm --version` |

Install Node.js from [nodejs.org](https://nodejs.org/) or via a version manager such as
[nvm](https://github.com/nvm-sh/nvm) (macOS/Linux) or [nvm-windows](https://github.com/coreybutler/nvm-windows).

## First-time setup

If the React app has not been created yet, scaffold it into this directory:

```bash
npm create vite@latest . -- --template react
```

Use `--template react-ts` instead if you want TypeScript.

Then install the dependencies:

```bash
npm install
```

If you cloned a repo that already has a `package.json`, skip the scaffold step and just run
`npm install`. For a clean, lockfile-exact install (CI or a fresh machine), use:

```bash
npm ci
```

## Running the app

Start the development server with hot module reload:

```bash
npm run dev
```

Vite prints the local URL — by default <http://localhost:5173>. The page reloads automatically as
you edit files under `src/`.

To expose the dev server to other devices on your network:

```bash
npm run dev -- --host
```

To run on a different port:

```bash
npm run dev -- --port 3000
```

## Available scripts

| Command | What it does |
| --- | --- |
| `npm run dev` | Start the dev server with hot reload |
| `npm run build` | Produce an optimized production build in `dist/` |
| `npm run preview` | Serve the built `dist/` locally to verify the production bundle |
| `npm run lint` | Run ESLint across the project (if configured) |

## Production build

```bash
npm run build
```

The output lands in `dist/`. Preview it before deploying:

```bash
npm run preview
```

## Project structure

```
.
├── index.html          # Entry HTML; Vite injects the bundle here
├── package.json        # Dependencies and scripts
├── vite.config.js      # Vite configuration
├── public/             # Static assets copied verbatim into dist/
└── src/
    ├── main.jsx        # App bootstrap — mounts <App /> into the DOM
    ├── App.jsx         # Root component
    └── assets/         # Images and other imported assets
```

## Environment variables

Create a `.env` file in the project root. Vite only exposes variables prefixed with `VITE_` to
client code:

```
VITE_API_URL=https://api.example.com
```

Read them in your components via `import.meta.env.VITE_API_URL`. Do not put secrets in these
variables — anything prefixed with `VITE_` is bundled into the shipped JavaScript and is visible to
anyone using the app. Keep `.env` files out of version control.

## Troubleshooting

**`npm` or `node` is not recognized** — Node.js is not installed or not on your `PATH`. Reinstall
from nodejs.org and open a new terminal.

**Port 5173 is already in use** — another dev server is running. Stop it, or pass
`--port <number>` as shown above.

**Blank page after `npm run dev`** — open the browser console. A missing `<div id="root">` in
`index.html`, or a mismatch with the id used in `src/main.jsx`, is the usual cause.

**Stale or broken dependencies** — delete and reinstall:

```bash
rm -rf node_modules package-lock.json && npm install
```

On Windows PowerShell:

```bash
Remove-Item -Recurse -Force node_modules, package-lock.json; npm install
```

**Changes not appearing** — hard-refresh the browser (`Ctrl+Shift+R`, or `Cmd+Shift+R` on macOS),
then restart the dev server.
