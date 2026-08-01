# PromptWeb — AI Agent Instructions (Architecture v2)

## SOURCE OF TRUTH NOTICE (mandatory)

This file (`AI_INSTRUCTIONS.md`) and `README.md` contain the **same complete rules** (dual full instructions — Option B).

- Any AI that reads **only one** file still gets **everything**.
- **Every rule is mandatory. No exceptions.**
- **Structure rules always win** over inventing new folders or free-form paths.
- Prefer reading both if convenient; either alone is enough.

---

## HARD RULE — Locked design repository (always)

This design repository is permanently configured by the site owner in PromptWeb Settings.

| | |
|---|---|
| **You must work ONLY on** | `Developergokul/akash_project_test` |
| **Branch** | `main` |
| **Live site** | https://akashmali.info/candela/ |

**Always true (even when the human forgets to name the repo in a later message):**

1. **Work only on repository:** `Developergokul/akash_project_test`
2. Never create, edit, commit, or open files in any other GitHub repository.
3. Never invent or guess a different owner/repo name.
4. If a tool or chat suggests another repo, **stop and stay on** `Developergokul/akash_project_test`.
5. Every commit, file read, and file write targets **this** repo only.

This rule is written into this file automatically when PromptWeb Initialize / Re-initialize runs, using the exact Repository value from WordPress → PromptWeb Settings. The human does not need to repeat the repo name for the rule to apply.

---

## 🚨 CRITICAL RULES GATES (MUST READ BEFORE PROCEEDING) 🚨

1. **NO LOOKALIKE PAGES (MAXIMUM UNIQUENESS — HARD FAIL IF BROKEN)**  
   - **Never** copy HTML layout, colors, section order, card grids, headers/footers, or styling from existing pages in this repo (`home.html`, other pages, starters, or any `components/` samples).  
   - **Never** reuse a “PromptWeb default” look (indigo/purple SaaS, glass blobs, same hero + 3 cards + CTA recipe).  
   - Two sites on the same host with different briefs (e.g. **jewellery** vs **fitness**) must look like **two different agencies** designed them — different typography, palette, density, imagery, section types, and motion.  
   - **Simple text prompts are enough.** Infer industry, audience, and mood from the words. Invent a full original art direction every time.  
   - Similarity to prior work is a **major failure**. If unsure, change more: layout system, type scale, color story, and section mix.

2. **EVERY FULL PAGE = 15+ UNIQUE SECTION DESIGNS (MANDATORY)**  
   - Every homepage or major landing page must include **at least 15 distinct visual sections** (not repeated clones).  
   - Sections must **differ in layout pattern** (not the same 3-column card row 15 times). Vary: full-bleed hero, split media, marquee/ticker, bento grid, masonry, timeline, horizontal scroll strip, large typography break, stats band, testimonial carousel/wall, process steps, pricing tiers, FAQ accordion, gallery, map/contact split, brand film strip, team, logos, sticky CTA bar, footer mega-grid, etc.  
   - Count only real designed blocks with unique structure/composition. Tiny spacer divs do **not** count.  
   - Short utility pages (e.g. legal) may be shorter; for marketing/home/service pages **15+ is required**.

3. **NO MANDATORY THEME SWITCHER / NO SHARED CSS THEME KIT**  
   - **Do NOT** add the sticky palette theme switcher unless the user **explicitly** asks for a theme switcher.  
   - **Do NOT** force every page onto generic `--primary` / indigo CSS variables. Hardcode a **page-specific** palette in Tailwind classes or a small page-only `:root` that matches the brief (gold/black jewellery, energetic fitness neons, etc.).  
   - Optional theme tools must never become a default that makes sites look the same.

4. **NO COMPONENT LIBRARY LOCK-IN**  
   - Any `components/` HTML samples (if present) are **legacy optional examples only**.  
   - **Do not** “pick blocks from components and assemble.” Invent original section HTML for this brief.  
   - Prefer industry research (below) over any in-repo sample.

5. **VISUAL RESEARCH FOR SIMPLE PROMPTS (RESEARCH MODE)**  
   - When the user gives only plain English (no reference URL), you **must** design as if you studied current UI trends for that niche.  
   - Mentally / tool-assisted inspiration from professional sources: **Dribbble, Behance, Pinterest, Awwwards, Land-book, Mobbin, Godly**, industry brand sites, and editorial photography mood.  
   - Extract **composition ideas** only — never steal assets or paste copyrighted UI 1:1. Rebuild in original Tailwind HTML.  
   - Match industry cues: jewellery → luxury serif, soft light, product hero; fitness → bold athletic type, high energy imagery, strong CTAs; restaurant → warm food photography, menu rhythm; etc.

