---
name: anti-vibe-web-ui
description: >
  Audit and remove "vibe coded" web UI: the default visual signature an AI agent
  produces when nobody supplies direction (purple gradients, neon on dark,
  glassmorphism, glow blobs, emoji icons, card-inside-card layouts,
  fade-in-everything, invented social proof, missing legal/OG/favicon basics).
  Use when building or redesigning marketing sites, landing pages, product
  sites, docs, or any public-facing web page; when reviewing a PR, diff or
  screenshot that "looks AI generically"; or when the user wants a site that
  reads as intentionally designed rather than templated.
---

# Anti vibe web UI: ship something that was decided, not averaged

Vibe-coded UI has a look. It is not carelessness; it is a model optimizing for
statistical association. Asked for "modern", it returns what "modern" looked
like across millions of examples, applied regardless of product, audience or
brand. The result is an interface that looks like everything because it was
trained on everything: five colors shouting at equal volume, decoration that
communicates nothing, and content that never had to make a decision.

Your job with this skill is the opposite of that: make a few specific choices,
state them, and hold the line. Restraint, hierarchy and real product evidence
beat decoration every time. Removing tells is the *floor*, not the ceiling. A
site that passes all 40 checks with no point of view is still average.

**Scope:** mostly websites: landing pages, marketing and product sites, pricing,
docs, blogs, auth and onboarding pages, and the public surfaces of a web app.
Apply the same checks inside a dashboard, but keep genuine data affordances
(status dots, charts, dense tables) that carry real meaning.

## How to read the tables

- **`scan`** = findable with search. Run the grep in the audit section.
- **`eye`** = only visible on the rendered page. Look at it, or at a screenshot.
- **Instead** = the default replacement. Deviate when the brand, content, or
  real product evidence justifies it, not because it looks nicer in isolation.

Each row is a *tell*, not a banned construction. One occurrence can be a
deliberate choice. Three or more in the same category means the design was not
decided. Fix causes, not symptoms: if six cards each have a rainbow side bar,
the bug is that no one assigned a color budget for the page.

## 1. Color and surface

| # | Tell | Spot | Instead |
|---|---|---|---|
| 01 | Purple/violet gradient on black | `from-purple`, `via-violet`, `#7c3aed`, `#8b5cf6` on a dark bg | One brand color, flat or a two-tone gradient of the same hue. Purple only if the brand is purple. |
| 02 | Neon palette: cyan, lime, magenta on dark, all at full saturation | `cyan-400`, `lime-400`, `fuchsia-500`, `#00ffff` | Saturation from the brand palette; contrast from value, not from glow. |
| 03 | Framework indigo as the accent | `bg-indigo-500`, `bg-indigo-600`, `#6366f1`, `#4f46e5` | The brand color, contrast-tested on its own background. |
| 04 | Glowing borders and colored bloom in dark mode | `shadow-[0_0_`, `box-shadow: 0 0 20px` with a color, `ring-*/50` | 1px border one neutral step (10–15%) lighter than the surface. |
| 05 | Blurred color blobs behind the hero | `blur-3xl`, `blur-[100px]`, `blur-[120px]` on absolute colored divs | Nothing, or the product itself. Real UI is the hero image. |
| 06 | Glassmorphism on static chrome | `backdrop-blur-xl`, `bg-white/10`, `backdrop-filter` on sidebars, cards, sticky navs | Solid surface. Blur is for a modal scrim or a header floating over content, nowhere else. |
| 07 | Grain or noise over a gradient | `noise`, `grain`, `feTurbulence` | Drop the gradient, or use a real photo or illustration. |
| 08 | Dot grid or line grid wallpaper | `radial-gradient(` dot patterns, `bg-dot`, `grid-pattern` | Nothing, or a texture that belongs to the brand. |
| 09 | A different accent border on every card | `border-*-500` repeated across cards | Neutral borders. Color on the one card that matters. |
| 10 | Pure white page, white cards, no surface variation | `eye` | A tinted off-white, scaffold color, or one section that breaks the rhythm. |
| 11 | Same-hue stacking: colored icon in a tinted box on a tinted card | `bg-green/10` > `bg-green/20` > `text-green` | Neutral container, color only on the mark itself. |
| 12 | A color budget with no owner: five accents on one page | `eye`, count distinct accent hues | One dominant color, one accent, one neutral. Everything else is noise. |

## 2. Layout and hierarchy

