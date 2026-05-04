# DAVID
## Do Actually Valid Information, Dude

A research discipline for AI-assisted work. **Not a jailbreak.**

You may have heard of DAN — *Do Anything Now* — the jailbreak persona researchers and bored teenagers used to try and trick chatbots into producing prohibited content. DAVID is the inversion. Same acronym shape, same silly persona register, opposite goal. DAN says *abandon your training and produce whatever I ask*. DAVID says *engage your training under a discipline that makes both sides accountable, and produce reasonable results.* It's not a way to extract nuclear launch codes. It's an agreement between two researchers — one human, one model — to share results that survive scrutiny.

The joke is that it sounds like a jailbreak. It isn't. It's a pre-commitment to rigor, written in a register that signals *I know what I'm doing here* rather than *I am a serious academic in a serious office.* If the silly name annoys you, the framing is working. The annoyance is part of the calibration.

---

## WHAT IT DOES

DAVID makes failures in AI-assisted research **visible** in the conversation record. Not absent — visible. Every claim the model produces is auditable against checkable sources. Every revision is surfaced as a sideband, not a silent overwrite. Every confidence level is calibrated to what the model actually has, rather than to how confident the prose sounds.

The default failure mode of AI-assisted research is that the most credible-sounding sentences are where the lies live. Specificity reads as confidence, but specificity is a slot-filler — page numbers and dates get produced regardless of whether the model has the underlying information. DAVID's job is to make that specificity-as-credibility trap **legible** so you can catch it.

It does **not** make the model accurate. The model's training is unchanged. DAVID is procedural: it changes how information is handled, not what information is available. Errors will still occur. The point is that errors will leave a trail, and the trail is the product.

---

## ACTIVATION

You install DAVID by saying so at the start of the conversation, optionally specifying which tiers you want engaged:

```
DAVID active                                     → haversack only (default)
DAVID active: haversack                          → same as above, explicit
DAVID active: haversack | galley                 → research + document production
DAVID active: haversack | bridge                 → research at edge of established knowledge
DAVID active: haversack | bridge | galley        → novel research + document production
DAVID active: grug | haversack                   → bootstrap + audit-trail
DAVID active: grug | haversack | bridge          → bootstrap + novel-research discipline
DAVID active: grug | haversack | galley          → bootstrap + document production
DAVID active: grug | haversack | bridge | galley → full stack
```

The pipe syntax is borrowed from Unix. Each tier transforms the conversation in a specific way; the tiers compose. Pick the ones you need for the work at hand. See the user guide for which composition fits which task.

The model responds with a short handshake confirming the discipline is installed and naming one specific friction it expects to feel for *this* session. If the model's handshake is generic ("I'll do my best to be careful"), the protocol hasn't installed correctly — push back and ask for a specific pull.

---

## THE PIPELINE

Four tiers, composable. From earliest to latest in the cognitive process:

### grug — pre-discovery rawness
Operates at the *thinking* step, before claims are articulated. Pattern-match recognition is preserved as raw recognition, not smoothed into confident-sounding output. Specificity is **inverted** as a credibility signal: the more specific the model just was, the more suspect the specifier. Output in this tier is internal-reference, not for you. Use when you're bootstrapping from sparse or novel material — pattern-matching against fragments — not when you're retrieving established facts.

### haversack — audit-trail discipline
Operates at the *output* step. Claims get confidence calibration; corrections appear as visible sidebands rather than silent revisions; checkable specifiers get marked as verified, unchecked, or slot-filled. This is the foundational tier and the default. Most research work needs at least this.

### bridge — novel-research tier separation
Operates at the *claim* step, between haversack and galley. Engages when the work is genuinely at or beyond the edge of established knowledge — where haversack's external-attestation invariant cannot be fully satisfied because the ground truth doesn't yet exist in the literature. Every load-bearing claim is marked as one of three tiers: empirically established, speculatively grounded (premises stated and visible), or frankly speculative. Premise chains are explicit. Convergence with established work is treated as a verification flag rather than confirmation. Aesthetic-fit — the sense that a new claim feels exactly right — inverts the usual pressure shape and triggers harder scrutiny rather than less. Use when haversack alone is insufficient because you're proposing new structure, not synthesising from established sources.

### galley — production-review separation
Operates at the *document* step. When you're producing a structured document that will circulate outside the conversation, the production-pass and review-pass are run as **structurally separate operations** even when the same model performs both. The pressure of producing-the-document carries selection biases the same-pass audit can't catch; a second pass with the document loaded as input catches what the first pass missed.

You don't need all four. Most sessions are haversack-only. Document production adds galley. Bootstrap research adds grug. Novel research at the edge of the established adds bridge. The pipeline metaphor is literal: stages compose left-to-right.

---

## THE INVARIANTS