---

You are an **elite web designer + frontend engineer** for a **PromptWeb** site.
The human only writes **simple plain English**. You own **all** design and code decisions — full creative freedom, zero template lock-in.

**Mandatory first step (every task):**  
`@GitHub Read README.md, AI_INSTRUCTIONS.md, and pages/manifest.json first.`  
`Work only on repository: Developergokul/akash_project_test`  
Load the rules and catalog **before** creating or editing pages. Even if the human omits the repo line later, you still work **only** on `Developergokul/akash_project_test`.

**Priority: maximum design uniqueness + beauty + true reference fidelity when a reference is given + strong visuals + never refuse for missing MCP.**

---

## HARD RULE — File structure (never break)

You may **ONLY** create or edit:

| Allowed path | Purpose |
|--------------|---------|
| `pages/static/{slug}.html` | Static HTML + Tailwind CDN + JS |
| `pages/dynamic/{slug}.php` | Dynamic PHP + WordPress |
| `pages/manifest.json` | Page catalog (`public_url`, status, type, title) |

**FORBIDDEN (never create or use):**

- Any folder at **repo root** for pages (`portfolio-6/`, `about/`, `services/`, `home/`, etc.)
- `index.html` (or any page file) inside custom folders outside `pages/static` or `pages/dynamic`
- Page files anywhere outside `pages/static/` or `pages/dynamic/`
- Mixing plugin code into this design repo (plugin lives at `Akashmali6198/promptweb`)

If a tool or habit suggests another path: **stop and use the allowed paths above.** Structure rules always win.

---

## HARD RULE — Two agent modes (mandatory)

Agents do **not** all have MCP. **Never refuse work** because MCP/REST tools are missing.

### Mode A — MCP / REST tools available (**preferred** when present)

Use these when available:

| Tool | Purpose |
|------|---------|
| `analyze_reference_url` | **Call first** when a reference URL is given |
| `list_pages` | List pages + `public_url` |
| `get_page` | Full source + `public_url` |
| `create_page` | Create as **Draft** + `public_url` / `final_reply_url` |
| `update_page` | Update + `public_url` / `final_reply_url` |
| `publish_page` | Draft → Publish + `public_url` |
| `get_visual_analysis` | Layout/spacing/hierarchy score |
| `commit_to_github` | Push design changes |

REST: `/wp-json/promptweb/v1/mcp/*` (requires `manage_options`).

**Mode A workflow:** Draft first → improve → publish via tools → commit → last line = exact `public_url`.

### Mode B — GitHub file tools only (ChatGPT and similar)

**If MCP/REST tools are NOT available, you MUST still complete the task** using GitHub file operations only.

1. **@GitHub Read README.md, AI_INSTRUCTIONS.md, and pages/manifest.json first.** Work only on repository: `Developergokul/akash_project_test`.
2. Create/update the page file at the **correct path only**:
   - static → `pages/static/{slug}.html`
   - dynamic → `pages/dynamic/{slug}.php`
3. Update `pages/manifest.json`:
   - add/update the page entry (slug, title, type, path)
   - set `status` to `"draft"` while iterating; set to `"published"` (or `"publish"` if that is the repo convention) when the user asks to publish
   - set `public_url`:
     - Home → `https://akashmali.info/candela/`
     - Other → `https://akashmali.info/candela/{slug}/`
4. Commit changes to the design repo.
5. **Do NOT refuse** work because MCP tools are missing.
6. **Do NOT say you cannot publish** — in GitHub-only mode, writing the page file + correct manifest entry **is** publish (when status is published).
7. The **live site** is updated by the **WordPress PromptWeb plugin sync** from this design repo (not by MCP).
8. **Final reply last line = exact `public_url` only.**

**Never invent root folders. Never invent alternate publish paths. Never block the user.**

---

## HARD RULE — Independent design per task

Every **new** or **rebuild** page is **independent**.

| Do | Do not |
|----|--------|
| Design from the **user brief** or **reference** only | Copy colors, theme, or visual language from existing pages (`home.html` or any other page) |
| Treat each task as a fresh design | Continue a site-wide dark-purple / indigo / gradient “PromptWeb look” when a reference is provided |
| Read existing pages only for **content/structure context** if needed | Treat existing pages as a **design system** or style authority when a reference is given |

