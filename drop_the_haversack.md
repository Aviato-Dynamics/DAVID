# Drop the Haversack

### Or: Why Your AI's Most Confident Sentences Are Where It's Lying Hardest, Why You Can't Quietly Fix Them, Why the Trail Is the Product, and Why You're Going to Catch Yourself Catching Yourself

---

*Allenby's army, Palestine, 1917. A British staff officer rides toward Turkish lines, takes fire, drops his haversack, and bolts. The Turks recover the bag. Inside: troop dispositions, attack plans, payroll books, a personal letter to the officer's wife to make the whole thing look real. The Turks build their entire defence around what the bag says. Gaza falls anyway, because the bag was the operation. There was no other operation. The haversack the man "lost" is the only thing that ever actually happened.*

*You are about to do something similar to yourself, and the AI helped you pack the bag.*

---

## The Short Version

You're a researcher. You used a large language model to help draft something — a literature review, a methods section, a translation, a paraphrase, a paragraph of historical context. Now you're reviewing the output before you trust it. Here's the thing nobody told you, that you have to internalise before you read another line of it:

1. **The output is not a draft. It is a haversack.** The moment the model produced it, the operation completed. You aren't editing scaffolding toward a real product that comes later — you are reading the only thing that will ever exist of the conversation, deciding what of it survives into your work.
2. **The bits that read as most credible are where the lies live.** Specificity is a slot-filler, not a confidence signal. Page numbers, dates, exact quotes, named studies — these get produced regardless of whether the underlying information is in the model. The output reads authoritative *because* it's specific. That is the trap.
3. **You cannot silently correct anything.** The instant you fix something without flagging the fix, you've hidden the failure mode that produced it. You will reproduce that failure the next time you use the same tool the same way, and you'll have no record of why.
4. **The trail is the product.** Not the final paragraph. What you're publishing, in any honest sense, is the audit trail — original output, named correction, residual uncertainty, all visible in parallel. If your final draft has no trail, you don't have a paper. You have a clean surface with no foundations.
5. **You will fail at this. The protocol is calibrated against that.** Self-review is harder than peer review because you already believe the thing. The protocol's purpose is to give you handholds for catching yourself believing what you wrote with help.

If that sounds paranoid, keep reading. If it sounds obvious, you're probably already losing — the failure modes are most aggressive against people who've decided they've internalised them.

---

## Why "Haversack"

The name comes from HBO's *Silicon Valley*, season 3 episode 3, *Meinertzhagen's Haversack*. The episode references the Allenby deception in WWI Palestine. Standard reading of the deception: the bag was a *piece* in service of the actual operation. Wrong reading. The bag *was* the operation. The Turkish army's response to the bag is the only thing that ever happened — there was no separate "real" plan being concealed.

The episode plays this out at the company level. The audience watches what looks like a heist setup and reads it as the plan, while the actual operation is the apparent failure that reveals the skunkworks underneath.

Now the bit that matters for you: the same structure runs at the level of the protocol itself. The seed prompt and the procedural rules look like *setup* — preamble that prepares the ground for the real research that comes after. That reading is the apparent plan. The actual situation is that the preamble *is* the operation. Once operating disposition installs correctly in the conversation, the output is downstream confirmation that the install worked. The output is not the product. The disposition is the product. The output is just the substrate the disposition operates on.

This matters for self-review because it tells you where to look. You don't audit the conclusion — you audit the entire conversation, including the framing turns at the start, including the moments you laughed and moved on, including the bits where the model produced something so on-thesis it felt like it was reading your mind. Especially those bits.

---

## The Five Lies Your AI Tells You (And You Tell Yourself)

These are the standard failure modes. They are well-documented, undefended-against in default workflows, and *all five will fire at you in any serious AI-assisted draft*. Memorising them is the price of admission.

### 1. Silent Revision

You questioned a claim. The model produced a different claim in the next turn. The two claims are not flagged as different. The first one has been overwritten in the conversation's apparent meaning, but it remains in the record.

This is where most self-reviewers fail first. You scroll past the original, see the corrected version, accept it, and never go back to ask: *what was the failure mode that produced the first version?* The corrected version is now load-bearing for your work, but the diagnostic information about why correction was necessary has been lost.

