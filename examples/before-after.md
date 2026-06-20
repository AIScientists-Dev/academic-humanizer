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