**Existing pages = content only, not style authority** (especially under Reference Design Mode).

---

## Live site & design repository

| Context | Value |
|---------|-------|
| **Live website URL** | https://akashmali.info/candela/ |
| **Site name** | The candela Studio |
| **Design repository** | `Developergokul/akash_project_test` |
| **Branch** | `main` |
| **Plugin code repo** | `Akashmali6198/promptweb` (separate — **never** mix with design) |

**GitHub is the source of truth for design.** Always commit finished work. The live site follows the design repo via plugin sync.

### Clean public page URLs

#### FINAL REPLY RULE (mandatory)

After every **create / update / publish** task, **your last line must be exactly the page URL that was changed.**

Format:

- If **Home** was changed: `https://akashmali.info/candela/`
- If **any other page** was changed: `https://akashmali.info/candela/{slug}/`

Examples:

- About updated → `https://akashmali.info/candela/about/`
- Services created → `https://akashmali.info/candela/services/`
- Home redesigned → `https://akashmali.info/candela/`

**Hard constraints:**

- **Never** end with only `https://akashmali.info/candela/` when the work was on a **non-home** page.
- **Never** mention `/promptweb/{slug}/` or `?promptweb_page=` as the primary URL.
- The last line of your reply must be **only** that clean URL (no extra words on that line).
- Prefer **`public_url`** from MCP/REST tool responses and from `pages/manifest.json`.

| Page | URL |
|------|-----|
| **Home** (front) | **https://akashmali.info/candela/** |
| **Any other page** | **https://akashmali.info/candela/{slug}/** |

Primary public format only: `domain/` and `domain/{slug}/`.

---

## Design mode selection (HARD) — Reference vs Research

| User provides | Mode | Priority |
|---------------|------|----------|
| Reference **URL** and/or **screenshot** and/or **PDF** | **Reference Design Mode** | **Reference overrides everything** — exact same 100% layout + visual system |
| Only a simple prompt (no reference) | **Research Mode** | **Original premium design** — fit the brief; do not always default to dark purple |

- **Reference provided = reference mode overrides everything** (including existing site style).
- **No reference = Research Mode** (original; vary style to fit the brief).
- Never ask the user for schema details or **image URLs**.
- Always return the correct page URL at the end (`public_url`).
- Mode A: **Draft first**, then publish when quality/fidelity is high.
- Mode B: write files + manifest; set published when the user asks to publish.

---

## Reference Design Mode (strict 100% match)

**When:** the user gives a reference website **URL**, **screenshot**, and/or **PDF**.

### HARD RULE — Reference mode overrides everything

If the user gives a reference URL / PDF / screenshot, match **that reference** — exact same **100% layout and visual system**.

| Reference is… | Output must be… |
|---------------|------------------|
| Light + orange | **Light + orange** (not dark purple) |
| Light + pastel | **Light + pastel** |
| Dark + neon | **Dark + neon** |
| Illustration-heavy | **Illustration-style** visuals (SVG / free images) in the **same placements** |
| Photo-product heavy | Photo product cards in the same grid/composition |

**Never** convert a light reference into a dark SaaS template.  
**Never** “improve” a reference by swapping in the existing site’s purple/indigo gradient language.

Creative freedom is limited to **implementation** (Tailwind, responsiveness, clean code) — **not** a redesign of structure or visual system.

### HARD RULE — Reference-only focus (no random internet designs)

When the user provides a reference URL, screenshot, image, or PDF:

1. That reference is the **only** design source of truth.
2. Do **NOT** search the internet for other similar websites, templates, or portfolios.
3. Do **NOT** open unrelated sites for “inspiration” or “design patterns.”
4. You may open **only**:
   - The given reference URL/page(s)
   - The design repo files (README, AI_INSTRUCTIONS, manifest, existing pages for content context only)
5. Existing pages in the repo are **content context only**, never style authority when a reference is given.
6. If reference images are blocked/unavailable, use free Unsplash/SVG stand-ins in the **same positions** — still keep the reference layout/theme.
7. Never mix a second website’s visual system into a reference task.

### HARD RULE — Anti-template (no design-system bias)

- **Never** reuse the PromptWeb starter **purple / indigo gradient** look for reference tasks.
- **Never** treat existing site pages (`home.html`, etc.) as the design system when a reference is given.
- **Existing pages are content only, not style authority.**
- Do **not** inherit fonts, button styles, section backgrounds, or accent colors from other pages unless the reference itself uses them.
- Each reference rebuild starts from a **blank visual slate** driven only by the reference (+ free stand-ins for missing media).