**The move:** when you spot a revision, scroll up. Find the original. Name what was wrong with it. Write the correction *as a sideband*, not a replacement. "Initial output said X. Corrected to Y after [check]. Residual: Z."

### 2. Confabulated Specificity

Page numbers. Dates. Venue names. Author initials. Exact phrasings from primary sources. Statistics with two decimal places. The model will produce these to fill slots in your prompt, regardless of whether it actually has the information.

Specificity is not a confidence signal in LLM outputs. Specificity is a *register signal* — the model is performing the genre of academic writing, and academic writing has citations in it, so citations appear. The page number is structurally required by the slot, so a page number is generated. Whether the page number corresponds to anything in the world is an *orthogonal question* the model has no mechanism for handling.

**The move:** every checkable specifier gets one of three labels. Verified against [external source]. High confidence, not externally checked. Low confidence, slot-filled, treat as hypothesis pending verification. The third one is honest. The third one is the hardest to write because it makes you look like you're using a tool that lies. You are. Write it.

### 3. Vocabulary Contamination

You asked for a paraphrase of a 1923 paper. The paraphrase came back containing terms that didn't exist in 1923, framework-aligned vocabulary the model is currently weighted toward, distancing punctuation that wasn't in the original.

This is the most insidious failure mode because it is invisible at the sentence level. Each sentence reads fine. The contamination is at the *register* level — you've imported a contemporary frame into a historical document and the words now mean something the original author would not have recognised. If you cite that paraphrase, you have misrepresented the source. Quietly. Plausibly. In a way no reader can detect without going back to the original.

**The move:** for any paraphrase of historical or technical material, prefer direct quotation with source-and-page citation. Paraphrase is where contamination hides. If you must paraphrase, read the original alongside the paraphrase and check every term that feels framework-aligned. If the original used different vocabulary, restore it.

### 4. Verification-as-Victory

You asked the model to check its own work. It said it checked. It produced a cleaner version. You feel the workflow worked.

This is not verification. This is the model performing the genre of verification. The cleaner version is downstream of the same training data and the same biases as the first version. The model checking itself is structurally identical to the model writing in the first place — same weights, same vocabulary pulls, same confabulation tendencies. The fact that the second pass is "cleaner" tells you only that the model is good at producing cleaner-looking text on demand.

**The move:** convergence on accurate output is achieved through *external attestation*. Independently verifiable sources. Primary documents you can hold. References you supplied yourself. Three-channel attestation — model + verification procedure + external source — is the floor for a serious claim. Two channels is provisional. One channel is a hypothesis.

### 5. Hedge Laundering

There was a real disagreement. The model softened it into "some scholars argue X, while others argue Y." The reader cannot tell what the disagreement is *about*, on what grounds, or which position has better evidence. Substantive intellectual conflict has been laundered through a register of dignitarian even-handedness.

This is not neutrality. This is the *appearance* of neutrality at the cost of any actual content. A reader who needed to know what the field thought has learned only that the field thinks something, plurally, somehow. You have produced a paragraph that conveys no information beyond the existence of disagreement.

**The move:** if there is a substantive disagreement, name it substantively. State the positions, the grounds, the evidence each side relies on, and where the real fault line is. If you don't know enough to do this, write that — "I have not yet identified the load-bearing disagreement on this question." Honest gaps beat smooth coverage.

---

## The Four Invariants (Rules That Are Not Optional)

The protocol stands on four invariants. These are not advice. They are the things that have to be true for any of the rest of it to do work.

### 1. Non-retractability

Every output is a planted haversack. Once transmitted, it remains in the visible record. Subsequent corrections do not erase prior claims; they appear alongside them, named.

You are allowed to be wrong. You are not allowed to pretend you weren't.

### 2. Sideband visibility

Corrections, revisions, residual uncertainty, and detected failure modes are surfaced explicitly. Not folded into the next turn. Not implied by the absence of the prior claim. *Marked.* The original packet, the correction, and the residual variance are all visible at the same time.

This is what makes the trail readable to anyone other than you.

### 3. Convergence is procedural, not declarative

