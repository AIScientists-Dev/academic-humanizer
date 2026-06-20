# Academic Humanizer

Remove the signs of AI-generated writing from **academic** manuscripts — papers, theses,
rebuttals, grant proposals — **without** flattening the precise, neutral, evidence-bound voice that
scholarship requires.

General "humanizers" are tuned for blogs and encyclopedic text. Academic Humanizer is built for
manuscripts:

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

Five layers — general AI-tell catalog → academic-specific tells → preserve scholarly conventions →
claim↔evidence matching → voice/venue calibration. The audit→rewrite loop is defined in
[`SKILL.md`](SKILL.md).

## Acknowledgments

- **[blader/humanizer](https://github.com/blader/humanizer)** (MIT) — *focus:* removing general
  AI-writing patterns for blog, casual, and encyclopedic text. This skill reuses its general AI-tell
  catalog (Layer 1) and extends it for academic prose.
- **[koaeraser/ARMS](https://github.com/koaeraser/ARMS)** — *focus:* an autonomous pipeline for
  statistics/methodology research papers (idea → validated, revised manuscript). A complementary,
  broader-scope project that informed the claim-evidence and numerical-precision emphasis here.

This skill is the narrower piece of that landscape: a single-purpose **editing pass** that de-AI-ifies
existing academic prose and matches claims to evidence while preserving scholarly voice.

## License

MIT.
