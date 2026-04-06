# nv:context Landing Page — Build Plan

**Goal:** Convert HN/X visitors into installs in 5 seconds.
**Timeline:** Build today (Monday), ship before Tuesday morning launch.
**Method:** Use nv:design to extract a reference DS, then build section-by-section.
**Total estimated time:** 2-3 hours.

---

## Why a Landing Page Matters

Current install funnel:
```
HN/X post → GitHub repo → README scroll → install command
```

With landing page:
```
HN/X post → landing page → instant before/after demo → install command
```

The README is text. A landing page can show the **before/after of a real production repo** in 5 seconds. That's the difference between "interesting" and "I need this now."

**Bonus:** The page itself becomes a proof point for **nv:design**. We can say "I built this in 90 minutes using nv:design. Here's the source." This is dog-fooding the entire collection.

---

## The Killer Hook

The selectools case study is the perfect demo. Hero section concept:

```
┌──────────────────────────────────────────────────┐
│                                                  │
│   440 lines → 67 lines (-85%)                    │
│   17,000 tokens → 2,000 tokens                   │
│   L3 → L5-L6 maturity                            │
│   58/60 leverage score                           │
│                                                  │
│   I applied nv:context to selectools             │
│   (a 4,612-test Python SDK).                     │
│   These are the real numbers.                    │
│                                                  │
│   [npx skills add johnnichev/nv-context -g -y]   │
│   [Read the case study]                          │
│                                                  │
└──────────────────────────────────────────────────┘
```

The numbers are visceral. They speak before any prose.

---

## Page Structure (8 sections)

### 1. Hero
- **Headline:** "Context engineering for engineers who ship"
- **Subheadline:** The selectools numbers (440 → 67, 58/60, etc.)
- **Primary CTA:** Install command (one-click copy)
- **Secondary CTA:** "See the case study" → scroll to section 2
- **Visual:** Animated counter or before/after toggle showing CLAUDE.md size collapse

### 2. Production Proof (the most important section)
Three case study cards side-by-side:

| Card | Headline | Numbers |
|------|----------|---------|
| **selectools** | Python SDK with 4,612 tests | L3 → L5-L6, 49/60 → 58/60, CLAUDE.md -85%, tokens -53% |
| **saas-platform** | Multi-product AI SaaS | L4 → L6, 17/60 → 49/60, SESSION.md -93% (saved 15.8K tokens/session), 81 bugs found |
| **sheriff** | Python + TypeScript | L4 → L5, 36/60 → 42/60, incremental polish on already-strong setup |

Each card has: project description, before/after numbers, "Read full case study" link.

### 3. The Problem
The 5 research findings as data points:

| Finding | Source |
|---------|--------|
| Auto-generated configs reduce success by 3% | ETH Zurich |
| Experienced devs are 19% slower with bad AI context | METR Study |
| 40%+ of AI project failures stem from poor context | IntuitionLabs |
| Using 40% of context window outperforms using 90% | Dex Horthy |
| Focused 300-token context beats unfocused 113K tokens | FlowHunt |

**Punchline:** "Bad context doesn't just not help — it actively hurts."

### 4. The 8 Laws
Clean grid of the 8 core laws with one-sentence explanations:

1. **Less is more** — every line competes with the actual task
2. **Landmines, not maps** — document what agents can't discover
3. **Commands beat prose** — snippets over paragraphs
4. **Context is finite** — 150-200 instructions max
5. **Progressive disclosure** — layer by need
6. **Hooks for determinism** — 100% compliance for critical rules
7. **Negative instructions backfire** — say MUST, not don't
8. **Compact proactively** — 60% safe, 85% hallucinating

### 5. What Gets Generated
Visual file tree with annotations:

```
your-repo/
  AGENTS.md                    ← Universal (25+ AI tools)
  CLAUDE.md                    ← Claude-specific, @imports
  tests/CLAUDE.md              ← Testing scope
  src/CLAUDE.md                ← Source scope
  HANDOFF.md                   ← Session handoff template
  .claudeignore                ← Token budget protection
  .claude/settings.local.json  ← Hooks (auto-format, branch protect, PostCompact)
  .github/workflows/
    learn-from-reviews.yml     ← Compounding engineering
```

Each item is a small tooltip card with "what it does" + "why it matters."

### 6. The Hierarchy of Leverage
Interactive (or animated) version of the scoring framework. Show a sample score with bars filling:

```
Verification        ████████░░  8/10
CLAUDE.md quality   ████████░░  8/10
Hooks               ██░░░░░░░░  2/10  ← biggest gap
Skills              ████████░░  8/10
Subagent patterns   ░░░░░░░░░░  0/10
Session management  ████████░░  8/10
                    ─────────
Overall             34/60
```

With "Top recommendation: Set up hooks → +14 points → 48/60"

### 7. The Research
- "12 documents · 471KB · 200+ sources"
- Logos/names of sources: Anthropic, ETH Zurich, Google DeepMind, Manus, GitHub, Boris Cherny, Dex Horthy
- Link to the research/ folder

### 8. Install + Final CTA
Big copy-paste install command:

```bash
npx skills add johnnichev/nv-context -g -y
```

Then: "Or install all 4 nv: skills" → 4 commands listed.

---

## Tech Stack

