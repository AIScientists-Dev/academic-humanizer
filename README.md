<div align="center">

# Academic Humanizer

**Strip the tells of AI writing from papers and grant proposals — without flattening the precise,
evidence-bound voice that scholarship requires.**

[![license](https://img.shields.io/badge/license-MIT-2f8f57?style=flat-square)](LICENSE)
&nbsp;![version](https://img.shields.io/badge/version-0.3.0-2f8f57?style=flat-square)
&nbsp;![Claude Code](https://img.shields.io/badge/Claude_Code-skill-1c1a15?style=flat-square)
&nbsp;![scope](https://img.shields.io/badge/scope-papers_·_theses_·_NSF_·_NIH-555?style=flat-square)
&nbsp;![provenance](https://img.shields.io/badge/built_by-NSF,_CAREER,_NIH_R01_funded_researchers-444?style=flat-square)

</div>

> Built and field-tested by an academic research group whose work is supported by the U.S. National
> Science Foundation (including an NSF CAREER award) and the National Institutes of Health (R01). It
> distills the manuscript and grant practice that gets papers accepted and proposals funded.

## See it work

> [!CAUTION]
> **Before** — AI-generated, every tell present.
>
> In recent years, continual learning has attracted increasing attention and achieved remarkable
> success. However, existing methods still face crucial challenges. In this proposal, we propose a novel
> framework that leverages cutting-edge techniques to delve into these intricate problems, paving the way
> for a transformative paradigm that will revolutionize the field.

> [!TIP]
> **After** — academic-humanized; in proposal mode the vision stays, the tells go.
>
> Existing continual-learning methods, though promising, are largely empirical, with unclear principles
> underpinning their behavior — which limits their reliability and further progress. This proposal
> builds a principled framework that unifies adaptation, soft supervision, and cross-domain knowledge
> through coupled theory and algorithm design, demonstrated on autonomous driving and network management.

**More before/after passes** — a general example, an NIH Specific Aims page, and a funded NSF CAREER
summary: [`examples/before-after.md`](examples/before-after.md).

---

General "humanizers" are tuned for blogs and encyclopedic text. Academic Humanizer is built for
manuscripts and proposals:

1. **Strips academic-specific AI tells** — "paves the way", "extensive experiments", "to the best of
   our knowledge", "In recent years … has attracted increasing attention", Moreover/Furthermore
   overuse, contribution-list clichés, citation dumping, hedging-by-vagueness — on top of the general
   AI vocabulary (delve, underscore, tapestry), copula avoidance, rule-of-three, and em-dash overuse.
2. **Enforces a claim↔evidence discipline** — every empirical claim must earn a number, figure, or
   citation, and no verb may be stronger than its evidence (`prove` → `show empirically`); magnitudes
   become ranges attributed to their method, metric, and baseline.
3. **Preserves legitimate scholarship** — evidence-tied hedging (`suggests`, `is consistent with`,
   `we hypothesize`), appropriate passive voice, `we`, definitions, symbols, and **every citation**.
   It never invents or alters a number, equation, or citation.
4. **Handles funding proposals as a distinct mode** — NSF (Project Summary with the Overview /
   Intellectual Merit / Broader Impacts heads; vision → goal → gap → thrusts → payoff) and NIH (the
   one-page Specific Aims arc). A proposal is sold on **vision plus feasibility**, so it *keeps* the
   ambition language a paper would trim and instead enforces **claim ↔ feasibility**, with the heaviest
   editing on the first pages — the part every reviewer reads and scores.

## Install

```bash
git clone https://github.com/AIScientists-Dev/academic-humanizer ~/.claude/skills/academic-humanizer
```

## Use

```
/academic-humanizer
[paste a section, or point at main.tex]
# optionally: "match my voice from prior_paper.pdf; target venue: ICLR"
```

## How it works

Six layers — general AI-tell catalog → academic-specific tells → preserve scholarly conventions →
claim↔evidence matching → voice/venue calibration → funding-proposal mode (NSF/NIH structure,
first-page primacy, claim↔feasibility). The audit→rewrite loop is defined in [`SKILL.md`](SKILL.md).

## References

Layer 6 distills the *stable* structure of NSF and NIH proposals. For current, binding requirements
(page limits, formatting, deadlines), consult the source:

- NSF — [Proposal & Award Policies & Procedures Guide (PAPPG)](https://www.nsf.gov/policies/pappg)
- NSF — [CAREER program](https://new.nsf.gov/funding/opportunities/career-faculty-early-career-development-program)
- NIH — [Write Your Application](https://grants.nih.gov/grants/how-to-apply-application-guide/format-and-write/write-your-application.htm) (Specific Aims, Significance, Innovation, Approach)

## Acknowledgments

- **[blader/humanizer](https://github.com/blader/humanizer)** (MIT) — *focus:* removing general
  AI-writing patterns for blog, casual, and encyclopedic text. This skill reuses its general AI-tell
  catalog (Layer 1) and extends it for academic prose.
- **[koaeraser/ARMS](https://github.com/koaeraser/ARMS)** — *focus:* an autonomous pipeline for
  statistics/methodology research papers (idea → validated, revised manuscript). A complementary,
  broader-scope project that informed the claim-evidence and numerical-precision emphasis here.

This skill is the narrower piece: a single-purpose **editing pass** that de-AI-ifies existing academic
prose and matches claims to evidence while preserving scholarly voice.

## License

MIT.
