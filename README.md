# City Page — Section-by-Section Prompt Builder

A single-file tool for Ring Ring Marketing's SEO team. Fill out the Client Brief **once**, pick the client's vertical, and it generates all **14 city-page section prompts** with the brief and the matching Vertical Pack already injected into each one — so you never have to re-paste the brief into every ChatGPT prompt.

## Live tool

👉 **https://joshuavns.github.io/city-page-prompt-builder/**

## How to use

1. Fill in the **Client Brief** fields (Business Name, City, and Keyword are the minimum to generate).
2. Pick the **Industry** (HVAC, Roofing, In-Home Care, Funeral, etc.). This drives the SGE/AIO + infographic topic libraries **and** auto-selects the matching Vertical Pack (tone, CTAs, heading patterns) behind the scenes.
3. Under **Topic Control**, choose the SGE/AIO angle and infographic topic (or leave on Auto), and paste any "already used" topics so they're never repeated across the client's pages.
3. Click **Generate all 14 prompts**.
4. **Run Prompt 1 (Meta)** in ChatGPT first → pick a set → paste its H1 / Meta Title / Meta Description into the **Selected Meta Set** fields → click Generate again.
5. Copy each prompt (Copy button) into a fresh ChatGPT (GPT-5.5) message and run Prompts 2–14 in order.
6. Assemble the section outputs and run the QA checklist per the SOP.

Use **Save brief to browser** / **Load saved brief** to keep your work between sessions.

## Attaching files (Brand Identity / Keyword Research)

Those two fields accept file attachments (**.docx, .xlsx/.xls, .csv, .txt**). The file is parsed **in your browser** and its text is appended into the field, so it travels with the brief into the prompt. Nothing is uploaded anywhere. (Old `.doc` and `.pdf` aren't supported — re-save as `.docx` or paste the text.)

## Notes

- Everything is client-side. No data leaves the browser; the Save feature uses `localStorage`.
- The 3 Vertical Packs and all section prompts are embedded verbatim from the Section-by-Section Prompt SOP.
- File parsing uses two libraries loaded from a CDN (mammoth for .docx, SheetJS for .xlsx), so attachments require the page to be online — which it is whenever it loads from GitHub Pages.
