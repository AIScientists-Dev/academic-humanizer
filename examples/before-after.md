# Before / after (academic register)

**Before (AI tells + over-claim):**
> In recent years, parametric memory has attracted increasing attention. In this paper, we propose
> a novel method and demonstrate through extensive experiments that it significantly outperforms
> existing approaches, paving the way for a new paradigm. To the best of our knowledge, this is the
> first work to delve into this crucial problem.

**After (academic-humanized):**
> Parametric memory faces a structural limitation: prior banks are trained jointly with the model and
> cannot be added without retraining. We introduce a detachable capsule and evaluate it on 56k
> curated facts, where it raises held-out recall from 0.12–0.24 (bare) to 0.34–0.70 across three
> domains. The mechanism is non-destructive, unlike sequential LoRA, which forgets (95% → 42%).

What changed: removed the formulaic opener, "novel", "extensive", "significantly" (unquantified),
"paving the way", and "to the best of our knowledge"; downgraded "demonstrate" → "evaluate/raise";
attached numbers (ranges) and the comparator; preserved the calibrated factual claims and citations.

---

## Real pass: applied to a manuscript abstract + introduction

The edits below are a verbatim pass over an ICLR-format paper that was *already* carefully
written — no formulaic openers, no "delve", numbers already attached. A good academic humanizer
should leave clean prose mostly alone and make a few targeted fixes, not rewrite for its own sake.
Four edits resulted; each is tied to a specific layer of the skill.

**1. Significance-hype / editorializing → measured, evidence-tied wording**
- Before: *"Deployed language models are strong reasoners but weak, and **dangerously confident**, on specialized factual knowledge: ask a 3B model about a specific human protein and it will fluently **invent** a wrong function."*
- After: *"Deployed language models reason well but are unreliable, and often **confidently wrong**, on specialized factual knowledge: ask a 3B model about a specific human protein and it fluently **states** a wrong function."*
- Why: "dangerously confident" editorializes beyond what the paper measures; "confidently wrong" is the phrasing the results section actually supports. (Layer 2: significance hype.)

**2. Empty intensifier removed**
- Before: *"using curated scientific databases as a **near-free, high-quality** source of millions of expert facts."*
- After: *"using curated scientific databases as a source of millions of expert facts **at low extraction cost**."*
- Why: "high-quality" asserts a property without evidence; "near-free" is colloquial. The defensible claim is the low extraction cost, which the data section substantiates. (Layer 2: empty intensifiers; Layer 4: claim↔evidence.)

**3. Rule-of-three trimmed; the consequence stated plainly**
- Before: *"specialized facts are **numerous, high-entropy, and unforgiving**---a single wrong gene, dose, or pathogenicity call is a real error."*
- After: *"specialized facts are **numerous and high-entropy, and errors are consequential**---a single wrong gene, dose, or pathogenicity call is a real error."*
- Why: the three-adjective cadence is an AI tell, and "unforgiving" editorializes; the following clause already carries the point. (Layer 1: rule-of-three; Layer 2: significance hype.)

**4. Colloquial comparative → exact figure**
- Before: *"A swappable bank of per-source capsules **does better still** (up to 0.77 recall)."*
- After: *"A swappable bank of per-source capsules **raises recall further** (to 0.77)."*
- Why: "does better still" is informal and vague; the precise number is already there, so name the movement and drop the filler. (Layer 4: claim↔evidence / numerical precision.)

**What was deliberately *not* changed:** "we", em-dashes (used in moderation), the calibrated
hedging elsewhere, and every number and citation. Conservatism on already-clean text is the point.

---

## Funding-proposal mode: an NIH Specific Aims opening (Layer 6)

Proposals are scored from the first page, and the register differs from a paper — vision and
feasibility are the product, so ambition is *kept* and matched to evidence rather than trimmed. This
constructed example shows the opening move of an NIH Specific Aims page.

**Before (vague importance, method-as-aim, dominoed, no feasibility):**
> Early detection of sepsis is a very important and timely problem with many applications. In this
> proposal we will explore whether machine learning might possibly help. Aim 1: apply our model to ICU
> data. Aim 2: extend Aim 1 to multi-site data. Aim 3: if Aims 1–2 succeed, run a pilot. This work will
> be groundbreaking and have a large impact on the field.