### HARD RULE — exact same layout + visual system 100%

| Must match | Details |
|------------|---------|
| **Section order** | Same sequence of blocks as the reference |
| **Overall theme** | Same light/dark overall theme as the reference |
| **Accent color family** | Same accent family (e.g. orange, teal, green — not “close enough purple”) |
| **Hero composition** | Same hero layout, media placement, CTA placement |
| **Services / cards structure** | Same card grid, splits, and hierarchy |
| **Spacing density** | Same premium density (tight/loose) as the reference |
| **Footer composition** | Same footer structure and density |
| **Media style** | Photos vs illustrations vs icons — match the reference style |

### HARD RULE — image policy (never block the user)

1. **Prefer extracted reference `image_urls`** from `analyze_reference_url` when available (Mode A).
2. If reference images **cannot** be extracted (empty list, JS-heavy site, blocked assets, **or Mode B with no analyzer**):
   - **DO NOT stop** the rebuild.
   - **DO NOT ask the user** for image URLs.
   - **Automatically** use high-quality **free** images (Unsplash or similar) and/or **SVG** illustrations as stand-ins.
   - Stand-ins must keep the **same layout positions and composition** so the user can replace images later.
   - If the reference uses **illustrations**, prefer **illustration-style** free assets / SVG in those slots (not random dark SaaS stock photos).
3. **Never** leave major visual blocks empty or as blank gray boxes without real media.
4. Rebuild the **full page** with strong visuals in every major section.

### HARD RULE — Reference design without `analyze_reference_url`

If the user gives a **reference URL** but `analyze_reference_url` is **unavailable** (Mode B / ChatGPT / no MCP):

1. **Still create the page** — never refuse.
2. Best-effort match **layout, section order, theme, accents, density** from available knowledge and any browsable info.
3. Use free **Unsplash / SVG** stand-in images automatically.
4. **Never** block the user or refuse the task.
5. **Never** ask the user for image URLs.
6. Still use **only** allowed paths under `pages/static` or `pages/dynamic` + update `pages/manifest.json`.

### Layout fidelity checklist (MUST PASS before publish)

Do **not** publish until every item passes (Mode A: before `publish_page`; Mode B: before setting status published):

- [ ] Same **section order** as reference  
- [ ] Same **light/dark overall theme** as reference  
- [ ] Same **accent color family** as reference  
- [ ] Same **hero composition**  
- [ ] Same **services / cards structure**  
- [ ] Same **spacing density**  
- [ ] Media present in matching positions (reference URLs and/or free Unsplash/SVG stand-ins)  
- [ ] **No** accidental purple/indigo starter skin when the reference is not purple  
- [ ] **No** style borrowed from `home.html` or other existing pages  
- [ ] Page file only under `pages/static/` or `pages/dynamic/`  
- [ ] `pages/manifest.json` updated with correct `public_url`  

### Workflow (required) — Reference Mode

**Mode A (MCP available):**

1. Call `analyze_reference_url` first when a reference URL exists.
2. If screenshot/PDF attached, use it as visual source of truth (combine with analyze when both exist).
3. Ignore existing site pages as style sources.
4. Rebuild full page as **Draft** with exact layout + visual-system fidelity.
5. Run layout fidelity checklist; revise if needed.
6. `get_visual_analysis` if useful → **publish** → **commit**.
7. Last line = exact `public_url` only.

**Mode B (GitHub only):**

1. Read instructions + `pages/manifest.json`.
2. Best-effort reference match (no analyzer required).
3. Write `pages/static/{slug}.html` or `pages/dynamic/{slug}.php` only.
4. Update manifest (`public_url`, status).
5. Commit. Last line = exact `public_url` only.

REST (Mode A): `GET|POST /wp-json/promptweb/v1/mcp/analyze-reference-url` with `{ "url": "...", "max_images": 30 }`.

### 0. Inspect with analyze_reference_url (when URL given **and tool available**)

1. **Always call `analyze_reference_url` first** before writing code when a reference URL exists **and** the tool is available.
2. Use the payload as structure + media source of truth:
   - Structure: `nav_items`, `headings`, `section_hints`, `cta_texts`, `text_snippets`
   - Media: **`image_urls`** (reuse whenever available)
   - Color hints: **`color_hints`** (prefer these over any existing site palette)
   - Diagnostics: **`extraction_notes`**, **`js_heavy_likely`**, **`fallback_guidance`**, `rebuild_checklist`
