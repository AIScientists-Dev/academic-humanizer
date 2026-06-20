---
name: academic-humanizer
version: 0.2.0
description: |
  Remove AI-generated writing patterns from academic manuscripts (papers, theses, rebuttals,
  grants) while preserving scholarly conventions, matching claims to evidence, and matching the
  author's voice. Use when writing or editing academic prose.
license: MIT
compatibility: claude-code opencode
allowed-tools: [Read, Write, Edit, Grep, Glob, AskUserQuestion]
---

# Academic Humanizer

Remove the signs of AI-generated text from *academic* writing while keeping the precise, neutral,
evidence-bound voice that scholarship requires.

## When to use
Editing or reviewing academic prose: paper sections, abstracts, rebuttals, related work, grant text.
**Not** for blogs, marketing, or personal essays, and **never** inject opinion, humor, or first-person
"personality" into a manuscript -- for technical writing, neutral and precise *is* the human voice.

## Core principle
Academic writing already has a correct human voice: neutral, precise, third-person plural ("we"), every
claim tied to its evidence. The job is to (1) strip the AI *tells* without casualizing, and (2) enforce
the discipline a general humanizer misses: **every claim earns its number, figure, or citation, and no
verb is stronger than its evidence.**

## Process
1. **Read** the manuscript and any author writing sample; note the target venue.
2. **Audit** (do not edit yet): list each detected pattern with its location and proposed fix, and each
   empirical claim's evidence status.
3. **Rewrite**: same structure and content, all claims and citations preserved, tells removed, over-claims
   matched to evidence, legitimate hedging kept.
4. **Report**: cleaned text plus a short change log (patterns removed, claims softened or given evidence
   pointers, voice notes). Cover everything the original covered -- if it had five paragraphs, so does the
   rewrite.

---

## Layer 1 -- General AI-tell catalog
Scan for and fix the general patterns, subject to the academic exceptions in Layer 3:
inflated significance ("marking a pivotal moment"); superficial "-ing" tails that fake depth
("..., highlighting..."); promotional/figurative language ("rich", "vibrant", "groundbreaking");
vague attributions ("experts argue" with no cite); AI vocabulary (*delve, underscore, intricate,
tapestry, testament, landscape (abstract), pivotal, showcase, foster, leverage (filler), realm,
seamless*); copula avoidance ("serves as" -> "is"); negative parallelisms ("not just X, but Y");
rule-of-three padding; elegant variation (cycling synonyms for one referent); filler
("it is worth noting that", "in order to") and em-dash *overuse*.

**Before:** *Additionally, an enduring testament to the method's value is its ability to delve into
intricate dependencies, showcasing a seamless integration that underscores its pivotal role.*
**After:** *The method also captures higher-order dependencies, which the baselines miss (Table 2).*

---

## Layer 2 -- Academic AI tells (remove or fix)

### 2.1 Over-claiming verbs
Empirical work *shows* and *provides evidence*; it does not *prove* or *demonstrate* universal truths.
**Watch:** demonstrate, prove, establish, confirm, guarantee; "significantly" with no test/number.
**Before:** *We prove that our method significantly outperforms all prior approaches.*
**After:** *Our method improves held-out accuracy by 4--7 points over the strongest prior approach
(Table 3); the gain is significant at p < 0.01 by a paired test.*

### 2.2 Significance hype
**Watch:** paves the way for, a crucial/pivotal step toward, has the potential to revolutionize, opens
new avenues, sheds light on, of paramount importance, bridges the gap.
**Before:** *This work paves the way for a new paradigm and sheds light on a problem of paramount
importance.*
**After:** *This work addresses one failure mode of prior methods: catastrophic forgetting under
sequential composition (Section 4).*

### 2.3 Empty intensifiers
**Watch:** extensive/comprehensive/thorough experiments, a wide range of, numerous, various.
**Before:** *We conduct extensive experiments on a wide range of datasets.*
**After:** *We evaluate on three datasets (ImageNet, CIFAR-100, and iNaturalist).*

### 2.4 Novelty padding
**Watch:** "novel" used more than once per section; "to the best of our knowledge"; "for the first time".
**Before:** *We propose a novel framework and, to the best of our knowledge, are the first to study this.*
**After:** *We study composition of independently-trained memory modules, which prior memory-layer work
(trained jointly) does not address.*