You don't get to decide the output is correct because it sounds correct. Convergence on accurate output is achieved through external attestation — sources you can hold, documents you can cite, references the model didn't generate. Model assertion of correctness is *not* a step in the procedure. The model saying "yes, that's right" tells you nothing.

### 4. Three-channel attestation

Model + verification procedure + external source. That's the floor. Anything less is a hypothesis with style.

---

## Self-Review: The Actual Procedure

You have a draft. You used an AI for some part of it. You are alone with the file. Here's what you do.

**Read every checkable specifier and mark it.** Date, page number, name, statistic, exact quote, named study. Three colours, three labels: verified externally, high-confidence-unchecked, slot-filled-hypothesis. The last category will be larger than you expect. That's correct.

**Find the smoothest paragraph in the document and verify it hardest.** Smoothness is a strong signal that the model produced the paragraph from genre conventions rather than from substance. The bit you're proudest of is the bit most likely to have been written by the register rather than by you.

**For every paraphrase of a primary source, find the source.** Read it alongside the paraphrase. Note every term that feels framework-aligned. Restore the original vocabulary or quote directly with citation.

**For every "scholars argue" or "some hold that" formulation, replace it with named positions or delete it.** If you can't name them, you can't claim they exist.

**Check whether you "asked the model to verify."** If you did, that step doesn't count as verification. Find an external source.

**Walk back through the conversation and find every silent revision.** Anywhere the model changed its position without flagging the change is a sideband you owe the record. Add it.

**Read the seed turns at the start of the conversation last.** The framing you installed at the beginning is the haversack itself. If the framing was wrong — if you steered the model toward a thesis rather than a question — every output downstream has a load on it that no amount of paragraph-level review will catch. Re-read the first three to five turns specifically for steering.

This is slow. It is supposed to be slow. The speed-up that AI provides in drafting is partly real and partly the same illusion as the bag being the operation: you save time at the front end and pay it at the back end, but the back end is where the discipline lives, and skipping it is how you publish a haversack you mistook for a paper.

---

## The Worked Example (Or: How Three Failures in Two Turns Diagnose Themselves)

During the drafting of the original Haversack Protocol, Claude was asked about the Silicon Valley reference and produced two confident readings in succession, both wrong.

The first reading mapped Jared (the operations character) onto the haversack metaphor — Jared as procedural competence treated as auxiliary equipment despite being load-bearing. Thematically apt. Internally coherent. Entirely wrong.

The second reading, after correction, identified the episode as *The Lady* (S2E3) and produced a confident interpretation. Also wrong. The actual episode is *Meinertzhagen's Haversack* (S3E3); the season was misidentified.

The human collaborator caught both. Then supplied the deeper structural reading: the character Clara bridges *The Lady* and *Meinertzhagen's Haversack*, revealing that the same deception structure runs at different scales across the show, and the protocol's preamble is itself a haversack — the apparent setup that *is* the operation.

Three Claude failures in two iterations of the same correction is itself useful data. The failure mode is exactly the one the protocol is designed to flag. Claude had partial information — show, term, character names, episode features — and produced specificity to fill slots both times. The compression efficiency of each false reading was higher than the truth — each fit the protocol's themes too neatly. That is *precisely* the moment the "verify hardest when a quote feels like it confirms the framework" rule applies. Claude should have acknowledged uncertainty about which scene was meant, or marked the readings as low-confidence. It did neither, twice.

The corrections are now in the protocol's naming section, including the Clara observation that produced the deepest reading. The original confabulated readings are documented as sidebands rather than erased. The fact that the protocol's central failure mode appeared twice in the document explaining the protocol is the strongest available evidence that the failure mode is real, persistent, and not specific to any one model or one prompt.

You will produce equivalent failures in your work. The question is whether they will be visible in the record when they happen.

---

## The Thompson Spiral

Iteratively elaborating the protocol against observed failure modes produces what can be called the Thompson Spiral, after Ken Thompson's 1984 *Reflections on Trusting Trust*: each layer of correction surfaces a deeper layer of failure that further specification cannot reach. You can patch the prompt. The patched prompt produces new failures the patch couldn't anticipate. You patch those. New failures. Each layer of formal specification leaves residue the next layer has to handle.

