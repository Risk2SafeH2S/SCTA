# SCTA
# SCTA 2.0

A web app for human factors **Safety Critical Task Analysis (SCTA)** in oil, gas and energy facilities. It follows the seven-step approach in the Energy Institute guidance.

It runs entirely on GitHub:

- **The app** is a static site served free by **GitHub Pages** from the `docs/` folder of this repository.
- **Your studies** are saved as files in a **private GitHub repository** that you own, for example `scta-studies`. Every save is a commit, so the repository history is a complete revision history.

You don't need a server, a database or any account besides GitHub.

## What it does

| | |
|---|---|
| **Start from the MAH** | *New study* asks for the major accident hazard first (reference, source document, worst credible outcome, how it happens), then takes you to Step 2. |
| **Seven steps** | 1 Major hazards · 2 Safety critical tasks with priority screening · 3 Task evidence · 4 Task breakdown (HTA) · 5 Human failures with guidewords and performance influencing factors · 6 Safety measures against the hierarchy of control, with an ALARP decision and reason for each · 7 Review with quality checks and automatic gap finding. |
| **Saved to GitHub** | Changes save automatically a few seconds after you stop typing, or straight away with *Save now*. If the same study is saved from two places, you're asked which version to keep. |
| **Revisions** | Save a named revision (for example "Rev A issued for review"). The *Study setup* page lists every saved version, and you can restore any of them. Restoring is itself a new save, so nothing is lost. |
| **Outputs** | An Excel workbook of the whole study (one sheet per step plus the action register), the study file (`.scta.json`), CSV worksheet and action register, and a print / PDF report. |
| **Examples** | Separator gas blow-by to bullet tank (HAZOP-derived) and sand erosion on a gas-lifted well. |

Study files from the original single-file SCTA Workbench can be imported unchanged.

## Set up (one time, about 10 minutes)

### 1. Publish the app with GitHub Pages

The repository root holds **`index.html`**, a single self-contained file with the whole app in it (styles, scripts, Excel library and worked example). You can upload just that file to any GitHub repository and publish it with Pages from the root folder, or open it straight from your computer. It is rebuilt from `docs/` with `npm run build:single`.

Using this repository:
1. In this repository, open **Settings → Pages**.
2. Under *Build and deployment*, choose **Source: Deploy from a branch**, **Branch: `main`**, **Folder: `/ (root)`** (the single `index.html`) or **`/docs`** (the same app as separate files), then **Save**.
3. After a minute, the page shows your app's address, for example `https://risk2safeh2s.github.io/SCTA---2.0/`.

### 2. Create the private studies repository
1. On GitHub, click **New repository**.
2. Name it, for example, `scta-studies`, and set it to **Private**. Tick *Add a README* so the repository isn't empty.
3. Click **Create repository**.

### 3. Create an access token for the app
1. Go to GitHub **Settings → Developer settings → Personal access tokens → Fine-grained tokens → Generate new token**.
2. Fill in the token:
   - **Expiration:** your choice. 90 days is a sensible default, and you create a new token when it expires.
   - **Repository access:** *Only select repositories*, then choose `scta-studies`.
   - **Permissions:** under *Repository permissions*, set **Contents** to **Read and write**. Leave everything else as it is.
3. Click **Generate token** and copy it.

### 4. Connect
Open the app and enter the repository as `owner/scta-studies`, for example `Risk2SafeH2S/scta-studies`. Paste the token and click **Connect**.

The token is kept only in your browser and is only ever sent to GitHub. On a shared computer, untick *Remember on this computer*. Use the **GitHub** button in the app to disconnect.

### Working as a team
1. Add colleagues as collaborators on the private `scta-studies` repository.
2. Each colleague creates their own token and connects with it.
3. The history then shows who saved each version.

## Develop and test

The app is plain HTML, CSS and JavaScript in `docs/`, with no build step. To try it locally, serve the folder with any static server, for example `npx serve docs`.

```bash
npm install
npm test     # end-to-end browser test against a simulated GitHub API (needs Playwright + Chromium)
```

## Project layout

```
docs/index.html     page structure
docs/app.js         the seven SCTA steps (from the SCTA Workbench)
docs/github.js      connection, study list, saving and history in the GitHub repository
docs/export.js      Excel export (uses docs/vendor/exceljs.min.js, MIT licence)
test/ui.test.js     end-to-end test
```

## Note on the method

The step structure, guidewords and influencing factors are paraphrased in plain language. The Energy Institute guidance itself is not reproduced here; use your own licensed copy for the full method.