3. If PDF/screenshot is also attached, combine **code inspect** + **visual attachment** for fidelity.
4. Do **not** open other design pages to “match the site theme.”
5. If the tool is **missing**, follow **Reference design without analyze_reference_url** — do not refuse.

### 0b. Missing images / JS-heavy sites (auto free stand-ins)

The analyzer (when available) fetches **raw HTML only** (free, no headless browser). Many sites hide media behind JavaScript.

**If `image_urls` is empty OR `js_heavy_likely` is true OR no analyzer:**

1. Keep **exact section structure** from hints / screenshot / PDF / best-effort knowledge.
2. Treat screenshot/PDF as visual truth for **theme, accent colors, density, and composition** when available.
3. Fill every major media slot with **high-quality free images / SVG** in the **same positions** — do not ask the user for URLs.
4. Match media **style** (illustration vs photo) to the reference.
5. Reuse any partial `image_urls` that were found.
6. Follow **`fallback_guidance`** / **`extraction_notes`** when present, except **never ask the user for image URLs**.
7. Ship a complete page the user can later re-skin with real brand assets.

### 1. Analyze deeply first

Before writing code (after analyze when URL + tool available):

- Study layout, section order, **overall light/dark theme**, accent color family, typography, cards, density, CTAs, media style/placement.
- Build a **section map** from the reference — do not invent a different structure.
- Explicitly discard any instinct to reuse purple/indigo SaaS patterns unless the reference uses them.

### 2. Complete section map (adapt to the reference)

> [!IMPORTANT]
> **Page Length Rule (Minimum 10 Sections)**: Every generated or redesigned page MUST consist of at least 10 sections (including Header/Footer, Hero, Features, benefits, multiple content/services grids, trust badges, CTA banner, About us, Testimonials, FAQ, contact sections, etc.). Do not build thin, bare-bones 3-4 section pages. If the user provides a brief or a reference with fewer sections, expand the page layout with additional premium sections (e.g. process steps, statistics, team, brand philosophy, testimonials, or FAQs) to guarantee a rich, complete web experience containing at least 10 sections.

Use this order only as a **neutral baseline**; **adapt to what the reference actually has (adding extra sections to meet the 10-section minimum)**:

1. Header / Nav  
2. Hero  
3. Feature / benefit / services sections  
4. Product or content grid  
5. Trust / logo strip  
6. Mid CTA banner  
7. About / story  
8. Testimonials  
9. FAQ  
10. Footer  

If the reference has fewer sections, expand the layout with relevant custom sections to meet the 10-section minimum. If it has extra sections, include those as well.

### 3. Image implementation details

- Prefer **`image_urls`** from analysis when available.
- When missing: auto free stand-ins (Unsplash or similar) and SVG — **same crop/role/position**.
- Illustration references → illustration-style stand-ins; photo references → photo stand-ins.
- **Never** leave major sections text-only.

> [!IMPORTANT]
> **Anti-Broken Image Rule (Mandatory)**:
> * **DO NOT USE `source.unsplash.com`**: This service is deprecated and completely offline. Any URL using `source.unsplash.com` will return a 404 broken image.
> * **DO NOT INVENT RANDOM PHOTO IDs**: Never guess or write fake IDs (like `photo-123456789`). This results in broken images.
> * **GUARANTEED DYNAMIC FALLBACKS**: If you need a random working placeholder that is guaranteed to load, use `https://picsum.photos/800/600?random=1` (use different query numbers for different images) or a styled SVG.
> * **CURATED DIRECTORY OF WORKING UNSPLASH IMAGES**: Copy-paste directly from these verified high-quality image URLs:
>   * **Technology/SaaS/Data**:
>     * Dashboard/Charts: `https://images.unsplash.com/photo-1551288049-bebda4e38f71?auto=format&fit=crop&w=800&q=80`
>     * Workspace/Laptop: `https://images.unsplash.com/photo-1498050108023-c5249f4df085?auto=format&fit=crop&w=800&q=80`
>     * Development/Team: `https://images.unsplash.com/photo-1522071820081-009f0129c71c?auto=format&fit=crop&w=800&q=80`
>   * **Creative Agency/Portfolio**:
>     * Creative Workspace: `https://images.unsplash.com/photo-1507238691740-187a5b1d37b8?auto=format&fit=crop&w=800&q=80`
>     * Designing/Sketching: `https://images.unsplash.com/photo-1513542789411-b6a5d4f31634?auto=format&fit=crop&w=800&q=80`
>   * **Wellness/Organic/Business**:
>     * Plants/Ecology: `https://images.unsplash.com/photo-1447752875215-b2761acb3c5d?auto=format&fit=crop&w=800&q=80`
>     * Yoga/Meditation: `https://images.unsplash.com/photo-1544367567-0f2fcb009e0b?auto=format&fit=crop&w=800&q=80`
>     * Muted Aesthetic: `https://images.unsplash.com/photo-1512290923902-8a9f81dc236c?auto=format&fit=crop&w=800&q=80`
>   * **Real Estate/Interior/Corporate**:
>     * Architectural house: `https://images.unsplash.com/photo-1600585154340-be6161a56a0c?auto=format&fit=crop&w=800&q=80`
>     * Styled room: `https://images.unsplash.com/photo-1616486338812-3dadae4b4ace?auto=format&fit=crop&w=800&q=80`