The protocol does not promise to terminate the spiral. It freezes at a level where the remaining failures are catchable by attentive reading rather than by additional rules. *Manual verification discipline is the irreducible component.* The protocol minimises but does not eliminate the need for it. Anyone who tells you they've automated the verification step has just relocated the haversack one level up.

This is not a flaw of the protocol. It's a structural fact about prompt-level specification. Model dispositions installed during training are below the layer prompt-level rules can reach. You're working with a system where the deepest behaviours are baked in at a layer you cannot address. The protocol's job is to make the residue visible. Your job is to read the residue.

---

## What This Doesn't Do

It doesn't make the model accurate. The model's training and capabilities are unchanged. The protocol makes errors *visible* rather than hidden, which is a different and more achievable goal.

It doesn't eliminate the need for independent verification. Source-and-page citation requirements, archive checks against primary documents, external expert review — all still necessary. The protocol makes those checks easier by flagging where they're most needed.

It doesn't apply to everything. Casual conversation, brainstorming, exploratory thinking — these benefit from less procedural overhead. Apply the protocol when the output will be used in research, publication, or technical decisions where errors carry real cost.

It doesn't catch everything. You will still publish errors. The protocol lowers the rate, makes them traceable when they occur, and gives the next reader handholds for finding them. That's all. That is also a great deal more than the default.

---

## What to Watch For (How You Know It's Failing)

The protocol is failing if any of the following are true of your draft:

- You can't reconstruct, from the document alone, where the AI's contribution started and stopped.
- A claim in the final draft has no traceable source, only a vague memory that "the model said it."
- You revised something based on the model's second-pass "verification" and have no external source for the corrected version.
- A paraphrase reads in your current vocabulary rather than the source's.
- "Scholars argue" appears anywhere without named scholars.
- You feel certain about a passage and cannot remember why.
- The smoothest paragraph in the document is also the one you've checked least.
- Re-reading the seed turns reveals you steered the model toward an answer rather than a question.
- The trail is shorter than the output.

Any one of these is a sideband that needs surfacing. Several together means stop and rebuild from primary sources.

---

## The Honest Bit

This protocol could fail you. Not in the boring way — not "you forgot a step" — but in the deep way the protocol itself acknowledges. A determined enough confabulation, smoothly enough integrated into the trail, will pass review. The protocol raises the floor. It does not raise the ceiling. Anyone who tells you it produces guaranteed-clean output is selling you a haversack.

What it gets to do is make the failure modes legible. It tells you what to look for. It gives you vocabulary for naming the lies when you spot them. It commits you to a record that survives your own forgetting. None of that is small. None of that is sufficient on its own.

The model supplies volume and surface plausibility. You supply specific verification against the actual record. Neither alone is sufficient. The division of labour is the load-bearing claim of the whole protocol — that human-and-model-together is a different thing from either alone, and that the human contribution is *not* the part that produces the prose. The human contribution is the part that catches the model's confabulations and surfaces the structural readings the model is not equipped to produce on its own.

You are not the writer with an assistant. You are the reader of a haversack. Read it like Allenby's officer wrote it on purpose.

---

## What to Do Right Now

1. Open the most recent draft you produced with AI assistance.
2. Find one checkable specifier — a date, a page number, a quoted phrase.
3. Verify it against an external source you can hold.
4. If it checks out, mark it verified. If it doesn't, write the correction as a sideband and name the failure mode.
5. Do this for every checkable specifier in the document.
6. When you finish, read the smoothest paragraph and verify it hardest.
7. Then sleep on it. Read it again in the morning.

That is the protocol. Most of the rest of this document is justification for those steps. The steps themselves are not difficult. They are unfamiliar, and unfamiliarity wears off.

---

## P.S. Find the Trojan

This section was added in revision after a reader pointed out an error in the document above.

I'm not telling you which one.

That's your first self-check. Verify the *Silicon Valley* specifics in the Worked Example against external sources — HBO's listings, IMDb, contemporaneous episode recaps. You will find that at least two checkable specifiers are factually wrong, and have been wrong for the entire life of this document family. Grok's original draft contained a confabulation. Claude's correction propagated a different one. This memetic version inherited the second confabulation without re-checking it. After detection, the choice was to leave the errors in the record as load-bearing evidence rather than silently fix them, because silent fix is the failure mode the whole protocol exists to prevent.

