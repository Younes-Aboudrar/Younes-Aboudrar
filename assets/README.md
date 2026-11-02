# Profile artwork and content notes

The profile renders directly on GitHub. It has no build step, JavaScript, external image service, or runtime font dependency.

## Artwork

- `signature-header.svg`: 1200 × 450 desktop hero; all lettering is converted to paths.
- `signature-header-mobile.svg`: 600 × 450 composition selected below 601 CSS pixels; larger relative type and shorter lines.
- `signature-header.png`: static 1200 × 450 fallback for renderers without SVG/picture support.
- `source/`: editable SVG masters. These use fonts only during artwork editing/export.
- `licenses/`: original SIL Open Font License notices for both typefaces.

The circuit geometry and composition are custom. The signature is outlined **Great Vibes** lettering, paired with **Plus Jakarta Sans**. The signature is typographic artwork, not a claim to reproduce Younes's handwritten signature. Both fonts come from [Google Fonts](https://github.com/google/fonts).

| Role | Color |
| --- | --- |
| Background | `#0B1423` |
| Signature / fine rules | `#D4B78B` |
| Circuit detail | `#55B9CB` |
| Primary text | `#EEF3F8` |
| Secondary text | `#8196A9` |

The opaque navy canvas preserves contrast in both GitHub themes. Body text uses GitHub's native theme and typography. All artwork is static, including for readers who prefer reduced motion. Descriptive image alt text and SVG titles retain the identity and tagline. Essential information and contact links remain ordinary text.

`<picture>` selects the mobile or desktop SVG, with a PNG `<img>` fallback. Browser format fallback does not recover a missing SVG URL: keep all three published assets together. Mobile uses the same signature, with the subtitle and tagline on shorter lines. No remote font files are fetched by readers.

## Editing the artwork

Edit the masters in `source/`, then export with Inkscape 1.4 and the fonts below installed. Run from the repository root:

```sh
inkscape assets/source/signature-header.svg --export-text-to-path --export-plain-svg --export-type=svg --export-filename=assets/signature-header.svg
inkscape assets/source/signature-header-mobile.svg --export-text-to-path --export-plain-svg --export-type=svg --export-filename=assets/signature-header-mobile.svg
inkscape assets/signature-header.svg --export-type=png --export-filename=assets/signature-header.png
```

Keep `<title>`, `<desc>`, the viewBox, and the README's alt text. Confirm the exported SVGs contain no `<text>` elements, scripts, external references, or font imports. Inspect at desktop and phone widths after changing lettering.

Font sources used for this artwork:

| Typeface | Source | SHA-256 of downloaded font |
| --- | --- | --- |
| Great Vibes Regular | [GreatVibes-Regular.ttf](https://raw.githubusercontent.com/google/fonts/main/ofl/greatvibes/GreatVibes-Regular.ttf) | `8d509802186f1b51572531ecf313e8098f9a5bfdfaca93f0c9b34467f9982d15` |
| Plus Jakarta Sans | [PlusJakartaSans\[wght\].ttf](https://raw.githubusercontent.com/google/fonts/main/ofl/plusjakartasans/PlusJakartaSans%5Bwght%5D.ttf) | `89b3fb38aa0d275d7a731d0d817a4f1622b316b4d7fbdedcf02ee9099ff68bc8` |

Upstream fonts may change. Check the downloaded files against these hashes before reproducing the export; retain the accompanying license notices.

## Content provenance

Descriptions were checked against repository source on 2 November 2026. They describe implementation, not independently measured performance or production readiness of the featured projects.

| Repository / inspected revision | Evidence used |
| --- | --- |
| [AI Engineering FAQs Chatbot](https://github.com/Younes-Aboudrar/CodeAlpha_AIEngineeringFAQsChatbot/tree/5bc3cff653de975a393eeb2a0717c81d5dc292d2) | `app.py`, `faqs.json`, `README.md`: Flask routes, spaCy matching, TF-IDF fallback, and conversation history. |
| [Language Translation Tool](https://github.com/Younes-Aboudrar/CodeAlpha_LanguageTranslationTool/tree/487fc14ce6c473ea10e900f154a2b5543640bbad) | `script.js`, `README.md`: Azure requests, detected language, browser speech synthesis. |
| [AéroENSEM](https://github.com/Younes-Aboudrar/aeroensem_website/tree/31c11122f5669bfdbdfed72c54524ec73c0c3337) | `content/index.md`, `hugo.toml`, `.github/workflows/hugo.yml`: club/event content and Hugo → GitHub Pages deployment. History and leadership pages are drafts and are not advertised as completed features. |
| [Portfolio](https://github.com/Younes-Aboudrar/portfolio/tree/4408237694b414eab92ba79f4fe55d23d50b2335) | `apps/portfolio/package.json`, `src/lib/i18n/{en,fr}.ts`, `src/lib/contact.ts`, `src/lib/projects/en.ts`, and `src/routes/cv/+page.svelte` within that app: stack, bilingual content, CV, exchange status, academic topics, and LinkedIn identity. |

The contact email and March 2027 availability follow the supplied brief. The portfolio source clarifies ENSEM Casablanca enrollment and the ENSEM Nancy exchange. MATLAB/Simulink, PID control, and data analysis are presented as academic foundations; unsupported candidate skills such as ROS 2 are omitted.

The statistics section deliberately uses GitHub's native contribution graph and activity timeline, shown below the README and pinned repositories on the profile. It does not embed third-party widgets, duplicate the graph, cache counts, or invent language shares or streaks. This keeps activity current without scheduled jobs or tokens.

The seven unique GitHub URLs in the profile returned HTTP 200 during validation. The portfolio and LinkedIn addresses were confirmed in the owner's portfolio source; direct HTTP checks were blocked by the environment's domain policy. A `mailto:` link is provided without claiming email deliverability was tested.

Local rendering was checked with cmark-gfm and Chromium using GitHub-style Markdown CSS at 320, 390, 768, and 1280 pixels in both light and dark modes. Checks covered horizontal overflow, image decoding, mobile source selection, reduced-motion settings, and PNG fallback. This validates a local rendering approximation; GitHub's live sanitizer and image proxy are only exercised after publication.

## Future updates

Keep each featured project to a linked title, the problem it addresses, its implemented approach, and a short technology line. Recheck the source before adding outcomes or competencies. Update the internship date in both occurrences when availability changes. No environment configuration or publication is part of this implementation.
