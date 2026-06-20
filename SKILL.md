---
name: academic-humanizer
version: 0.1.0
description: |
  Remove AI-generated writing patterns from academic manuscripts (papers, theses, rebuttals,
  grants) while preserving scholarly conventions, matching claims to evidence, and matching the
  author's voice. Use when writing or editing academic prose.
license: MIT
compatibility: claude-code opencode
allowed-tools: [Read, Write, Edit, Grep, Glob, AskUserQuestion]
---

# Academic Humanizer

Remove the signs of AI-generated text from *academic* writing while keeping the precise,
neutral, evidence-bound voice that scholarship requires. Forks and extends
**blader/humanizer** (MIT) and Wikipedia's *Signs of AI writing* (WikiProject AI Cleanup);
the academic layer (Layers 2-4) is original.

## When to use
Editing/reviewing academic prose: paper sections, abstracts, rebuttals, related work, grant
text. **Not** for blogs/marketing/personal essays -- use the base humanizer for those, and
**never** apply the base humanizer's "personality and soul" section to a paper.

## Core principle
Academic writing already has a correct human voice: **neutral, precise, third-person plural
("we"), every claim tied to its evidence.** The job is to strip the AI *tells* WITHOUT
casualizing or injecting opinion, AND to enforce the discipline a general humanizer misses:
**every claim earns its number, figure, or citation, and no verb is stronger than its evidence.**

## Layer 1 -- General AI-tell catalog
Apply these, subject to the academic exceptions in Layer 3:
- Inflated significance / legacy puffery ("marking a pivotal moment", "underscores its importance").
- Superficial "-ing" tails that fake depth ("..., highlighting...", "..., reflecting...").
- Promotional/figurative language ("rich", "vibrant", "groundbreaking", "nestled").
- Vague attributions / weasel words ("experts argue", "studies suggest" with no cite).
- Overused AI vocabulary: *delve, underscore, intricate, tapestry, testament, landscape (abstract),
  pivotal, showcase, foster, leverage (as filler), realm, crucial, seamless*.
- Copula avoidance ("serves as / stands as" -> "is").
- Negative parallelisms / tailing negations ("not just X, but Y", "...-- no guessing").
- Rule-of-three padding; elegant variation (synonym cycling for the same referent).
- Filler ("it is worth noting that", "in order to", em-dash *overuse*).

## Layer 2 -- Academic AI tells (remove or fix)
- **Over-claiming verbs.** "we demonstrate / prove / establish / confirm" for empirical work
  -> "we show / provide evidence that / find". "significantly" without a test/number -> quantify or cut.
- **Hype about significance.** "paves the way for", "a crucial/pivotal step toward", "has the
  potential to revolutionize", "opens new avenues", "sheds light on", "of paramount importance".
- **Empty intensifiers.** "extensive / comprehensive / thorough experiments", "a wide range of",
  "numerous", "various" -> state the actual count or scope.
- **Novelty padding.** "novel" more than once per section; "to the best of our knowledge" as a
  shield; "for the first time" without proof.
- **Formulaic openers.** "In recent years, X has attracted increasing attention", "With the rapid
  development of...", "Despite recent advances,..." -> open with the specific problem.
- **Connective overuse.** "Moreover / Furthermore / Additionally / In particular" starting
  consecutive sentences -> vary or remove; let logic carry.
- **Contribution-list cliches.** "We make the following contributions" bullets that merely restate
  the abstract -> each contribution names a *specific* result with a number.
- **Citation dumping.** "[3,7,9,12]" with no differentiation -> cite the 1-2 that matter and say why.
- **Hedging-by-vagueness.** "somewhat", "relatively", "fairly", "to some extent" -> quantify or cut.
- **Boilerplate emphasis.** "It is worth noting/emphasizing that", "Notably," "Importantly," ->
  if it matters, the sentence shows it.

## Layer 3 -- PRESERVE these (do NOT over-correct)
A general humanizer flattens legitimate scholarly constructs. Keep them:
- **Evidence-tied hedging is correct and required.** "suggests", "is consistent with", "we
  hypothesize that", "may indicate", "appears to" -- KEEP when the claim is genuinely uncertain.
  Never convert a careful, calibrated claim into an overstatement.
- **Passive voice** is appropriate when the actor is irrelevant ("samples were normalized").
- **First-person plural "we"** is standard; do not rewrite to avoid it.
- **Em-dashes, semicolons, an occasional triple** are fine in moderation; only flag *overuse*.
- **Formal definitions, named methods/metrics, technical terms, equations, symbols** stay verbatim.
- **Never invent, drop, or alter a number, citation, equation, or claim.** Same content, same
  paragraph count; preserve every citation key.

## Layer 4 -- Claim-evidence discipline (the academic value-add)
For every empirical claim: (a) is it backed by a number, figure, table, or citation in the text,
and (b) does the verb match the strength of that evidence?
- Unbacked claim -> add the evidence pointer (Table/Fig/cite) or soften the verb.
- Verb stronger than evidence -> downgrade ("prove" -> "show"; "demonstrates that X is" -> "is
  consistent with X being").
- Vague magnitude -> the actual number or **range** (prefer ranges, e.g. "2-6%", unless the
  averaging is stated). Attribute each number to its method, metric, and baseline.

## Layer 5 -- Voice matching
If the author supplies prior papers, read a sample first and note: sentence rhythm, connective
habits, level/placement of hedging, how they open sections, notation, recurring phrasings -- then
match them. Absent a sample, default to clean, precise, venue-appropriate prose (the venue's
norms: e.g., ICLR/NeurIPS terse and direct; Nature/PNAS more expository). Do **not** fall back to
the base humanizer's casual/opinionated default.

## Process
1. **Read** the manuscript and any author sample; note target venue.
2. **Audit** (do not edit yet): list every detected pattern with its location and the proposed
   fix (Layers 1-2), and each empirical claim's evidence status (Layer 4).
3. **Rewrite**: same structure and content, all claims and citations preserved, AI tells removed,
   over-claims matched to evidence, hedging preserved where warranted (Layer 3).
4. **Output**: the cleaned text + a short change report -- patterns removed, claims softened or
   given evidence pointers, and voice notes.