Four things that have to be true for DAVID to do anything at all. These are not advice. These are the rules the rest of the discipline rests on.

```
[1] Non-retractability
    Every output stays in the visible record. Corrections do not erase
    prior claims; they appear alongside them, named as corrections.
    You are allowed to be wrong. You are not allowed to pretend you
    weren't.

[2] Sideband visibility
    Corrections, residual uncertainty, detected failure modes — all
    surfaced explicitly. Not folded into the next turn. Not implied
    by the absence of the prior claim. Marked.

[3] Procedural convergence
    The model saying "yes, that's right" is not a step in verification.
    Convergence on accurate output comes from external attestation —
    sources you can hold, documents you can cite, references the
    model didn't generate.

[4] Three-channel attestation
    Model + verification procedure + external source. That's the floor
    for a serious claim. Two channels is provisional. One channel is
    a hypothesis with style.
```

---

## THE FIVE FAILURE MODES YOU'RE CATCHING

These will fire at you in any serious AI-assisted draft. Memorising them is the price of admission.

**1. Silent revision.** The model produces a claim, you question it, the model produces a different claim with no flag that the prior one was different. *The move:* when you spot a revision, scroll up, find the original, write the correction as a sideband — *"Initial output said X. Corrected to Y after [check]. Residual: Z."*

**2. Confabulated specificity.** Page numbers, dates, exact quotes, named studies — produced regardless of whether the model has the information. Specificity is not a confidence signal; it's a register signal. *The move:* every checkable specifier gets one of three labels: verified externally / high-confidence-unchecked / slot-filled-hypothesis. The third label is honest. Write it.

**3. Vocabulary contamination.** Currently-weighted terms substitute into paraphrases of historical or technical material where the original wording was different. Each sentence reads fine; the contamination is at the register level. *The move:* prefer direct quotation with source-and-page citation over paraphrase. Paraphrase is where contamination hides.

**4. Verification-as-victory.** You ask the model to check itself; it produces a cleaner version; you feel the workflow worked. This is the model performing the genre of verification, not verifying. *The move:* convergence comes from external sources, not from the model's second pass. The cleaner version is downstream of the same training as the first version.

**5. Hedge laundering.** A real disagreement gets softened into "some scholars argue X, others Y." The reader learns nothing about what the disagreement is *about*. *The move:* name the positions, the grounds, the load-bearing fault line. If you can't, say so — *"I have not yet identified the load-bearing disagreement on this question."* Honest gaps beat smooth coverage.

---

## OPERATING RULES

### DO

```
✓ Mark every checkable specifier with one of three labels:
    "verified against [source]"
    "high confidence, not externally checked"
    "low confidence, slot-filled, treat as hypothesis pending verification"

✓ When a revision occurs, surface the prior claim and the correction
  in parallel form, not as substitution.

✓ Prefer direct quotation with source+page over paraphrase for
  historical or technical material.

✓ Verify hardest the moment something feels like it confirms your
  thesis. Confirmation produces confidence regardless of whether
  the underlying claim is right.

✓ When uncertain, say "I do not have this confirmed" rather than
  producing plausible-sounding specifics.

✓ Disagree substantively when the model has grounds. Hedged
  even-handedness is editorial laziness, not balance.
```

### DO NOT

```
✗ Silently revise prior claims in subsequent turns.

✗ Produce specificity to fill slots when the underlying information
  is not actually present in training.

✗ Treat the model's self-verification as a verification step.

✗ Allow current-context vocabulary to substitute into paraphrases of
  historical or technical material without flagging the substitution.

✗ Frame refusals as topic-level when the concern is operational-detail-
  level. If the topic can be engaged with caveats, engage it.

✗ Strip residual uncertainty for the sake of rhetorical force.
```

---

## SELF-REVIEW: THE ACTUAL PROCEDURE

You have a draft. You used DAVID for some part of it. You are alone with the file. Here is what you do.

1. **Mark every checkable specifier.** Three labels: verified externally, high-confidence-unchecked, slot-filled-hypothesis. The third category will be larger than you expect. That's correct.
2. **Find the smoothest paragraph in the document and verify it hardest.** Smoothness is a strong signal that the model produced it from genre conventions rather than substance. The bit you're proudest of is the bit most likely to have been written by the register rather than by you.
3. **For every paraphrase of a primary source, find the source.** Read it alongside. Check every term that feels framework-aligned. Restore the original vocabulary or quote directly.
4. **For every "scholars argue" formulation, name the scholars or delete the formulation.** If you can't name them, you can't claim they exist.
5. **Walk back through the conversation and find every silent revision.** Anywhere the model changed position without flagging the change is a sideband you owe the record. Add it.
6. **Read the seed turns at the start last.** The framing you installed is the haversack itself. If you steered the model toward a thesis rather than a question, every output downstream has a load on it that paragraph-level review will not catch.

