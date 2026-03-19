# AI Transparency Tracker

**Document · Disclose · Declare**

A lightweight, open-source tool for journalists and journalism students to track their AI usage across the stages of story production — and generate a standardised transparency declaration when the story is published.

Think of it as [Creative Commons](https://creativecommons.org/) for AI use in journalism.

---

## What it does

The AI Transparency Tracker lets you:

- **Create story folders** for each piece you're working on
- **Log AI interactions as you go**, recording which tool you used, what for, your actual prompts, and your intent
- **Self-assess your AI usage** at the end, using a five-level scale across each production stage
- **Auto-generate an AI Transparency Label** — a composable code (like `AI-R` or `AI-RDP`) that indicates which stages involved AI
- **Generate a natural-language transparency declaration** suitable for publishing alongside your story
- **Export structured data** as JSON for research or record-keeping

All data stays in your browser. Nothing is sent to any server. The generated transparency declaration **never includes the journalist's name** — it uses "the author" throughout, protecting identity by default. The name field is retained only in the local data and JSON export for internal record-keeping.

---

## The Label System

The AI Transparency Label is built on five stages of journalistic production:

| Letter | Stage | What it covers |
|--------|-------|----------------|
| **I** | Idea | Story conception, angle development, pitch |
| **R** | Research | Background research, data gathering, source finding |
| **O** | Organise | Structuring, outlining, planning the narrative |
| **D** | Draft | Writing the story, generating text |
| **P** | Polish | Editing, proofreading, rewriting, headlines |

Labels are **composable** — they auto-generate from your logged entries. Only stages where AI was actually used appear in the label.

### Example labels

| Label | Meaning |
|-------|---------|
| `AI-0` | No AI tools were used |
| `AI-R` | AI used for research only |
| `AI-RP` | AI used for research and polishing |
| `AI-RDP` | AI used for research, drafting, and polishing |
| `AI-IRODP` | AI used across all production stages |

Any combination of I · R · O · D · P is possible. The label is descriptive, not evaluative — it says *where* AI was used, not whether that use was appropriate.

---

## Getting started

### Option 1: Open directly

Download `index.html` and open it in any web browser. That's it. No installation, no server, no dependencies.

### Option 2: Host on GitHub Pages (recommended for classroom use)

1. Create a new repository on GitHub (e.g. `ai-transparency-tracker`)
2. Upload `index.html`, `README.md`, and `LICENSE`
3. Go to **Settings → Pages → Source** and select your main branch
4. GitHub will give you a URL like `yourusername.github.io/ai-transparency-tracker`
5. Share that link with your students — they bookmark it and they're done

Students open the link in any browser, use the tool, and their data automatically persists between sessions via localStorage. No accounts, no installation, no app store.

### Option 3: Fork and customise

```bash
git clone https://github.com/[your-username]/ai-transparency-tracker.git
```

The entire application is a single HTML file with no build step. Edit it in any text editor.

---

## How it works

### For journalists and students

1. **Start a story** — give it a title, your name, and publication
2. **Log AI use as you go** — whenever you use an AI tool during your reporting, tap the relevant stage, pick the tool and usage type, and optionally paste your prompt
3. **Self-assess** — when the story is done, use the five-level assessment to describe how much AI influenced each stage
4. **Generate your declaration** — the tool produces a natural-language transparency statement and your AI label
5. **Copy or export** — copy the declaration to publish alongside your story, or export the full dataset as JSON

### For researchers

The JSON export contains:

- Story metadata (title, author, publication)
- Every logged AI interaction with timestamps, tools, usage types, prompts, and intent notes
- The self-assessment ratings per stage
- Open-ended reflections
- The auto-generated label and disclosure text

This structured data supports quantitative analysis (usage patterns, tool frequency, stage distribution) and qualitative analysis (prompt construction, stated intent, reflexive commentary).

---

## The self-assessment scale

Adapted from a checklist developed by Janak Rogers, the self-assessment asks students to rate their AI use at each stage on a five-point scale:

| Level | Description |
|-------|-------------|
| **AI-led** | AI drove the process at this stage |
| **High use** | AI assisted at key points |
| **Moderate** | AI used selectively for specific tasks |
| **Light use** | AI used for reference and checking only |
| **No AI** | Worked independently |

Each level has stage-specific descriptions to help users identify where their practice sits. The self-assessment data is included in both the transparency declaration and the JSON export.

---

## Research context

This tool was developed as part of a practice-led research project at RMIT University's School of Media and Communication. It is designed to be deployed as both a pedagogical tool and a research instrument, enabling studies that compare:

- **Contemporaneous AI usage logs** (captured in real time via the tracker) with **retrospective self-assessment** (captured via the end-of-process survey)
- Patterns of AI adoption across production stages
- Prompt literacy and how students frame tasks for AI tools
- The adequacy of current disclosure frameworks

If you use this tool in your research, we'd love to hear about it.

---

## Privacy

- **No data leaves the browser.** Everything is stored in localStorage on the user's device. There is no server, no analytics, no tracking.
- **The journalist's name never appears in the declaration.** The transparency statement always refers to "the author," so it can be published alongside a story without creating a secondary identification risk.
- **The name field exists for internal records only.** It appears in the JSON export, which is useful for research data collection under ethics protocols, but is never surfaced in any public-facing output.
- **Data persists between sessions.** Students can close their browser, shut down their computer, and return days later — their data will still be there. Data is only lost if they clear their browser data, switch to a different browser, or use incognito mode.
- **Students control their own data.** They can delete stories at any time, and they choose whether and when to export their data. We recommend students export their JSON periodically as a backup.

---

## Technical details

- **Single HTML file** — no build step, no framework, no dependencies beyond Google Fonts
- **Vanilla JavaScript** — no React, no npm, nothing to install
- **localStorage** — all data persists in the user's browser; nothing is transmitted
- **Responsive** — works on desktop and mobile, with adaptive layouts for the self-assessment grid
- **Dark mode** — automatically follows system preferences
- **~1,100 lines** — small enough to read, understand, and modify

---

## Contributing

Contributions are welcome. Some areas where the tool could grow:

- **Browser extension** that detects AI tool usage and prompts logging automatically
- **Additional export formats** (CSV, PDF declaration)
- **Localisation** into other languages
- **Newsroom deployment features** — team dashboards, aggregated analytics (would require a backend)
- **Integration with C2PA/Content Credentials** to embed AI provenance metadata in published content
- **Accessibility audit** and improvements
- **Additional label categories** — e.g. distinguishing between generative and analytical AI use

Please open an issue to discuss significant changes before submitting a pull request.

---

## Licence

This project uses a **dual licence** structure:

### Code — GNU GPL v3

All source code is licensed under the [GNU General Public License v3.0](https://www.gnu.org/licenses/gpl-3.0.html). You can use, modify, and redistribute the code, but derivative works must also be released under GPL v3.

### Label system — CC BY-SA 4.0

The AI Transparency Label taxonomy — the composable I · R · O · D · P stage framework and all label codes — is licensed separately under [Creative Commons Attribution-ShareAlike 4.0](https://creativecommons.org/licenses/by-sa/4.0/).

This means you can implement the labelling system in your own tools, newsroom policies, editorial guidelines, and publications, provided you credit the original work and share adaptations under compatible terms. **You do not need to engage with the GPL to adopt the labels.**

---

## Citation

If you use this tool or the AI Transparency Label system in academic work, please cite:

> Ambyo, T. and Rogers, J. (2026). *AI Transparency Tracker* [Software]. RMIT University. Available at: https://github.com/[your-username]/ai-transparency-tracker

---

## Credits

**Tito Ambyo** — concept, design, development
**Janak Rogers** — self-assessment framework, co-design

School of Media and Communication, RMIT University, Melbourne, Australia.

---

## Related work

- [C2PA / Content Credentials](https://c2pa.org/) — open standard for digital content provenance
- [Trusting News](https://trustingnews.org/) — resources on AI disclosure for newsrooms
- [Generative AI in the Newsroom](https://generative-ai-newsroom.com/) — Tow Center research on AI in journalism
- [JournalismAI](https://www.lse.ac.uk/media-and-communications/polis/JournalismAI) — LSE initiative on AI and news
- [Paris Charter on AI and Journalism](https://rsf.org/en/paris-charter-ai-and-journalism) — principles for AI transparency in news
