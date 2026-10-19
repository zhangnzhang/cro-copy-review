# cro-copy-review

English | [简体中文](README.zh-CN.md)

An AI skill that reviews website and marketing copy the way a conversion copywriter would: a 10-dimension score out of 100, the 3 issues costing you the most conversions, and paste-ready rewrites for each.

Works with Claude (as a Skill) and any other agent that can read a Markdown instruction file.

## What you get

Give it a headline, a product description, a CTA button, an FAQ, a pop-up or an email, and it returns:

- **A scorecard** across 10 dimensions — Hook & Headline, Benefit > Feature (weighted highest), Emotional Resonance, Specificity, Voice of Customer, Rhythm & Readability, Trust & Social Proof, CTA Clarity, Framework Application, Comparison & Metaphor — each with a one-line diagnosis.
- **Top 3 conversion killers**, each with the exact quote, why it hurts, and a rewrite you can paste.
- **An optional full rewrite** and **up to 3 next steps** (including A/B tests with both variants written out).
- **A quick-scan mode** — 30 yes/no checks when you only want "the main problems".

See a full [sample review](examples/sample-review.md).

## Why it's different from "make this copy better"

- **Every judgement is anchored.** Each dimension has written scoring anchors (what a 10, 6 or 2 looks like), so scores are consistent and arguable.
- **It cites, it doesn't vibe.** A built-in evidence library — Nielsen Norman Group, Baymard, CXL, Copyblogger, Moz/Conductor, PowerReviews, Northwestern's Spiegel Research Center, VWO and Unbounce tests, and more — lets it explain *why* a change matters instead of giving generic advice. Every figure carries its source and a confidence tier.
- **It won't fake proof.** When a rewrite needs a rating, a customer count or a testimonial, it writes `[real review count]` instead of inventing one.
- **It respects your brand voice.** Deliberate style choices (fragments, one-word sentences, playful Q&A) aren't penalized as "bad rhythm".

## Install

**Claude:** copy `skills/cro-copy-review/` into `~/.claude/skills/` (or your project's `.claude/skills/`). Then:

> Review this hero copy for conversion: "…"

**Other agents:** point the agent at `skills/cro-copy-review/SKILL.md` as its instructions; the reference files are loaded on demand.

## Files

```
skills/cro-copy-review/
├── SKILL.md                    # The workflow, output template and ground rules
└── references/
    ├── dimensions.md           # Scoring anchors for each of the 10 dimensions
    ├── evidence.md             # Research findings and published tests, with sources and confidence tiers
    ├── examples.md             # Frameworks, feature→benefit and CTA libraries, anti-patterns
    └── checklist.md            # 30-point quick scan
examples/
└── sample-review.md            # A full worked review
```

## Sources and honesty

Every figure in [`evidence.md`](skills/cro-copy-review/references/evidence.md) names its source and a tier: **A** (checked against the original), **B** (published source linked), or **C** (reported, original not located — the skill must say "reported"). The skill is told to state what each study measured and never to treat a published result as a forecast for your site. Frameworks and examples are labeled as such. Spotted a claim that needs a better source? Open an issue.

## License

[MIT](LICENSE)
