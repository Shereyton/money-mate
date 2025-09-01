# Deployment (Private Repo, Public App)

This project is proprietary and the repository must remain private. The app itself should be publicly accessible via a host that only serves compiled build output (HTML/CSS/JS from `dist/`).

Below are two recommended approaches that do not expose your source repository.

## Option A: Netlify (Recommended)

- Works seamlessly with private GitHub repositories.
- Netlify pulls the repo privately, runs the build, and serves only the `dist/` folder.

Steps:
- Keep this GitHub repository private (Settings → General → Change visibility → Private).
- Ensure Node is installed locally (v18+ recommended).
- Install dependencies: `npm install`
- Local build (optional): `npm run build` → outputs to `dist/`.
- On Netlify:
  - New site → Import from Git → choose this private repo.
  - Build command: `npm run build`
  - Publish directory: `dist`
  - Deploy. Only compiled assets are public.

Notes:
- `netlify.toml` is included with the correct defaults (builds to `dist`).
- You can also deploy by dragging & dropping the `dist/` folder in Netlify UI.

## Option B: Vercel

- Also supports private repositories and builds server-side.

Steps:
- Create a new project on Vercel and connect the private GitHub repo.
- Framework Preset: “Other” or “Vite”.
- Build command: `npm run build`
- Output directory: `dist`

## Option C: GitHub Pages (Artifacts Only)

Avoid serving from the same repository that stores your source code unless your account/plan supports Pages from private repos and you understand the exposure risks. Safer pattern:

- Keep this repo private.
- Create a separate public repository, e.g. `money-mate-site`.
- From this private repo, push only the contents of `dist/` to the public repo (via CI or manual), never the source.
- Configure GitHub Pages on the public artifacts repo to serve from the default branch or `/docs` folder.

Example manual flow:
```
# In the private repo
npm run build

# Clone or add remote for the public artifacts repo
# Then copy ONLY the dist contents into that repo and push
```

## Preventing Source Exposure

- Do NOT enable GitHub Pages directly from the source branch of this repository unless it is private Pages with no source exposure.
- Always deploy from `dist/` only.
- Do not include build tooling (`node_modules`, config files) in any public artifacts repo.

## Local Development

- Start a dev server: `npm run dev`
- Build for production: `npm run build` (output in `dist/`)
- Preview production build: `npm run preview`

## Contact and Permissions

- All rights reserved. See `LICENSE`.
- No redistribution or resale without written permission.
- To request source access or modification rights, contact: Shereyton (add your preferred email or contact method).

