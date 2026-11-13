# Mind-sage Version 3 — Your Personal Wellbeing Journey

**Full static GitHub Pages website, with Version 2 preserved and eleven major Version 3 upgrades.** No build command, npm modules, hosted database, API key, or Render server is needed for the static release. Uses HTML, CSS and vanilla JavaScript.

## 1. What's new in V3

| Area | What works now |
|---|---|
| Completely redesigned home | Botanical, editorial, sage/forest-green responsive experience with five student entry categories |
| Emotion Landscape | Six animated emotional-weather selections, tailored reflection guidance, optional local/session history |
| Mind Garden | Growing botanical scene for completed self-care reflections, one per activity per day; no streak punishments |
| Life Journey | Five new branching student stories, three decisions per story with non-scored supportive feedback |
| Mind Journal | Guided writing prompts, private notes, tags, delete and text export |
| Personalized plans | 7-day or 14-day, five focus areas, daily activities, undo/check tracking, transparent recommendations |
| Wellbeing insights | Self-reported diary energy trends, local stats and an explainable rule trace |
| Mind Map | Visual organization of recent emotions, self-care activities and support options, with no inferred diagnoses |
| Relaxation room | Synthesized rain/waves/forest audio, volume setting, English/Bengali/Hindi speech guide |
| Accessibility and control | Normal/large/extra-large text, contrast, reduced motion, local data deletion and PWA installation |
| Support Connect | Private report handoff, optional institution-supplied booking URL, professional/research integration roadmap |
| Connected AI hook | Rule-based companion works fully offline; separately hosted AI endpoint can be configured (see optional adapter) |
| Progressive Web App | Installable app manifest, 192/512 icons, offline caching of the site shell and art, GitHub Pages-compatible |

**Version 2 is retained:** five student categories; DOB, gender and changing CAPTCHA; four distinct 10-question anxiety/low mood/stress/confusion check-ins and adaptive follow-up; reporting and A4 PDF; mood diary; original four scenario exercises; Bro-minD breathing, grounding, meditation, sourced Bengali Vivekananda Vani and motivation; guided local companion; support directory; optional 7/14-day challenges; adult-only device-local research CSV summaries; Bengali/English UI.

## 2. GitHub Pages deployment — easiest option

**Create a new repository** so V1 and V2 continue working independently.

1. Extract `Mind-sage-Version-3-GitHub-Pages.zip` on your computer. The site files are at the **root** of the extracted archive.
2. Open <https://github.com/new>, create a **public** repository, for example `MIND-SageV3`.
3. Choose **Add file → Upload files** and upload **all files extracted from the zip**, without nesting inside another folder. The repository root must contain `index.html`, `app.js`, `data.js`, `v3.js`, `styles.css`, `v3.css`, `config.js`, `manifest.webmanifest`, `sw.js`, `icon-192.png`, `icon-512.png`, `favicon.svg`, `vivekananda-portrait.webp`, `README.md`, and `SOURCES.md`.
4. Commit to branch `main`.
5. Open **Settings → Pages → Build and deployment → Deploy from a branch**, select `main` and `/(root)`, then save.
6. Expected address, for the previously supplied GitHub username: **https://SAYANPAL-CREATE.github.io/MIND-SageV3/**.
7. After deployment completes, refresh the public page with **Ctrl + Shift + R**. To install, use **Accessibility & privacy → Install Mind-sage**, or the browser's **Install App / Add to Home Screen** menu.

**Important:** upload the `vivekananda-portrait.webp` beside `styles.css` in the repository root. The CSS has a root-relative-in-repository `./vivekananda-portrait.webp` path; do not move the image into `assets` unless you change the CSS.

### For an existing V2 repository

Create a backup first, then overwrite the five existing website source files, update the existing favicon and image if desired, and add the V3-specific assets and files. A new V3 repository is cleaner. Device-local data is origin-specific: changing repository paths can change how `localStorage` is scoped, but do **not** assume the data is migrated between separate origins or automatically backed up. If you want to retain any personal V2 diary data, export it first from the V2 site, and keep it on a private device.

## 3. Editing, maintenance and troubleshooting