- **Pure HTML/CSS/JS** (no framework) — fastest to build with nv:design, fastest to load
- **CDN libraries:** GSAP for animations, ScrollTrigger for scroll effects
- **Hosting:** Vercel (free, fast, custom domain support)
- **Domain:** `nvcontext.dev` or `nvskills.dev` ($10/year — buy today)

## Reference Sites to Extract DS From

Pick ONE of these to download and extract design system from:

1. **vercel.com** — clean dark, great typography, animation tradition
2. **linear.app** — minimal, premium feel, perfect for dev tools
3. **resend.com** — developer-focused, clean, lots of code blocks
4. **railway.app** — bold colors, developer-targeted

**My pick:** Linear or Resend. Both are designer-favorites for dev tool landing pages. Both have great DS that nv:design will extract well.

---

## Build Workflow (using nv:design)

### Step 1: Download reference site (10 min)
- Go to sd.asimov.academy (Site Downloader)
- Paste the URL of chosen reference (linear.app or resend.com)
- Download the HTML + assets to `~/projects/nv-context-landing/reference/`

### Step 2: Extract design system (10 min)
```bash
cd ~/projects/nv-context-landing
git init
# Copy reference into folder
# Run /nv-design in Claude Code:
"Extract the design system from reference/index.html"
```

This produces `design-system.html` — your visual DNA.

### Step 3: Build sections one at a time (90 min)
For each of the 8 sections:
```
"Using the design system, build the [hero/proof/problem/etc.] section
for nv:context. Content: [paste the section content from this plan]"
```

Review, refine 2-3x, git commit, next section.

### Step 4: Polish (15 min)
- Mobile responsive check (375px, 768px, 1024px)
- All animations work
- All links functional
- Install commands copy-able
- Open Graph meta tags for social sharing

### Step 5: Deploy (15 min)
```bash
# Push to GitHub
gh repo create johnnichev/nv-context-landing --public --source=. --push

# Connect to Vercel
vercel
# Follow prompts, deploy
```

### Step 6: Domain (10 min)
- Buy `nvcontext.dev` or `nvskills.dev` from any registrar (Cloudflare Registrar = cheapest)
- Add CNAME in DNS pointing to `cname.vercel-dns.com`
- Add domain in Vercel project settings
- HTTPS auto-provisioned

**Total: 2.5 hours from start to live URL.**

---

## Content Already Written (Copy-Paste Ready)

### Hero Headline
> Context engineering for engineers who ship.

### Hero Subheadline
> Most agent failures aren't model failures. They're context failures.
> nv:context fixed selectools (440-line CLAUDE.md → 67 lines, L3 → L5-L6) and saas-platform (saved 15,800 tokens per session). Yours next.

### CTA Button Text
> Install in 30 seconds

### CTA Code Block
```bash
npx skills add johnnichev/nv-context -g -y
```

### Problem Section Headline
> Bad context doesn't just not help. It actively hurts.

### Solution Section Headline
> nv:context applies 200+ research sources to set up your repo correctly. In under 3 minutes.

### Final CTA Headline
> Stop fighting your AI agent. Start engineering its context.

---

## Open Graph Meta Tags (for social sharing)

```html
<meta property="og:title" content="nv:context — Context engineering for engineers who ship">
<meta property="og:description" content="I applied this to selectools (4,612 tests) and reduced the CLAUDE.md from 440 lines to 67 (-85%). Production-tested context engineering setup.">
<meta property="og:image" content="https://nvcontext.dev/og-image.png">
<meta property="og:url" content="https://nvcontext.dev">
<meta name="twitter:card" content="summary_large_image">
```

Need to create `og-image.png` (1200x630) — should show the selectools numbers prominently.

---

## What NOT to Do

1. **Don't over-design.** This is a launch page, not a portfolio. Clean > clever.
2. **Don't hide the install command.** It should be visible without scrolling.
3. **Don't add a video.** Engineers skim. Video is too slow.
4. **Don't use stock photography.** Either no images or screenshots of real terminal output.
5. **Don't skip the production proof section.** It's the most important conversion driver.
6. **Don't gate anything.** No email signup, no "join waitlist." Just install command.
7. **Don't add navigation menu.** Single-page scroll only. No distractions.

---

## Success Criteria

The landing page is good if:
- A visitor can install the skill in <30 seconds without scrolling past the hero
- The selectools numbers are visible above the fold
- "Bad context hurts you" is communicated within 5 seconds
- Mobile loads in <2 seconds
- Lighthouse score >90 across all categories

---

## Decision Point: Domain Name

Three options:

| Domain | Pros | Cons |
|--------|------|------|
| **nvcontext.dev** | Specific to the skill, easy to remember | Locks in if we want broader brand |
| **nvskills.dev** | Covers all 4 nv: skills, future-proof | Less specific to nv:context launch |
| **No custom domain (use Vercel default)** | Free, instant | Looks less professional |

**My pick:** `nvskills.dev` — covers the full collection and you can have `nvskills.dev/context`, `nvskills.dev/dev`, etc. as paths for each skill later. Most flexible.

---

## After Launch: Iteration Plan

**Week 1:** Just monitor analytics (Vercel built-in)
- Bounce rate (target: <60%)
- Time on page (target: >30s)
- Install command click rate (target: >20%)

**Week 2:** Iterate based on data
- If bounce rate high → simplify hero
- If time on page low → cut content, focus
- If click rate low → make install command more prominent

**Week 3+:** Add more case studies as users contribute their own