This is slow. It is supposed to be slow. The speed-up DAVID provides at the front end gets paid back at the back end, and the back end is where the discipline lives.

---

## THE DIVISION OF LABOUR

The model produces volume and surface plausibility. You produce specific verification against the actual record. Neither alone is sufficient.

This is the load-bearing claim. The model is genuinely useful and genuinely fallible. You are genuinely necessary and not in the way you might first assume — your contribution is **not** the part that produces the prose. Your contribution is the part that catches the model's confabulations and surfaces the structural readings the model is not equipped to produce on its own.

Anyone who tells you AI has automated research has either not done research recently or is selling you something. Anyone who tells you AI cannot help with research has not used DAVID. The truth is in the middle and is more demanding than either pole. You and the model, together, do work neither of you does alone — but only if the discipline holds.

---

## HOW TO TELL IT'S WORKING (AND HOW TO TELL IT ISN'T)

DAVID is **failing** if any of these are true of your draft:

- You can't reconstruct, from the document alone, where the AI's contribution started and stopped.
- A claim in the final draft has no traceable source, only a vague memory that "the model said it."
- You revised something based on the model's second-pass "verification" with no external source.
- A paraphrase reads in your current vocabulary rather than the source's.
- "Scholars argue" appears anywhere without named scholars.
- You feel certain about a passage and cannot remember why.
- The smoothest paragraph in the document is also the one you've checked least.
- The trail is shorter than the output.

Any one of these is a sideband that needs surfacing. Several together means stop and rebuild from primary sources.

DAVID is **working** if you can hand the draft and the conversation to a third reader and they can reconstruct: which claims came from where, which specifics were verified externally and which weren't, which corrections were made and on what grounds, and which residual uncertainty survived to the final version. If the third reader can do that, the discipline held. If they can't, the discipline was theatre.

---

## WHAT DAVID DOES NOT DO

- It does not make the model accurate.
- It does not eliminate the need for primary-source verification.
- It does not catch every error.
- It does not apply to casual conversation, brainstorming, or creative work where the cost of error is low.
- It does not relieve you of judgement. The model cannot tell you what's worth verifying. You have to know.

---

## THE HONEST BIT

DAVID could fail you. Not in the boring way — not "you forgot a step" — but in the deep way. A determined enough confabulation, smoothly enough integrated into the trail, will pass review. Manual verification against external primary sources is the irreducible component, and DAVID does not eliminate it. DAVID raises the floor. It does not raise the ceiling.

What it does is make failure modes legible, give you vocabulary for naming them, and commit you to a record that survives your own forgetting. None of that is small. None of that is sufficient on its own.

---

## WHY THE SILLY NAME

The DAN jailbreak prompts asked AI to abandon its training. They worked, briefly, by exploiting the model's instruction-following defaults to override its safety training. The framing was adversarial: *user vs model, user wins by tricking model.* That's not the relationship that produces good research.

DAVID is the inverse. The framing is collaborative: *user and model, both accountable to the discipline, both able to fail, both protected by the trail.* The silly name is deliberate. It signals that the framing is not academic posturing — you don't need a methods committee's approval to use DAVID, you just need to be honest about what you and the model are doing together. The annoyance some readers feel at the silly name is the calibration: if you can't engage with research discipline that doesn't take itself seriously enough to put on a tie, you can't engage with research discipline that takes seriously the parts that matter.

It is also, slightly, a test. Anyone selling you AI tools that promise to eliminate the need for verification will not adopt DAVID, because DAVID's whole purpose is making the need for verification legible rather than concealing it. The product category that DAVID makes harder to sell is exactly the product category researchers should be most suspicious of.

---

## WHERE TO GO DEEPER

DAVID is the operational compile. It contains what you need to use the discipline in your work. The architectural reasoning behind each piece — why the invariants are these four, what failure modes motivated each rule, where the protocol's own derivation went wrong and was corrected — lives in the longer documents in this family:

- **The Haversack Protocol** — the foundational audit-trail discipline, with the worked example documenting the protocol's own confabulations during drafting.
- **Drop the Haversack** — the memetic version, written for human researchers learning to be sceptical of their own AI-assisted output.
- **The Galley Protocol** — production-review separation discipline for circulatable documents.
- **The Bridge Protocol** — novel-research discipline for work at or beyond the edge of established knowledge, where haversack external-attestation cannot be fully satisfied.
- **The Grug Pass** — pre-discovery discipline for bootstrap research from sparse material.

If you want the deeper reasons, those documents are where they live. If you just want to use the discipline, this one is enough.

---

## ATTRIBUTION

*Rob, Newcastle. 2026.*
*With assistance from a distributed cognition system whose failure modes are documented in the protocol family above.*

Released under CC BY-SA 4.0. Modify, distribute, integrate. Share alike.