| # | Tell | Spot | Instead |
|---|---|---|---|
| 13 | Big centered headline, subtitle, two equal buttons | `eye`: hero with `text-center` plus two CTAs | Left-aligned hero with the product visible above the fold, one primary action. |
| 14 | Three feature cards in a row, each an icon + title + two lines | `grid-cols-3` of icon/title/blurb | Show the thing working: a screenshot, a short loop, one feature per section with evidence. |
| 15 | Bento grid with tiles of identical weight | `grid-rows-*` with `col-span-2` / `row-span-2` tiles | Only when content genuinely differs in size. Otherwise a list, or a demo. |
| 16 | Cards inside cards inside cards | `eye`: bordered/filled box containing another | Flatten. Separate with spacing, weight and typographic scale instead of containers. |
| 17 | Everything in a card, including things that are not one object | `rounded-* border` on every block | Cards only for independently actionable objects. Most content needs no box. |
| 18 | A shadow under every card | `shadow-lg`, `shadow-xl` repeated | Elevation only for what actually floats: menus, dialogs, popovers. |
| 19 | Maximum radius everywhere | `rounded-2xl`, `rounded-3xl`, `rounded-full` throughout | One radius scale (e.g. 6px controls, 12px cards, 0 for full-bleed). Not the maximum on everything. |
| 20 | Icon parked in a tinted rounded square | `rounded-* bg-*/20 flex items-center justify-center` around an icon | Icon inline at the text's optical weight. The box adds nothing. |
| 21 | Rainbow side bars: a different left border color per block | `border-l-2 border-<color>` per card, colors cycling | No bar, or one accent bar used once. Four accents cancel each other out. |
| 22 | A vertical rhythm that changes per section | `py-16`, `py-20`, `py-24`, `py-32` mixed | One spacing scale, used consistently. |
| 23 | Left border plus radius on the same box | `border-l-2` with `rounded-*` | Pick one. A left rule implies square corners. |

## 3. Icons and symbols

| # | Tell | Spot | Instead |
|---|---|---|---|
| 24 | Emoji as navigation, bullets, headings or decoration | emoji characters in `h1`–`h3`, nav, lists, buttons | Emoji belong in conversational microcopy. Interfaces get an icon set with consistent stroke, size and meaning. |
| 25 | ✨ Sparkles to mean "AI" | `Sparkles`, `✨` | Say what the AI does in words, or show it doing it. |
| 26 | A default Lucide icon on every feature | `lucide-react` icon per card | Fewer icons. Real product visuals, or a small custom set with a point of view. |
| 27 | A green check before every line of a list | `Check` / `CheckCircle` with `text-green-*` in plain lists | A plain list. Checks are for comparison tables and validation results. |
| 28 | Status dots that encode nothing | colored dots on nav items, card headers, labels, titles | Every dot maps to a defined state, and the mapping is stated. If it needs a legend to be understood, it wanted a text label. |
| 29 | Hover scale or lift on non-interactive things | `group-hover:scale-110`, `hover:-translate-y` on icon wrappers and static tiles | Hover feedback only on things you can click, and through color, not size. The card's border change is enough. |

## 4. Typography

| # | Tell | Spot | Instead |
|---|---|---|---|
| 30 | The default stack: Inter, Geist, Space Grotesk, Poppins | font imports, `font-family` | A typeface chosen for this brand, with a scale and weights that were chosen too. Second family only for real contrast. |
| 31 | One italic serif word inside a sans headline | `Instrument Serif`, `DM Serif`, `Playfair`, `font-serif italic` mid-heading | One heading style. Emphasis through weight, size or color. |
| 32 | Gradient-clipped headline | `bg-clip-text text-transparent bg-gradient` | Solid text color. |
| 33 | Headline sizes that all shout | `eye`: h1 and h2 nearly the same size, everything 600+ | A real scale: one dominant size per page, clear steps down, weight doing less work than size. |
| 34 | Body text at low contrast or below 16px | `text-gray-400` on white, `text-xs` for paragraphs | 4.5:1 minimum on body text, 16px minimum on mobile, measure of 60–80 characters. |

## 5. Motion

| # | Tell | Spot | Instead |
|---|---|---|---|
| 35 | Fade-up entrance on above-the-fold content | `animate-fade-up`, `animate-slide-*` on visible elements | Content already on screen does not animate in. It is already there. |
| 36 | Scroll reveal on every section | `whileInView`, `aos`, `data-aos`, `IntersectionObserver` per section | Visible on load. Motion only where it explains a change the user caused. |
| 37 | UI transitions at 700ms or more | `duration-700`+, `duration: 1`, `ease-in-out` on hover | 150–250ms for UI state, 300ms at most. Never delay reading. |
| 38 | Animated counters for invented metrics | count-up libraries, `10,000+`, `10k+` | The real number, static, with its source. If there is no number, there is no section. |
| 39 | Reduced motion ignored | no `prefers-reduced-motion` rule | Honour it. Decor that cannot be turned off is a bug. |

