# Tools by Dr. Prashant Patel

Browser-based tools for pharmaceutical professionals — built from real workflow frustration, running entirely offline, with no uploads and no accounts.

**[praxdocs](https://drprash.github.io/tools/praxdocs.html)** · **[pdfCompare](https://drprash.github.io/tools/pdfCompare.html)** · **[HighLit AI](https://drprash.github.io/tools/HighLit_AI.html)** · **[HighLit](https://drprash.github.io/tools/HighLit.html)** · **[FOCUS](https://drprash.github.io/tools/FOCUS.html)**

---

## Why these exist

I spent 9+ years in pharmacovigilance, regulatory affairs, and medical affairs working with dense PDFs every day — clinical study reports, SmPCs, patient information leaflets, regulatory submissions. The tools I needed either didn't exist, cost too much to justify, or required uploading confidential documents to a third-party server.

So I taught myself to build them.

These are not products. They are solutions to specific frustrations I had at work, released publicly on the chance they solve the same frustrations for someone else.

---

## Philosophy

**Privacy by default.** Regulatory and clinical documents are sensitive. A tool that uploads your files to process them is a liability, not a tool. Everything here runs locally in your browser tab. Nothing leaves your device.

**No install friction.** The best tool is the one people actually use. A URL you can bookmark beats software that needs IT approval, a licence key, or a two-hour onboarding session.

**Domain expertise first.** The features aren't invented — they're extracted from real work. PDF Compare reads two-column layouts because I've compared hundreds of SmPCs. FOCUS has a priority matrix because pharma demands you know, before 9am, exactly what must ship today.

---

## Tools

### PraxDocs — PDF Manipulation Suite

A complete offline PDF toolkit. Open `praxdocs.html` in your browser.

**What it does:**
- **Merge** — combine multiple PDFs into one; select specific pages from each
- **Stamp / Watermark** — overlay a PDF (e.g. a "DRAFT" stamp or a company logo) onto another
- **Rotate** — rotate pages individually or in bulk
- **Convert to JPEG** — export individual pages as images
- **Compress** — reduce file size with selectable quality presets

**How to use:**

1. Open `praxdocs.html` in Chrome or Edge
2. Select a tool from the sidebar
3. Drag and drop your PDF files into the file area, or click to browse
4. Configure options (page ranges, quality, etc.) and click the action button
5. The processed file downloads automatically — nothing is stored anywhere

All processing happens in-browser using [pdf-lib](https://pdf-lib.js.org/) and [PDF.js](https://mozilla.github.io/pdf.js/). No server involved.

---

### PDF Compare — Column-Aware Document Diff

A diff tool built specifically for pharmaceutical documents. Open `pdfCompare.html` in your browser.

**What it does:**
- Extracts text from two PDFs and compares them side-by-side or in a unified view
- **Auto-detects two-column layouts** — reads the left column fully before the right, which is critical for SmPCs and patient leaflets that use multi-column formatting (most generic diff tools get this wrong)
- Three diff granularities: line, word, and character level
- Similarity score gives a quick read on how much has changed
- Myers diff algorithm — fast even on large regulatory documents

**How to use:**

1. Open `pdfCompare.html` in your browser
2. Drop your original document into the left panel and the revised document into the right
3. Choose your diff granularity (word-level is usually the most readable)
4. Click **Compare** — additions are highlighted green, deletions red
5. Toggle between unified and side-by-side views as needed
6. Use **Reset** to start a new comparison

> **Tip for SmPCs and PIL comparisons:** If your document uses a two-column layout, make sure the auto-detect is working — the column order matters for a meaningful comparison.

---

### HighLit AI — AI-Assisted Safety Literature Analyser

An AI-powered analyser for pharmacovigilance and medical affairs literature review. Open `HighLit_AI.html` in your browser.

Built for situations where keyword scanning isn't enough — when you need to understand context, extract structured safety signals, or produce PBRER-ready narratives from a stack of abstracts.

**What it does:**
- **Smart Highlight** — AI reads your abstracts and colour-codes safety signals by type without pre-defined keyword lists
- **Signal Extraction** — returns a structured list of PV signals with severity classification (red / amber / green) and the source text
- **PBRER Summary** — generates a narrative paragraph suitable for dropping into a PSUR or PBRER literature section
- **Imputability** — structured causality assessment applied to the submitted text

**How to use:**

1. Open `HighLit_AI.html` in your browser
2. Select your AI provider (Anthropic, OpenAI, Gemini, or OpenRouter) and enter your API key — stored only in your browser session, never sent anywhere except the selected provider
3. Paste your PubMed abstracts, MEDLINE export, or any safety text into the input panel — multiple abstracts are supported
4. Optionally add product context (e.g. drug class, indication) for more targeted analysis
5. Select an analysis mode and click **Analyse**
6. Review the output in the results panel

> **Privacy note:** Your text is sent to the AI provider you select, using your own API key. It is not stored or processed by any other server. Choose a provider consistent with your organisation's data governance policy.

---

### HighLit — Safety Literature Highlight Tool

A browser-based keyword highlighter for PubMed literature exports. Open `HighLit.html` in your browser.

Built for pharmacovigilance and medical affairs workflows where you need to scan hundreds of abstracts for safety signals, mechanisms, or population characteristics — and want to see them colour-coded at a glance rather than Ctrl+F-ing the same terms repeatedly.

**What it does:**
- Upload any PubMed `.txt` export (Abstract format, MEDLINE/tagged format, or plain text)
- Keyword categories are pre-loaded and fully editable — one term per line, one column per category
- Each category gets a distinct highlight colour; a legend at the top identifies which colour means what
- **Prefix stem matching** — entering `injur` catches "injury", "injured", "injuries", and "injurious" without requiring exact terms
- Matching is case-insensitive throughout
- Download the keyword table as an Excel file to edit offline, then re-upload the updated version

**How to use:**

1. Open `HighLit.html` in your browser
2. Drag and drop your PubMed `.txt` export (or click to browse) into the upload zone
3. Review the keyword table — edit categories directly in the browser, or download as Excel, modify, and re-upload
4. Click **Highlight** — the preview renders all abstracts with matching terms highlighted by category colour
5. Click **Download** to save the highlighted output

No data leaves your browser. No PubMed credentials required — just export your search results as a `.txt` file and drop it in.

---

### FOCUS — Strategic Time Manager

A daily planning tool built around three ideas: your most important tasks for the day, a time-blocked schedule, and a priority matrix. Open `FOCUS.html` in Chrome or Edge.

FOCUS is more involved to set up than the other tools because it stores data persistently. Read the setup steps below before opening it for the first time.

---

#### First-time setup

When you open FOCUS for the first time, you will see a setup screen before anything else. This is asking you where to save your data file — a plain `.json` file on your computer that FOCUS reads and writes to every time you make a change.

**Step 1 — Choose where to save your data**

Click **Create New Data File**. A file picker opens. Navigate to where you want to store your data and give the file a name (e.g. `focus-data.json`).

> **Recommended location:** A cloud-synced folder such as OneDrive or Google Drive. This means your data is backed up automatically and accessible if you switch computers. A local Desktop folder works fine too — just be aware that clearing your browser data will not affect this file, but losing the computer will.

**Step 2 — Grant permission**

After choosing the location, your browser will ask you to confirm write access. Click **Allow** (or **Save**). FOCUS will create the file and load the main app.

That's it. You're in.

---

#### Every time you reopen FOCUS

This is the most important thing to understand: **every time you open FOCUS, you will see a reconnect screen.** This is normal and expected — it is not an error.

Browsers require you to explicitly re-grant file access at the start of each session. This is a security feature of the [File System Access API](https://developer.mozilla.org/en-US/docs/Web/API/File_System_API) that cannot be bypassed.

**What to do:** Click **Open My Data File** → your browser will show a small permission prompt → click **Allow**. FOCUS loads in a second or two.

If you see "File not found" instead, it means the file was moved or deleted. Click **Open Existing File** and navigate to where your `focus-data.json` now lives.

---

#### What's inside FOCUS

| View | What it's for |
|------|---------------|
| **Today** | Your 3 Most Important Tasks for the day, plus your time-blocked schedule |
| **Tasks** | Full task list — add tasks, set due dates, assign categories, filter by status |
| **Priority Matrix** | Eisenhower-style quadrant view: Urgent/Important, Not Urgent/Important, etc. |
| **Settings** | Manage categories, change data file location, export/import data |

**Most Important Tasks (MITs):** The Today view shows three slots at the top. The discipline here is intentional — you are forced to decide, before looking at email or anything else, which three tasks will constitute a successful day. Mark them done as you go.

**Time Blocks:** Below the MITs is a time-block scheduler. Add blocks with a start time, end time, and label. This is your intended shape for the day — not a rigid schedule, but a plan that forces you to think about whether your MITs will actually fit.

**Priority Matrix:** Tasks you add anywhere in FOCUS can be dragged into one of four quadrants. This view is useful at end-of-week to see where your energy has been going versus where it should go.

---

#### Backing up your data

Your data is saved automatically to the `.json` file on disk. To create an explicit backup:

- Go to **Settings** → click **Export Backup**
- This downloads a timestamped `.json` file you can store anywhere

To restore from a backup, use **Import Backup** in Settings and select the backup file. The app will reload with your imported data.

---

#### Firefox and other browsers

FOCUS uses the [File System Access API](https://developer.mozilla.org/en-US/docs/Web/API/File_System_API), which is supported in Chrome, Edge, and other Chromium-based browsers, but **not in Firefox or Safari** as of 2025.

If you open FOCUS in Firefox, it will fall back to **browser localStorage** — your data is saved inside the browser itself rather than a file on disk. This works, but:

- Data is lost if you clear your browsing history or browser data
- Data does not transfer across browsers or machines
- There is no automatic file-level backup

If you use Firefox, use **Export Backup** regularly (Settings → Export Backup) and keep that file somewhere safe.

---

## Browser compatibility

| Tool | Chrome | Edge | Firefox | Safari |
|------|:------:|:----:|:-------:|:------:|
| PraxDocs | ✓ | ✓ | ✓ | ✓ |
| PDF Compare | ✓ | ✓ | ✓ | ✓ |
| HighLit | ✓ | ✓ | ✓ | ✓ |
| HighLit AI¹ | ✓ | ✓ | ✓ | ✓ |
| FOCUS (file mode) | ✓ | ✓ | — | — |
| FOCUS (browser storage) | ✓ | ✓ | ✓ | ✓ |

¹ Requires an API key from your chosen provider (Anthropic, OpenAI, Gemini, or OpenRouter) and an internet connection.

Chrome or Edge is recommended for FOCUS to get persistent file-based storage.

---

## Tech stack

No frameworks. No build step. No backend.

- **JavaScript** — all logic
- **HTML5 / CSS3** — structure and theming (dark/light mode)
- **PDF.js** — PDF rendering and text extraction
- **pdf-lib** — PDF creation and manipulation
- **Myers diff algorithm** — document comparison
- **File System Access API** — persistent local file storage in FOCUS
- **GitHub Pages** — hosting

---

## About

I'm a Medical Doctor with a specialisation in Pharmacology. The tools here are a direct result of problems I ran into doing real work in the pharmaceutical industry. I am not a software engineer by training — I built these to scratch my own itch, and I share them in case they scratch yours too.

If something is broken or you have a suggestion, open an issue on this repository.

**Dr. Prashant Patel** · [LinkedIn](https://linkedin.com/in/drprashantpatel) · [GitHub](https://github.com/drprash)

---

## License

MIT © Dr. Prashant Patel. Free to use, modify, and distribute.
