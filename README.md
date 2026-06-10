# City Page — Prompt Builder

A single-file, client-side tool for Ring Ring Marketing's SEO team. Fill out the Client Brief **once**, pick the client's industry, and it builds ready-to-paste ChatGPT (GPT-5.5) prompts with the brief and the matching Vertical Pack already injected — so you never re-paste the brief, and the output follows the City Page SOP rules. It also cleans the result into a properly formatted Word document.

It's built as a **fallback** that reproduces the deployed Vercel/GPT-5.5 City Page Generator, and it runs entirely on GitHub Pages (independent infrastructure), so it stays up even if the main app is down.

## Live tool

👉 **https://joshuavns.github.io/city-page-prompt-builder/**

## Two modes

- **One-shot (recommended)** — 2 prompts total: a **Meta** prompt (5 sets), then a single **Full Page** prompt that produces the entire draft in one ChatGPT generation. Whole-page-aware, so it enforces the cross-section rules (25-city-mention total, business-name placement, no topic overlap). This mirrors what the live tool does.
- **Section-by-section** — the 14 individual section prompts, one per section. A last resort, or for regenerating a single section surgically.

## How to use

1. Fill in the **Client Brief** (Business Name, City, and Keyword are the minimum). Set the full **ADDRESS** including state + ZIP — it's copied verbatim into the Intro and Closing.
2. Pick the **Industry** (HVAC, Roofing, In-Home Care, Funeral, etc.). This drives the SGE/AIO + infographic topic libraries **and** auto-selects the matching Vertical Pack (tone, CTAs, heading patterns) behind the scenes — no separate "vertical" pick.
3. **Services to Cover** — add each service as a row (name + optional URL), with a toggle to enter sub-services manually. Manual sub-services are the most reliable; a URL alone relies on ChatGPT being able to read that page.
4. Under **Topic Control**, choose the SGE/AIO angle and the infographic topic (or leave on Auto), and paste any "already used" topics so they're never repeated across the client's pages.
5. Pick a **mode** and click **Generate**.
6. **Run the Meta prompt** in ChatGPT first → pick a set → paste its H1 / Meta Title / Meta Description into the **Selected Meta Set** fields → click **Generate** again.
7. Copy the **Full Page** prompt (or each section prompt) into a **fresh ChatGPT chat** and run it.
8. **Copy ChatGPT's reply using its Copy button** (raw markdown — keeps `**bold**` and `[links](url)`), then format it for Word (below).
9. QA the draft per Sections 15–16 of the SOP.

Use **Save brief to browser** / **Load saved brief** to keep your work between sessions.

## Format pasted output for Word

ChatGPT collapses the spacing around the `<h2>`/`<h3>` tags on copy, so headings get jammed into the body. Paste the full ChatGPT output into the **Format pasted output for Word** box, then:

- **Clean for Word** → rich preview with headings on their own lines, bold labels, and clickable links. Use **Copy for Word** to paste into an existing doc.
- **⬇ Download Word (.doc)** → a Word-openable file with everything already formatted (headings, bold, hyperlinks, paragraphs). No copy-paste fidelity issues.

> Tip: always copy from ChatGPT with its **Copy button** (raw markdown). Highlighting the text strips the `**bold**` markers and link URLs that the cleaner needs.

## Attaching files (Brand Identity / Keyword Research)

Those two fields accept file attachments (**.docx, .xlsx/.xls, .csv, .txt**). The file is parsed **in your browser** and its text is appended into the field, so it travels with the brief into the prompt. Nothing is uploaded anywhere. (Old `.doc` and `.pdf` aren't supported — re-save as `.docx` or paste the text.)

## Output format

The prompts emit the deliverable's document format: raw URL + `Meta Title:` / `Meta Description:` + `Download all images:` + `<h1>`, then literal `<h2>`/`<h3>` heading tags, `<CTA Button>` blocks, `<Image Alt>` tags, bold-label list paragraphs, an inline `[ INFOGRAPHIC IMAGE — ADD AFTER UPLOAD ]` placeholder, and a structured `<h2>Infographic Prompt</h2>` block.

## Notes

- Everything is client-side. No data leaves the browser; the Save feature uses `localStorage`.
- The Vertical Packs, the 10-industry topic libraries, and all prompts are embedded in the page. If the SOP rules change, update the constants in `index.html` to match.
- File parsing and the rich Word cleaner use small libraries from a CDN (mammoth for `.docx`, SheetJS for `.xlsx`), so those features need the page online — which it is whenever it loads from GitHub Pages.
- This is a **fallback** for the deployed Vercel/GPT-5.5 City Page Generator. Keep its rules in sync with the live app's system prompt.