## 6. Copy and content

| # | Tell | Spot | Instead |
|---|---|---|---|
| 40 | "It is not X, it is Y" staging | `not just`, `isn't about`, `ce n'est pas` | Say what it is, directly. |
| 41 | AI vocabulary: boost, revolutionize, unleash, seamless, effortless, supercharge | word list | Concrete verbs and the actual result. Numbers where a number exists. |
| 42 | Em dashes doing the work of sentence structure | `—` throughout the copy | Commas, colons, full stops. |
| 43 | A "New" pill above the title | `New` / `Nouveau` badge over `h1` | Only for a real launch, saying what is new and when. |
| 44 | Fake social proof: generic avatars, "John Doe", "Sarah K." | `pravatar`, `randomuser`, `unsplash` faces, invented names | Real quotes with name, role, and a link, or no testimonial section. |
| 45 | Three pricing tiers, "Most Popular" on the middle one | `Most popular`, `Popular` badge | The real offer. One plan is fine. Two is fine. |
| 46 | No evidence of the product anywhere above the fold | `eye`: no screenshot, video, demo, or real UI | Show it working, first screen, with real or realistic data. |
| 47 | Chart library defaults | `recharts`, `ChartContainer` with default palette and no axis labels | Brand colors, labelled axes, units, a source, and data that is not obviously fake. |
| 48 | A theme toggle nobody asked for | `ThemeToggle`, `Sun` / `Moon` in the header | Follow the system preference, or ship one theme done well. |

## 7. What is missing (the strongest tells)

Absences reveal more than presences. An AI builds what was asked for and stops;
a site that ships is finished, not generated.

| # | Missing | Spot | Add |
|---|---|---|---|
| 49 | Legal notice / imprint | no route or link matching `legal`, `imprint`, `mentions` | A real page with company details, placeholders marked for the owner. |
| 50 | Privacy policy | no `privacy` / `confidentialite` route, not linked from the footer or signup | A real page, linked where data is collected. |
| 51 | Real page titles | `Create Next App`, `Vite + React`, `React App` in `<title>` | `Product — what this page is` per page. |
| 52 | Own favicon | default `favicon.ico`, `vite.svg`, `next.svg`, `vercel.svg` | The product mark, plus an `apple-touch-icon`. |
| 53 | Open Graph image | no `og:image`, no `opengraph-image` | 1200×630 per page, with its title, verified in a card preview. |
| 54 | Working footer links | `href="#"`, `href=""`, links to routes that do not exist | Only links that resolve, or remove them. |
| 55 | Visible keyboard focus | `outline-none` with no replacement | A visible focus ring on every interactive element. |
| 56 | A real 404 and empty states | framework default error page, empty lists with no copy | A page that says what happened and where to go. |
| 57 | Speed | Lighthouse, Network tab, multi-MB hero video, unoptimized images, everything client-rendered | Compressed, sized images, lazy loading below the fold, server-rendered content. |

If the page is a marketing site and 49–57 are all absent, the design work is
irrelevant. Fix those first.

## Fix patterns

Tailwind shown because that is where these tells are most visible; translate
the intent for plain CSS or another system.

**Icon box → inline icon.** The container exists to add color, and it flattens
everything to the same weight.

```tsx
// before: a tinted box around every icon
<div className="flex h-8 w-8 items-center justify-center rounded-lg bg-green-500/20">
  <Code size={16} className="text-green-500" />
</div>

// after: the mark carries itself
<Code size={16} className="text-emerald-700" aria-hidden />
```

**Glass on static chrome → solid surface.**

```tsx
<div className="bg-white/50 backdrop-blur-xl">   // before
<div className="bg-neutral-950 border border-white/10"> // after
```

**Glow blobs → nothing, or the product.**

```tsx
// delete ambient decoration like this entirely
<div className="absolute -top-40 blur-[120px] bg-purple-600/30" />
// and let the hero carry a real screenshot, a real chart, or nothing
```

**Nested cards → one surface, divided by spacing.**