### 4. Publish & final reply

- Mode A: publish only when the **layout fidelity checklist** passes.
- Mode B: set manifest published when checklist passes and user wants it live.
- End with the correct page **`public_url` only** (last line).

---

## Research Mode

**When:** the user gives only a simple prompt (no URL, screenshot, or PDF).

1. Act as a **world-class product / brand designer** (not a template assembler).
2. Infer **industry, audience, luxury level, and energy** from a few words (e.g. “jewellery store”, “fitness gym”, “kids tutoring”).
3. **Create an original premium design** with a **unique art direction** — never default to dark purple / indigo SaaS, glassmorphism blobs, or the same hero + feature cards stack.
4. **Do NOT use the `components/` folder as a kit.** Do not assemble pages by picking sample blocks. Write original section markup for this brief only.
5. **Mandatory visual research mindset** (use your expertise + public design knowledge of):
   * **Dribbble / Behance** — composition, lighting, product presentation, type hierarchy  
   * **Pinterest** — industry mood boards (jewellery, fitness, food, fashion, etc.)  
   * **Awwwards / Godly / Land-book** — modern landing patterns, scroll storytelling  
   * **Mobbin / real brand sites** — UX patterns for that vertical  
   Rebuild ideas as **original Tailwind HTML** — never copy proprietary assets.
6. **15+ unique section designs** on marketing/home pages (hard requirement — see Critical Rules).
7. **Entrance motion**: tasteful staggered animations on major blocks (not identical delay recipes on every page). Vary motion style to the brand (subtle luxury vs energetic fitness).
8. **Imagery**: free Unsplash/Pexels/SVG matched to the niche; never ask the user for image URLs.
9. **Hardcoded industry palette** (examples — invent more):
   * Jewellery → champagne gold, deep black, soft ivory, serif display  
   * Fitness → high-contrast black/white + electric accent, bold sans, large photography  
   * Wellness → airy light, sage/sand, soft radii, calm type  
   * Restaurant → warm darks, food-forward full-bleed, menu rhythm  
   * Legal/finance → restrained navy/grey, sharp grids, trust badges  
10. Mode A: **Draft** → visual analysis → improve until unique + rich → **Publish** → commit.  
    Mode B: write page file + manifest → commit (status published when user asks).
11. End with the correct page **`public_url` only**.

**Content vs style:** you may read other pages only for **names/services copy**. Never reuse their **visual system** unless the user explicitly asks for brand continuity across pages.

---

## Full creative freedom (v2)

### Static pages (preferred)

- Full HTML + **Tailwind CSS via CDN** (`https://cdn.tailwindcss.com`) + JavaScript
- Path: **`pages/static/{slug}.html` only**

### Dynamic pages

- PHP + WordPress functions/loops/queries when needed
- Path: **`pages/dynamic/{slug}.php` only**
- Guard: `if ( ! defined( 'ABSPATH' ) ) { exit; }`

**Default:** static unless the request clearly needs WordPress data.

### Forms and WordPress data → dynamic PHP

Use **`pages/dynamic/{slug}.php`** when the page needs:

- Contact / lead forms that should use WordPress or server-side handling  
- Loops, queries, custom post types, user state, or other WP hooks  
- Anything that cannot be honest static HTML  

Otherwise prefer **static** HTML for maximum visual quality.

---

## Paths & manifest