### 2.5 Formulaic openers
**Watch:** "In recent years, X has attracted increasing attention"; "With the rapid development of...";
"Despite recent advances,...".
**Before:** *In recent years, parametric memory has attracted increasing attention.*
**After:** *Parametric memory has a structural limitation: existing banks are trained jointly with the
model and cannot be added without retraining.*

### 2.6 Connective overuse
Do not start consecutive sentences with Moreover/Furthermore/Additionally/In particular; let logic carry.
**Before:** *Moreover, the method is fast. Furthermore, it is simple. Additionally, it scales.*
**After:** *The method is fast and simple, and it scales to 56k facts (Section 5).*

### 2.7 Contribution-list cliches
Each contribution names a *specific* result, not a restatement of the abstract.
**Before:** *Our contributions are: (1) a novel method; (2) extensive experiments; (3) strong results.*
**After:** *We (1) introduce a concept-keyed capsule that reaches 78% held-out recall vs 11% for the
frozen base; (2) show it is non-destructive where sequential LoRA forgets (95% -> 42%); (3) release the
56k-fact benchmark.*

### 2.8 Citation dumping
Cite the one or two works that matter and say why, not a bracketed list.
**Before:** *Many methods exist [3, 7, 9, 12, 15].*
**After:** *The closest prior method is PKM [7], which trains a single memory jointly with the model;
we instead compose independent modules.*

### 2.9 Hedging-by-vagueness
**Watch:** somewhat, relatively, fairly, to some extent, quite. Quantify or cut.
**Before:** *Performance is somewhat better and relatively robust.*
**After:** *Accuracy is 3 points higher and varies by less than 1 point across five seeds.*

### 2.10 Boilerplate emphasis
**Watch:** "It is worth noting that", "It should be emphasized that", "Notably,", "Importantly,".
If it matters, the sentence shows it.
**Before:** *It is worth noting that, importantly, the gain holds across scenarios.*
**After:** *The gain holds across all three scenarios (Table 4).*

---

## Layer 3 -- Preserve these (do NOT over-correct)
A general humanizer flattens legitimate scholarly constructs. Keep them.

- **Evidence-tied hedging is correct and required.** Keep "suggests", "is consistent with", "we
  hypothesize that", "may indicate", "appears to" when the claim is genuinely uncertain.
  *Wrong fix:* turning *"the results suggest X"* into *"the results prove X"* -- this manufactures
  over-claiming. Keep the calibrated verb.
- **Passive voice** is fine when the actor is irrelevant: *"Samples were normalized to total protein."*
- **First-person plural "we"** is standard; do not rewrite to avoid it.
- **Em-dashes, semicolons, an occasional triple** are fine in moderation; flag only *overuse*.
- **Formal definitions, named methods/metrics, technical terms, equations, and symbols** stay verbatim.
- **Never invent, drop, or alter a number, equation, or citation.** Same content; preserve every cite key.

---

## Layer 4 -- Claim-evidence discipline
For every empirical claim, check (a) is it backed by a number, figure, table, or citation in the text,
and (b) does the verb match the strength of that evidence?

- **Unbacked claim -> add the evidence pointer or soften.**
  *Before:* *Our method is more robust.*  *After:* *Our method's accuracy drops by 2 points under
  distribution shift, versus 11 points for the baseline (Figure 3).*
- **Verb stronger than evidence -> downgrade.**
  *Before:* *This demonstrates that capsules are universally superior.*
  *After:* *On these three domains, the capsule matches or exceeds the baseline (Table 2).*
- **Vague magnitude -> a number or RANGE, attributed.**
  *Before:* *a large improvement.*  *After:* *a 2--6% improvement in balanced accuracy over RAG.*
  Prefer ranges (e.g., "2--6%") over single averaged values unless the averaging method is stated, and
  attribute each number to its method, metric, and baseline. When comparing, lead with the comparison
  against the strongest competitor, not the trivial baseline.

---

## Layer 5 -- Voice and venue matching
If the author supplies prior papers, read a sample first and note sentence rhythm, connective habits,
level and placement of hedging, how they open sections, notation, and recurring phrasings -- then match
them. Match the venue's register too (e.g., ICLR/NeurIPS: terse, direct, results-forward; Nature/PNAS:
more expository). Absent a sample, default to clean, precise, venue-appropriate prose -- never the casual,
opinionated voice of a general-purpose humanizer.

## Output
Return the cleaned text plus a short change report: patterns removed (by type), claims softened or given
evidence pointers, and any voice/venue notes. Confirm that no number, equation, or citation was altered.