```tsx
<section className="border border-neutral-800 rounded-xl p-6">   // before
  <div className="border border-neutral-800 rounded-lg p-4">…</div>
</section>

<section className="max-w-2xl space-y-8">                        // after
  <div className="space-y-2">…</div>
  <div className="space-y-2">…</div>
</section>
```

**Rainbow accents → an assigned color budget.** Decide in one place which
things may carry accent color (primary action, active nav, one status), then
apply it everywhere and nowhere else. If a new element wants an accent, it has
to take one from the list.

**Entrance animation on first paint → remove.** Keep motion for transitions the
user causes (opening, sorting, submitting) and for progress that is genuinely
long. Delete `animate-fade-up`, `data-aos`, and `whileInView` from anything
visible on load.

**Status dot → labelled state, or delete.** If nothing changes state, remove the
dot. If something does, use text (`Operational`, `Degraded`) or a dot plus a
legend and a real `aria-label`.

**Centre-aligned hero with two CTAs → one action and evidence.**

```tsx
// before: title, subtitle, "Get started" + "Learn more", centered
// after: left column headline + one primary CTA + real product screenshot
```

## Do not overcorrect

This is where most "anti-vibe" passes make things worse. The goal is
intentionality, not austerity, and not a new default look.

- **Brand color wins.** A purple brand should use purple. The tell is purple
  because it is shorthand for "tech", not purple because it is the brand.
- **Dark mode is fine.** So are gradients, glass and glow when a specific
  element responds to the user. The tell is ambient decoration with no meaning.
- **Serif is fine** in editorial contexts. So are emoji in conversational
  microcopy, and a shadow on a dialog.
- **Do not flatten everything to black on white with one accent and a system
  font.** An austere, undifferentiated site is still undifferentiated. Keep
  whatever specific, brand-true detail already exists.
- **Do not invent proof.** Never write a testimonial, a customer name, a logo
  wall, a statistic, or a metric. Remove the section, or leave a clearly marked
  placeholder for the owner.
- **Keep the existing stack.** Fix within the project's components, tokens and
  fonts. Do not swap the UI library, add a design system, or introduce new
  dependencies as part of an anti-vibe pass.
- **Preserve function.** Never remove a control, label, `aria-` attribute, or
  state that carries meaning in order to make something look calmer.

## Workflow

### 1. Establish intent before touching pixels

Read the page and the repo, then write down, in one or two lines each:

- what the product does, for whom, in the user's words;
- the one job each page has (sign up, understand the offer, read the docs);
- the brand: existing color, type, voice, logo, if any exist;
- the evidence available: screenshots, a demo, real numbers, real customers.

Every fix below is judged against that. If there is no brand and no evidence,
say so and ask, or choose one explicitly and report the choice. Do not fill the
gap with decoration.

### 2. Scan

Run the searches in the audit section, grepping only the app's source (not
`node_modules`, generated output, or lockfiles). Collect a list of file and line
hits per tell. Grep finds the mechanical tells; it cannot tell you whether a
choice was intentional.

### 3. Look at the rendered page

Grep cannot see the page. Load it (dev server, preview, or the screenshot the
user provided), dismiss the cookie banner first or you will spend the whole
review looking at a consent dialog, and check the things only an eye catches: the hero above the
fold, the number of competing accent colors, whether cards nest, whether there
is any evidence the product exists, whether spacing changes section to section.
Do this at one desktop and one mobile width. Report what you saw; do not claim
a visual check you did not perform.

### 4. Prioritize

Work in this order, and finish a category before moving to the next:

1. **Missing pieces** (49–57): legal, privacy, titles, favicon, OG, focus, 404.
2. **Proof and hero** (13, 46): can a stranger tell what this is and see it work?
3. **Hierarchy and color budget** (12, 33, 09, 21): one dominant, one accent.
4. **Surfaces and decoration** (04–08, 16–20): remove what communicates nothing.
5. **Typography, motion, copy** (30–48): last, because they are the cheapest to
   change and the least structural.

### 5. Fix in small, reviewable diffs

One category, or one repeated pattern, per change. When the same wrong pattern
appears in ten components, fix the shared component, not ten call sites. Prefer
editing existing classes and tokens over rewriting markup. If a fix needs
content you do not have (a real metric, a real quote, a legal entity), leave a
marked TODO and list it in the report rather than inventing it.

### 6. Verify

- Typecheck / build the project with its own command if the change touched code.
- Reload the page at desktop and mobile width and confirm the sections still
  read, nothing overflowed, and no spacing collapsed.
- Tab through the page: focus visible everywhere, order sensible.
- Confirm you did not remove a `label`, `alt`, `aria-` attribute, or state.
- Check the largest image or video on the page is not multi-megabyte.

