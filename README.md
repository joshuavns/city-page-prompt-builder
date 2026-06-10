# City Page — Section-by-Section Prompt Builder

A single-file tool for Ring Ring Marketing's SEO team. Fill out the Client Brief **once**, pick the client's vertical, and it generates all **14 city-page section prompts** with the brief and the matching Vertical Pack already injected into each one — so you never have to re-paste the brief into every ChatGPT prompt.

## Live tool

👉 **https://joshuavns.github.io/city-page-prompt-builder/**

## How to use

1. Fill in the **Client Brief** fields (Business Name, City, and Keyword are the minimum to generate).
2. Pick the **Vertical** — Home Improvement, Home Care, or Death Care. The matching Vertical Pack is injected automatically.
3. Click **Generate all 14 prompts**.
4. **Run Prompt 1 (Meta)** in ChatGPT first → pick a set → paste its H1 / Meta Title / Meta Description into the **Selected Meta Set** fields → click Generate again.
5. Copy each prompt (Copy button) into a fresh ChatGPT (GPT-5.5) message and run Prompts 2–14 in order.
6. Assemble the section outputs and run the QA checklist per the SOP.

Use **Save brief to browser** / **Load saved brief** to keep your work between sessions.

## Notes

- Everything is client-side. No data leaves the browser; the Save feature uses `localStorage`.
- The 3 Vertical Packs and all 14 prompts are embedded verbatim from the Section-by-Section Prompt SOP.