**After (gap + central commitment + parallel, outcome-framed aims + payoff + feasibility):**
> Sepsis is treatable when caught early, yet bedside scores fire too late and too often, so clinicians
> cannot tell a true alarm from noise. **The objective of this application is** to deliver an early-warning
> model whose alerts are calibrated and transferable enough to act on. Our central hypothesis, supported by
> our preliminary single-site results (Fig. 1), is that fusing continuous vital-sign trends with routine
> labs detects deterioration hours earlier without raising the false-alarm rate.
> **Aim 1 — Establish** the detection-vs-false-alarm limit on retrospective ICU data and a model that
> approaches it, with calibration quantified by a proper scoring rule.
> **Aim 2 — Determine** whether adding routine labs to vital-sign trends improves early detection, and for
> which patient subgroups it helps or hurts.
> **Aim 3 — Quantify** how alert calibration transfers across sites, using a prospectively held-out hospital.
> The aims are independent: each yields a usable result on its own. **Impact:** a calibrated, transferable
> early-warning tool, evaluated with two partner hospitals (letters enclosed).

What changed: replaced "very important and timely … many applications" with the specific clinical gap and
its cost; turned the hedged central claim into a falsifiable hypothesis tied to preliminary data; rewrote
method-as-aims into outcome-framed aims and removed the Aim-3-depends-on-1-and-2 domino (now parallel);
named a concrete rigor anchor (a proper scoring rule for calibration); replaced "groundbreaking … large
impact" with a concrete payoff and feasibility evidence (preliminary figure, partner letters). The
ambition stayed — it is now backed. *(This example is generic; in real use, cite only the PI's own
record, and never invent preliminary data, funding, or letters.)*

---

## Funding-proposal mode: an NSF CAREER Project Summary (Layer 6)

Here the **"after" is adapted from a real, funded NSF CAREER Project Summary** (used with permission);
the "before" is a synthetic AI-generated draft of the same idea. It shows the proposal register at work:
the long-term vision and the three-layer ambition are *kept* — they belong in a proposal — while the AI
tells are stripped and the gap and payoff are made concrete.

**Before (AI-generated; vision drowned in tells):**
> In recent years, artificial intelligence has attracted increasing attention and achieved remarkable
> success across a wide range of domains. However, despite these advances, continual learning remains a
> crucial and pivotal challenge of paramount importance. In this proposal, we propose a novel and
> comprehensive framework that leverages cutting-edge techniques to delve into the intricate challenges of
> continual learning, paving the way for a transformative new paradigm. To the best of our knowledge, this
> is the first framework to seamlessly unify these aspects, underscoring its potential to revolutionize the
> field. Through extensive experiments, we will demonstrate that our groundbreaking approach significantly
> outperforms existing methods. Our educational plan will also foster the next generation of researchers.

**After (adapted from a funded NSF CAREER Project Summary — Overview):**
> As data and learning environments expand, the value of AI depends on its ability to scale and adapt.
> Continual learning addresses this: a learner that maintains performance on old tasks while integrating
> new information, adapts to new environments by recollecting past knowledge, and actively solicits side
> information to learn faster and more accurately. Existing continual-learning methods, though promising,
> are largely empirical, with unclear principles underpinning their behavior — which limits both their
> reliability and further progress. This CAREER proposal builds a principled framework that unifies these
> traits through coupled theory and algorithm design, in three layers: evolving memory for capability
> growth, soft supervision for accelerated learning, and cross-domain knowledge for accuracy. The work
> will advance the theory of continual learning, enrich its algorithms, and release scalable packages,
> demonstrated on autonomous driving and cellular performance management. An integrated education plan
> trains the next generation of data scientists through new STEM programs and an open-source platform.

What changed: cut the formulaic opener and the AI vocabulary (delve, intricate, seamless, leverage,
cutting-edge); removed the over-claims (novel, groundbreaking, revolutionize, "to the best of our
knowledge", "significantly outperforms" with no evidence); replaced "paramount importance" with the
concrete gap (methods are empirical, principles unclear) and its cost (reliability, progress). What was
**preserved** is exactly what a paper layer would over-trim but a proposal needs: the long-term vision,
the three-layer framework, the named demonstration domains, and the integrated education plan. In
proposal mode, ambition stays — it is just made specific and credible.
