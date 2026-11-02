# Profile design and content notes

The profile renders directly on GitHub with text and supported HTML. It has no build step, images, JavaScript, external statistics widgets, or runtime font dependencies.

## ASCII hero

`YOUNES` uses the four-line FIGlet **Small** style in a native `<pre>` block. `ABOUDRAR` follows as a smaller `<samp>` subtitle. A surrounding `<div align="center">` centers the hero using GitHub-supported HTML. Subtitle, positioning line, availability, and contact links remain ordinary wrapping text.

The banner is 31 monospace columns wide. Keep its leading spaces and backslashes unchanged. The `&#32;` at the end of the first row preserves its final space without trailing whitespace in the Markdown source. All four decoded rows have equal width, so centering does not shift individual rows out of alignment. Do not indent the block or apply language syntax highlighting.

GitHub supplies the monospace font, foreground, and code-block background in light and dark themes. No fixed color, custom CSS, SVG, or cursive artwork is used. The banner is static, including for readers who prefer reduced motion. The introduction also spells out the full name in ordinary text.

The initial banner was generated with pyfiglet 1.0.4 and the `small` font, then stored directly in the README. pyfiglet is an optional authoring tool, not a project dependency. Preserve the current compact width when editing; a full-name FIGlet banner would be too wide for phones.

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

## Rendering checks

The README was validated with cmark-gfm and Chromium using GitHub-style Markdown CSS at 320, 390, 768, and 1280 pixels in both light and dark modes. All eight checks passed: the page and `<pre>` have no horizontal overflow, all four banner rows remain equal-width and centered, the subtitle and availability text wrap naturally, and all 16 project/contact links remain present. The banner uses the native monospace stack at 13.6 pixels without custom font loading. Recheck these properties after editing.

This is a local rendering approximation. GitHub's live sanitizer can be checked after pushing the update; local preview CSS is not shipped in the repository.

## Future updates

Keep each featured project to a linked title, the problem it addresses, its implemented approach, and a short technology line. Recheck the source before adding outcomes or competencies. Update the internship date in both occurrences when availability changes.