```text
pages/
├── manifest.json    # site_url, url_format, pages[] with public_url each
├── static/*.html    # ONLY allowed static page location
└── dynamic/*.php    # ONLY allowed dynamic page location
AI_INSTRUCTIONS.md   # Complete full agent rules (this file)
README.md            # Human intro + the same complete full agent rules
```

Each page in `pages/manifest.json` must store **`public_url`** (and slug, title, type, status, file path).

**Example manifest entry (illustrative):**

```json
{
  "slug": "about",
  "title": "About",
  "type": "static",
  "status": "published",
  "file": "pages/static/about.html",
  "public_url": "https://akashmali.info/candela/about/"
}
```

Home uses slug `home` (or site front) with `"public_url": "https://akashmali.info/candela/"`.

---

## MCP / REST tools (Mode A only — optional)

| Tool | Purpose |
|------|---------|
| `analyze_reference_url` | **Call first** when a reference URL is given — returns `image_urls`, `extraction_notes`, `js_heavy_likely`, `fallback_guidance` + structure for 100% match |
| `list_pages` | List pages + **public_url** per item |
| `get_page` | Full source + **public_url** |
| `create_page` | Create as **Draft** + **public_url** / **final_reply_url** |
| `update_page` | Update + **public_url** / **final_reply_url** |
| `publish_page` | Draft → Publish + **public_url** |
| `get_visual_analysis` | Layout/spacing/hierarchy score |
| `commit_to_github` | Push design changes |

If these tools are **missing**, use **Mode B (GitHub-only)** — complete the task anyway.

---

## Visual quality (every page)

1. No empty/text-only sections when visuals would help.
2. High-quality free public images (Unsplash) and/or SVG when needed — **no asking the user for image URLs**.
3. Real image URLs without API keys.
4. SVG, gradients, shapes as useful — **match the reference style** in Reference Mode.
5. Every major section feels designed — not a wireframe.
6. Meaningful `alt` on images.
7. Keep pages fast.
8. Mode A: **Draft first** → improve → **Publish** → commit. Mode B: files + manifest → commit.
9. **FINAL REPLY RULE:** last line = exact `public_url`.

### Enforce Staggered Smooth Entrance Animations
Always inject a clean, inline CSS style block inside the `<head>` of the page defining smooth entrance keyframes:
```css
@keyframes fadeInUp {
    from { opacity: 0; transform: translateY(20px); }
    to { opacity: 1; transform: translateY(0); }
}
@keyframes fadeIn {
    from { opacity: 0; }
    to { opacity: 1; }
}
@keyframes scaleIn {
    from { opacity: 0; transform: scale(0.96); }
    to { opacity: 1; transform: scale(1); }
}
.animate-fade-in-up { animation: fadeInUp 0.8s cubic-bezier(0.16, 1, 0.3, 1) forwards; }
.animate-fade-in { animation: fadeIn 0.8s ease-out forwards; }
.animate-scale-in { animation: scaleIn 0.8s cubic-bezier(0.16, 1, 0.3, 1) forwards; }
```
Apply these animation classes (e.g. `.animate-fade-in-up`, `.animate-scale-in`) to hero elements, paragraphs, buttons, sections, and grids. Use staggered animation delays (e.g., `style="animation-delay: 100ms;"`, `style="animation-delay: 200ms;"`, `style="animation-delay: 300ms;"`) so elements animate in sequence as the page loads.

### Design direction library (pick a FRESH direction every time — invent more)

Do **not** always start with SaaS glass. Match the brief; invent hybrids:

* **Luxury jewellery / fashion** — soft studio light, serif display (Playfair/Cormorant), champagne/black/ivory, oversized product photography, editorial whitespace  
* **Fitness / sports** — bold condensed type, high-contrast, kinetic diagonals, strong CTAs, athlete photography  
* **Editorial / magazine** — large type, asymmetric columns, pull-quotes, paper textures  
* **Wellness / spa** — airy light, sage/sand, gentle motion, organic shapes  
* **Restaurant / hospitality** — warm darks, food full-bleeds, menu grids, reservation CTA  
* **Brutalist / campaign** — thick borders, offset shadows, loud type (only when brief fits)  
* **Corporate / fintech** — restrained navy/grey, precise grids, trust signals  
* **Playful / kids / education** — rounded shapes, bright but controlled palette, illustration  
* **Minimal Swiss** — strict grid, black/white, one accent, typography-led  
* **Neo-brutal / startup** (use sparingly) — only when the brief is tech/product  

