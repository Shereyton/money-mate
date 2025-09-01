# money-mate

A professional financial tracker app that lets you input income and expenses, automatically calculates savings and disposable income, and displays live interactive charts and graphs.

Now includes support for entering either a single monthly income or individual paycheck amounts. When paychecks are entered, the app automatically totals them, estimates monthly earnings, and projects yearly income.

**License & Permissions**
- License: All rights reserved (proprietary). See `LICENSE`.
- No redistribution or resale without written permission.
- Source usage/modifications require explicit approval. Contact the author.

**Public Access vs. Private Code**
- Repo: Keep this GitHub repository private.
- Deploy: Publish only the compiled site (the `dist/` folder) so users can access the app, not the raw source.
- Recommended host: Netlify with a private repo connection (builds from `main`, serves `dist/`).

**Deploy (Quick)**
1. Ensure the repo is private in GitHub: Settings → General → Danger Zone → Change visibility → Private.
2. Install dependencies locally: `npm install`.
3. Build: `npm run build` (outputs to `dist/`).
4. Netlify: Create a new site from Git, choose this private repo, set Build command `npm run build`, Publish directory `dist/`.
   - Alternative: Manually upload the `dist/` folder to Netlify.

For detailed options (Netlify, Vercel, or GitHub Pages via a separate public artifacts repo), see `DEPLOYMENT.md`.
