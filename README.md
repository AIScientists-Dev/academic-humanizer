# Academic Humanizer

> By **AIScientists-Dev** (Jie Ding et al.) · github.com/AIScientists-Dev/academic-humanizer

A Claude Code / OpenCode skill that removes signs of AI-generated writing from **academic**
manuscripts (papers, theses, rebuttals, grants) **without** flattening the precise, neutral,
evidence-bound voice that scholarship requires.

It is a **fork of [blader/humanizer](https://github.com/blader/humanizer)** (which is excellent
for general/Wikipedia/blog text) with an added **academic layer**:

- **Claim ↔ evidence matching** — every empirical claim must earn a number, figure, or citation,
  and no verb may be stronger than its evidence (`prove` → `show empirically`).
- **Academic AI tells** — removes "paves the way", "extensive experiments", "to the best of our
  knowledge", "In recent years … has attracted increasing attention", Moreover/Furthermore overuse,
  contribution-list clichés, citation dumping, hedging-by-vagueness.
- **Preserves legitimate scholarship** — evidence-tied hedging (`suggests`, `is consistent with`,
  `we hypothesize`), appropriate passive voice, `we`, definitions, symbols, and every citation.
- **Voice + venue matching** — matches the author's prior papers and the target venue's register.

## Install

```bash
git clone https://github.com/AIScientists-Dev/academic-humanizer ~/.claude/skills/academic-humanizer
```

## Use

```
/academic-humanizer
[paste a paper section, or point at main.tex]
# optionally: "match my voice from paper_prior.pdf; target venue: ICLR"
```

## Acknowledgment & license

MIT, © **AIScientists-Dev** (Jie Ding et al.). Builds on **blader/humanizer** (MIT) and Wikipedia's *Signs of AI writing*
(WikiProject AI Cleanup, CC BY-SA). The academic layer, claim–evidence discipline, and
venue/voice calibration are original to this skill.