- `index.html`: entry point, fonts, metadata and PWA manifest.
- `styles.css` / `app.js` / `data.js`: original V2 interface, interactions, questions, quotations and content.
- `v3.css` / `v3.js`: new V3 views, styles, animation, journal, garden, scenarios, wellbeing plans, analytics, audio, install behavior.
- `config.js`: optional **public-safe URLs only**, no credentials. Leave `aiEndpoint` empty for offline/local mode. Only use `approvedBookingUrl` after checking a real, authorized provider's HTTPS appointment link.
- `sw.js` / `manifest.webmanifest` / icon PNGs: offline installation.
- `vivekananda-portrait.webp`: original, locally bundled AI-created artistic portrait of Swami Vivekananda (not an archival photograph).
- `SOURCES.md`: supporting verified public sources and quotation provenance.

### If something looks wrong

- **Blank page:** check all JavaScript filenames, especially `v3.js`, `config.js` and `data.js`, at the root. JavaScript errors may appear in the browser console.
- **Portrait missing:** confirm `vivekananda-portrait.webp` at the repository root; case must match exactly.
- **Old version persists:** hard refresh; for a previously installed PWA, close and reopen it after the service worker updates, or clear the site's cache.
- **Cannot install:** GitHub Pages HTTPS is required for ordinary PWA installation; use Chrome/Edge's install menu or Safari's Add to Home Screen. Browser support varies.
- **No sound or voice:** tap an audio option to start it. Browser sound permissions, Web Audio and text-to-speech voices vary, especially for Bengali/Hindi. Other site features work without audio.
- **No data after closing:** for children (<18), V2/V3 personal entries are session-only by design; for adults, use the explicit save actions. Avoid shared computers.
- **AI not responding:** this public frontend intentionally ships without a connected AI provider. The local guided companion still works. See section 5.

## 4. Privacy, safety, age and health boundaries

This static release runs primarily in the visitor's browser. **No live patient dashboard, clinician database, or centrally collected university research data exists in this package.** The original 10-item questions and response percentages are illustrative software-defined indexes, not verified clinical probabilities or medical diagnoses. A clinician must make treatment and medication decisions. The Mind Map and plan recommendation rules are transparent descriptive choices, not trained psychiatric predictions.

The project may be visited by minors:

- V2 personal assessment answers, DOB and gender are kept in browser memory during the session.
- Under-18 V2 diary/challenge entries and V3 journal, garden, plans and landscape entries are session-only, not saved between reloads.
- For adults, **explicitly saved** V2 and V3 records are stored locally in the browser's `localStorage`; no automatic server sync occurs. Someone using the same browser profile may be able to see the stored data. V3 includes a local wipe control. V2 has its own data deletion control. Downloaded files need separate deletion.
- The `config.js` booking URL, if supplied, opens an external provider's site; no appointment is booked without that provider's confirmation.
- The optional AI backend example must not be put into use with minors or real mental health patients without strong age assurance, clinical oversight, privacy and safety controls.
- Responding to serious distress requires appropriate human support. The support directory includes Tele-MANAS **14416**, emergency **112**, and Child Helpline **1098** in India. Verify current service details before publication or any real-world study.
- For university research or protected health data, first establish institutionally approved consent/assent, ethical review, validated measures, data-protection and incident-response policies, role-based access and secure backend infrastructure.

The front-end client uses Google Fonts when online; system fonts provide an offline fallback. For maximal privacy, self-host fonts or use system fonts. No analytics SDK is included.

## 5. Optional separate backend integration

A separate download, `Mind-sage-V3-Optional-AI-Backend.zip`, contains a Node.js starter for an opt-in, adult-only connected AI experience, with an origin allowlist, rate limiting and no transcript database. **It is not production-ready, does not provide accounts, real clinician portals or bookings, and cannot be run on GitHub Pages.** It must run separately on secure HTTPS infrastructure with the AI API key held in environment variables. See its README.

Do not place secrets in `config.js`, client JavaScript, or the GitHub repository.

## 6. Quality checks completed

Verified with a headless Chromium browser using an in-memory page harness and local website assets: homepage and five student choices, invalid → regenerated CAPTCHA, underage profile, ten + one assessment flow, PDF download and A4 rendering, six V3 route groups, adult-safe UI controls, journal HTML escaping, garden interaction, personal plan completion, three-stage branching story, accessibility toggles and browser console. Responsive smoke tests at a 390px mobile width for home, landscape, garden, journal, plan, mindmap, relaxation and support pages showed no horizontal overflow.

Static assets, relative URLs, PWA manifests and service-worker files have been validated locally; a real GitHub Pages deployment and AI-provider connection are **not** covered by those local browser tests.