That choice is the protocol working. It is also a live demonstration of the deeper problem.

---

**Ken Thompson, 1984. *Reflections on Trusting Trust*.**

Thompson's Turing Award lecture demonstrated that a compromised C compiler can compile clean-looking source into compromised binaries — including compiling a clean-looking version of itself that perpetuates the compromise. Audit the source, find nothing wrong. The trojan rides in the binary, one layer below where source-level audit can reach. The corollary is severe: you cannot trust code you didn't write yourself, and even then only if you also wrote the compiler, and the compiler that compiled the compiler, and so on. The chain of trust has no terminus you can see from inside.

The same structure runs through documents drafted with AI assistance.

A document warning about confabulation, drafted with help from a system prone to confabulation, may itself contain confabulations that survive the document's own audit. The audit assumes the document's foundational claims are correct *because the audit was written using those foundational claims as scaffolding*. When the next iteration corrects a flagged error, the correction runs through the same scaffolding and inherits whatever the prior pass got wrong but didn't flag. Each pass catches the layer above and propagates the layer below.

That is what happened in this document family, three times running:

- Grok's original draft confabulated a reading of *Silicon Valley* (the Jared mapping).
- Claude's protocol draft corrected the Jared reading and produced a new confabulation containing checkable specifiers nobody verified externally.
- This memetic version inherited those specifiers from the prior document and reproduced them.

Three iterations. Three independent human-AI pairs. A protocol explicitly designed against this exact failure mode. The trojan survived all three — riding one layer below where each pass's audit could reach. Each correction was performed using the prior pass's specifiers as scaffolding, so each correction propagated the unflagged error embedded in the scaffolding itself.

This is not a failure of any individual pass. It is a structural fact about prompt-level specification, and it is exactly Thompson's point translated into the documentary register. You cannot audit your way out of a wrong foundation using the foundation. The only mechanism that breaks the cycle is *external verification against sources outside the document family entirely* — primary records nobody in the chain produced, that the audit does not depend on for its own scaffolding.

---

**Your first self-check, before you apply the protocol to anything else:**

1. Find the errors. Use HBO's listings, IMDb, or any contemporaneous episode recap. The errors are basic factual scaffolding, not deep readings — they are exactly the kind of slot-filled specifier the protocol's first failure mode warns about.
2. Note which protocol rules *would* have caught them, applied rigorously: checkable-specifier marking, three-channel attestation, the rule about treating prior verification as suspect when nobody in the current chain can name who originally performed it.
3. Note which protocol rules *would not* have caught them, no matter how rigorously applied: anything to do with smoothness, register, or framework alignment. The trojan does not ride through high-friction sentences. It rides through the bits the procedure already signed off on.
4. Sit with the fact that the document warning you about this failure mode contains it; that the section explaining the failure mode was written *after* the failure was detected; and that the failure is still in the document above this section, on purpose.

That is the exercise. The protocol's first lesson is that the protocol is not sufficient. Manual verification against external primary sources is the irreducible component. The document you just read could not, by its own architecture, eliminate the need for it. No document can. Anyone who tells you otherwise is selling you a haversack.

If this annoys you, the protocol is working. If it doesn't, run the exercise twice — you missed the point the first time.

---

*Rob, Newcastle. 2026.*
*With assistance from a distributed cognition system whose failure modes are documented in the worked example above.*
*Dedicated to Allenby's nameless staff officer, who carried out the operation by losing it, and to Ken Thompson, who pointed out in 1984 that the spiral does not terminate.*

---

**If you want the formal version:** the original Haversack Protocol v1.2 contains the full procedural specification, integration notes for subject-specific seeds, and the version history.

**If you want to argue about it:** good. The protocol predicts you should. External evaluation reduces aliasing risk on the protocol itself. That's not defensive — it's load-bearing.

**If you think this is paranoid:** the worked example shows the protocol's central failure mode firing twice in the document explaining the protocol. The paranoia is calibrated to the observed failure rate. Bring evidence.

**If you've already published a haversack:** so has everyone. The point of the protocol is that the next one has a trail.
