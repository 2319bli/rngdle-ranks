# RNGdle Rank Explorer

An independent calculator for RNGdle's 5 October 2026 scoring snapshot. Search all **1,000,001 numbers (0–1,000,000)** by number, exact EP score, or rank.

- Exact ranks, including ties and occupied positions within ties.
- All matching numbers for an EP score, paginated in groups of 100.
- Badge breakdowns and contributing-digit highlights.
- Light and dark themes using the supplied RNGdle styling.
- Inter and Space Mono loaded through Google Fonts.

## Publish on GitHub Pages

1. Create a GitHub repository with `main` as its default branch.
2. Upload **the contents of this folder** to the repository root, so `index.html` is at the top level. Include `.github/workflows/pages.yml`. On macOS, press **Command–Shift–.** in Finder to show hidden files and folders.
3. In the repository, open **Settings → Pages → Build and deployment → Source** and select **GitHub Actions**.
4. Open **Actions → Deploy to GitHub Pages → Run workflow**. Subsequent pushes to `main` deploy automatically.
5. Once the workflow succeeds, the deployment link appears under **Settings → Pages** and in the workflow's deployment summary.

No npm installation, build command, API key, or Sites account is needed. Relative asset paths support both `username.github.io` and `username.github.io/repository-name/` hosting.

Alternative: choose **Deploy from a branch**, then `main` and `/(root)` in Pages settings. Remove `.github/workflows/pages.yml` if you use that method.

## Open locally

Open `index.html` in a browser, keeping `assets/` beside it. The calculator itself needs no network connection; Google Fonts requires internet access and falls back to local fonts if unavailable.

## Files

| File | Purpose |
| --- | --- |
| `index.html` | Page structure and controls |
| `assets/styles.css` | Supplied RNGdle CSS and calculator-specific layout |
| `assets/scoring-engine.js` | Scoring snapshot supplied from RNGdle |
| `assets/app.js` | Search, badge rendering, exact score distribution and reverse lookup |
| `favicon.svg` | Calculator icon |
| `.github/workflows/pages.yml` | Automatic Pages deployment |

The large JavaScript file contains a precomputed reverse lookup for every number, keeping searches instant without a backend. Keep the score distribution, reverse lookup and scoring engine together when updating the scoring snapshot.

## Rank definition

**Rank = 1 + the number of numbers with a strictly higher EP score.** Equal scores share a rank. If a group occupies positions 10–12, searching 11 returns that group and shows its shared rank of 10. EP searches require an exact integer score.

## Source attribution

This is an unofficial tool, not affiliated with RNGdle. The scoring engine and base styles originate from user-supplied RNGdle JavaScript and CSS; the layout was adapted from user-supplied page HTML. This package does not assign a new licence to those third-party materials. The data is a fixed snapshot, not a live connection to RNGdle.

GitHub Pages workflow reference: https://docs.github.com/en/pages/getting-started-with-github-pages/using-custom-workflows-with-github-pages