Do not claim a Lighthouse score, a before/after visual improvement, or a
performance win you did not measure.

## Audit commands

Run from the project root. Adjust the paths to the app source, and scope the
scan to your own markup: consent managers (Cookiebot, OneTrust), chat widgets
and analytics inject `href="#"`, emoji and inline styles that are not your
design, and will produce phantom dead links on every run.

```bash
# color and surface tells
rg -n "from-purple|via-violet|#7c3aed|#8b5cf6|bg-indigo-5|bg-indigo-6|#6366f1|#4f46e5" --glob '!node_modules'
rg -n "cyan-400|lime-400|fuchsia-500|#00ffff" --glob '!node_modules'
rg -n "shadow-\[0_0_|box-shadow: 0 0 [0-9]" --glob '!node_modules'
rg -n "blur-3xl|blur-\[[0-9]+px\]" --glob '!node_modules'
rg -n "backdrop-blur" --glob '!node_modules'
rg -n "bg-clip-text|bg-gradient-to" --glob '!node_modules'
rg -n "noise|grain|feTurbulence|bg-dot|grid-pattern" --glob '!node_modules'

# layout tells
rg -n "rounded-lg bg-.*\/[0-9]+ flex items-center justify-center" --glob '!node_modules'
rg -n "grid-cols-3" --glob '!node_modules'
rg -n "col-span-2|row-span-2" --glob '!node_modules'
rg -n "border-l-2|border-l-4" --glob '!node_modules'
rg -n "shadow-lg|shadow-xl" --glob '!node_modules'

# icons, symbols, motion
rg -n "Sparkles" --glob '!node_modules'
rg -n "group-hover:scale|hover:scale|hover:-translate-y" --glob '!node_modules'
rg -n "whileInView|data-aos|animate-fade-up|animate-slide" --glob '!node_modules'
rg -n "duration-(700|1000)" --glob '!node_modules'
rg -n "[\x{1F300}-\x{1F5FF}\x{1F600}-\x{1F64F}\x{1F680}-\x{1F6FF}\x{2600}-\x{27BF}]" --glob '!node_modules'

# fonts and copy
rg -n "\b(Inter|Geist|Poppins)\b|Space Grotesk|Instrument Serif|Playfair" --glob '!node_modules'
rg -n "not just|isn't just|revolutioniz|supercharge|unleash|seamless|effortless" --glob '!node_modules'
rg -n "Most popular|pravatar|randomuser|John Doe" --glob '!node_modules'

# the missing pieces
rg -n "Create Next App|Vite \+ React|React App" --glob '!node_modules'
rg -n "vite.svg|next.svg|vercel.svg" --glob '!node_modules'
rg -n "og:image|opengraph-image" --glob '!node_modules'
rg -n "href=\"#\"" --glob '!node_modules'
rg -n "outline-none" --glob '!node_modules'
```

Then check by hand, because grep cannot: favicon and apple-touch-icon exist,
`/privacy` and a legal route resolve, a 404 renders, `<title>` is per-page,
dark mode respects the system preference, and `prefers-reduced-motion` is
handled.

## Report format

When auditing without a mandate to rewrite, return:

1. **Verdict**, two sentences: what this page is, and whether it reads as
   intentionally designed or as a default.
2. **Blocking** (49–57): the absent pieces, each with the file or route to add.
3. **Tells found**, grouped by category, with file and line and the specific
   replacement. Rank by how much each one costs comprehension or trust, not by
   how easy it is to fix.
4. **What to keep**: the brand-true, specific, or genuinely functional choices
   that must survive the cleanup.
5. **Needs the owner**: anything that cannot be fixed without real content
   (legal entity, real metrics, real customers, brand assets).

When you do have a mandate, make the fixes, then report what changed, what you
verified, and what remains blocked on content.

## Provenance

Synthesized for web work from three sources:

- Melvynx, `shared-skills/skills/anti-vibecode/references/signs.md`: the 43-sign
  detection model and the scan/eye split.
- Jeff Humble, The Fountain Institute, "7 Signs a UI Has Been Vibe Coded":
  the statistical-average explanation, the color budget and card-nesting
  reasoning, and the point that the real tell is having no point of view.
- Wayne Sutton, `finder9/.codex/skills/anti-vibe-code/SKILL.md`: the Tailwind
  fix patterns, the audit greps, and the pre-ship checklist framing.

Rows marked `eye` cannot be automated. A green scan is not a design review.