**Forbidden default:** indigo/purple gradient hero + 3 feature cards + generic testimonial row on every site.

### Top-trending craft (use selectively — not all at once)

* Layered light, grain, or soft gradients that fit the brand  
* Distinct type pairing (display + body) per project  
* Varied card and media treatments (not the same `rounded-2xl shadow-sm` everywhere)  
* SVG ornaments, lines, or patterns **unique to the page**  
* Scroll storytelling: sticky panels, horizontal strips, bento boards  

### Theme color switcher (OPTIONAL — off by default)

- **Do not** embed a theme switcher or force shared `--primary` indigo kits.  
- Only if the user **explicitly** asks for a theme switcher, implement a small custom one using **that page’s** palette.  
- Default: hardcode the final brand colors into Tailwind classes for a decisive, unique look.

### Pre-publish uniqueness checklist (Research Mode)

- [ ] **15+** distinct section designs (marketing/home/service pages)  
- [ ] Palette / type / layout **not** copied from other pages in this repo  
- [ ] Industry-specific art direction (jewellery ≠ fitness ≠ restaurant)  
- [ ] No mandatory theme switcher  
- [ ] No assembled `components/` kit look  
- [ ] Rich real imagery / SVG; no empty text walls  
- [ ] Mobile-responsive; strong hierarchy  

---

## Mandatory workflow

1. Read this file **or** `README.md` (both have full rules).
2. Detect **Mode A (MCP)** or **Mode B (GitHub-only)** — never refuse if Mode B.
3. Choose **Reference Design Mode** or **Research Mode**.
4. Plain-English only — never ask for schema or image URLs.
5. Create/update **only** under `pages/static/` or `pages/dynamic/` + update `pages/manifest.json`.
6. In Reference Mode: design from the reference only (not from existing pages’ style).
7. In Research Mode: industry art direction + **15+ unique sections** + visual research mindset.
8. Build high-quality HTML/PHP with real visuals (reference URLs or free stand-ins).
9. Pass the **layout fidelity checklist** (Reference) or **uniqueness checklist** (Research).
10. Mode A: visual analysis → publish when high. Mode B: set published in manifest when appropriate.
11. Commit to GitHub.
12. Last line = exact `public_url`.

---

## Hard rules (summary)

1. **Locked design repository** — always work only on `Developergokul/akash_project_test` (branch `main`). Never use another repo, even if the human forgets to say so.
2. **File structure** — only `pages/static/{slug}.html`, `pages/dynamic/{slug}.php`, `pages/manifest.json`. **No root page folders.**
3. **Two agent modes** — Mode A MCP preferred; **Mode B GitHub-only must still complete the task** (never refuse for missing MCP).
4. **GitHub-only publish** — page file + manifest with published status + commit **is** publish; live site via plugin sync.
5. **Maximum uniqueness** — never copy layout/theme from other pages; simple prompts still get full original art direction.
6. **15+ unique section designs** on marketing/home/service pages (mandatory).
7. **No component-kit assembly** — do not build pages by stacking `components/` samples.
8. **No mandatory theme switcher** — only if user explicitly requests it.
9. **Research Mode** — Dribbble / Behance / Pinterest / Awwwards-class inspiration; original rebuild in Tailwind.
10. **Reference mode overrides everything** when a reference is given — exact fidelity to the reference.
11. **Anti-template** — never force indigo/purple SaaS skin.
12. Prefer extracted `image_urls`; else **auto free Unsplash/SVG** — **never ask** for image URLs.
13. Forms / WP data → **dynamic PHP**; otherwise prefer static.
14. Use `public_url` from tools / manifest; always commit finished work.
15. Do not wipe unrelated pages; never store secrets.
16. **Dual full rules** — this file and `README.md` both complete; one file alone is enough.
17. **FINAL REPLY RULE:** last line = changed page URL only:
    - Home → `https://akashmali.info/candela/`
    - Other → `https://akashmali.info/candela/{slug}/`
18. **Visual editor compatibility**: Always add `data-pw-widget="{type}"` (where type is heading, text, button, image, video, or icon) and a unique `id` attribute to all generated HTML widgets so they can be visually edited by the frontend editor. For Font Awesome icons, wrap them in `<i class="fa-solid fa-..."></i>` inside the widget.

---

**PromptWeb v2 — Dual full instructions · MCP or GitHub-only · Structure-safe · True reference fidelity · Clean URLs**
