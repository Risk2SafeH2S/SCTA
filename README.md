<p align="center"><b>risk2Safe · Safety up. Risk down.</b></p>

# SCTA Studio

A simple web app for human factors **Safety Critical Task Analysis (SCTA)** in oil, gas and energy facilities. It walks you through the seven-step SCTA process one screen at a time. At each decision point in the process flowchart it asks you a Yes / No question and tells you what to do next.

Everything is in one file, **`index.html`**. There's no server, no database, no sign-in and nothing to install.

## How the app follows the process

| Phase | Steps | What you do | Decision points in the app |
|---|---|---|---|
| **Scope** (what matters) | 0 Start · 1 Hazards · 2 Tasks | Record the study details. List the major accident hazards (MAHs). Find the safety critical tasks and rank them by consequence × human involvement. | First SCTA on this site? (run a pilot) · Are the main hazards clear yet? · Do good HAZOP / bow tie studies exist? · Is the task list manageable? |
| **Analyse** (one task at a time) | 3 Understand · 4 Break down · 5 Failures | See how the task is really done: documents, interviews, walk-through. Break it into steps (HTA) and stop where probability × consequence is low. For each step ask "how could this go wrong?" using guidewords, and record the PIFs. | Is the HTA validated with an operator? · Is the failure credible? · Could it lead to a MAH? · More steps or failures to examine? |
| **Act** (reduce risk) | 6 Measures | Choose measures using the hierarchy of control, matched to the failure type. Decide Adopt or Reject for each against ALARP, with a reason, an owner and a due date. | Are nearly all measures retraining or procedures? (go back to Step 5) · Are violations widespread? (escalate) |
| **Learn** (improve) | 7 Review · Actions | Run the quality checks and look for signs of a weak study. Feed the results back, then pick the next task. | Any signs of a weak study? (fix that step) · More tasks to analyse? (back to Step 3) |

The coloured bar at the top always shows where you are. Click any step to jump to it. Loop-back buttons take you straight to the step the flowchart sends you back to.

## Using it

1. Open the app and click **+ New study**, or **Open the worked example** to see a finished study: gas blow-by from a separator to a bullet tank.
2. Work through the steps from left to right. Use **Next step →** at the bottom of each screen.
3. Your work **saves automatically** in your browser as you type.

### Outputs

| Button | What you get |
|---|---|
| **Report** | A full report with the logo, ready to **print or save as PDF** |
| **Excel** | A workbook with one sheet per step plus the action register |
| **Download** | The study file (`.scta.json`) to keep, share or bring back with **Open a study file…** |
| **Actions** → *Download as CSV* | The action register on its own |

### Where your data is kept

Studies are stored **only in the browser on the computer you're using**. Nothing is sent anywhere. To keep a study safe, or to move it to another computer:

- click **Download** to save the `.scta.json` file, and
- store that file somewhere safe. A good place is a `studies/` folder in this GitHub repository (**Add file → Upload files**), so GitHub keeps every version.

Clearing your browser data deletes the studies saved in that browser, so download a copy after each working session.

## Publish it on GitHub Pages (5 minutes)

1. Put **`index.html`** and this **`README.md`** in the root of your repository: **Add file → Upload files**, then **Commit changes**.
2. Open **Settings → Pages**.
3. Under *Build and deployment*, choose **Source: Deploy from a branch**, **Branch: `main`**, **Folder: `/ (root)`**, then **Save**.
4. After a minute or two, the page shows your app's address, for example `https://<your-account>.github.io/<repository>/`.

On a free GitHub plan, Pages needs the repository to be **public**. Your studies are not published, because they stay in each user's browser or in the files you choose to upload.

You can also just double-click `index.html` on your computer to use it without the internet.

## Updating the app

Upload a new `index.html` over the old one. Your saved studies are unaffected, because they live in the browser, not in the file.

## Note on the method

The steps, guidewords and performance influencing factors follow the Energy Institute's published approach to SCTA. They are paraphrased in plain language. The guidance itself is not reproduced here, so use your own licensed copy for the full method. The app supports the analysis and does not replace competent human factors judgement.

---
© risk2Safe. *Safety up. Risk down.*
