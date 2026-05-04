# DAVID USER GUIDE
## Pipeline composition for AI-assisted research

DAVID is composed of three tiers that engage like Unix pipeline stages. You don't run all three for every task — you pick the composition that fits the work. This guide shows you which composition does what, when to use it, and how the tiers interact when they're stacked.

---

## THE PIPELINE METAPHOR

If you've used a shell, the metaphor is literal:

```
input → grug → haversack → galley → output
```

Each stage transforms what passes through it. Each stage has a job. You can engage any subset by specifying which stages you want; the unspecified ones are skipped. You always include at least one. The default — `haversack` alone — is the foundational tier and the right choice for most research conversations.

If you haven't used a shell, the rough analogy is a coffee filter, then a mug, then a saucer. Each stage handles something the next stage assumes is already done. You don't have to use the saucer. You probably want the mug.

---

## TIER 0 — NO PIPELINE

You're just talking to the model, no DAVID active. Default behaviour. This is the right choice for:

- Casual conversation
- Brainstorming and exploratory thinking
- Creative work where the cost of factual error is low
- Quick "remind me how X works" lookups where you'll catch errors yourself
- Emotional or social conversation

The protocol explicitly does **not** want to colonise these. Most of what you do with an AI does not need DAVID. Wrapping every interaction in research discipline is overhead with no payoff.

---

## TIER 1 — HAVERSACK ONLY

```
DAVID active: haversack
```

The foundational tier. Engage when:

- You're having a research conversation that involves checkable facts
- You're fact-checking something the model produced earlier
- You're discussing a topic where the model's confidence might exceed its evidence
- You want a record of where claims came from

What you get:

- Confidence calibration on every checkable specifier (verified / unchecked / slot-filled)
- Visible sidebands when claims get revised (no silent overwriting)
- Refusal to produce specifics when the underlying information isn't in training
- Substantive disagreement rather than "both sides" hedging
- The four invariants holding for the rest of the conversation

What you don't get:

- Document-level structural review (use galley for that)
- Pre-articulation rawness preservation (use grug for that)

Sample invocation:

> *"DAVID active: haversack. I'm researching how the Bell Labs Unix team thought about portability before C was finished. I want every claim about specific dates, papers, or attributed positions marked for verifiability."*

The model handshakes, names a friction it expects to feel ("pull toward producing specific paper citations even where my information is fragmentary"), and the discipline is installed.

---

## TIER 2 — HAVERSACK + GALLEY

```
DAVID active: haversack | galley
```

Engage when:

- You're going to ask the model to produce a structured document — a methods section, a literature review, a memo, a draft chapter
- The document will leave the conversation and circulate elsewhere
- Errors in the document will carry costs at distance from production

What you get:

- Everything tier 1 gives you, plus —
- A structurally separate review pass after the document is produced, with the document loaded as input rather than as conversational continuation
- Detection of failure modes specific to document production: rhetorical-landing inflation, argumentative slot-filling, vocabulary capture, decorative humility
- Argumentative warrant marking on every load-bearing claim (established / synthesised / asserted-without-warrant)
- Framing metadata top and bottom of the document so it survives circulation outside its source conversation

The key insight tier 2 enforces: *production and review are different operations.* The pressure of producing-the-document carries selection biases that the same-pass audit cannot detect. A second pass with the document loaded as input catches what the production pass missed. Same model, same discipline, different operation. This is the central thing tier 2 buys you that tier 1 cannot.

Sample invocation:

> *"DAVID active: haversack | galley. We've been auditing claims about FM synthesis chip architectures. Now I want a 1500-word document synthesising the audited positions. After you produce it, run the galley pass against it and surface any failures."*

The model handshakes for both layers, produces the document, and then explicitly runs a second pass surfacing audit findings. The findings are sidebands you can act on or accept as residual.

---

## TIER 3 — GRUG + HAVERSACK

```
DAVID active: grug | haversack
```

Engage when:

- You're bootstrapping from sparse or novel material toward a finding
- You're pattern-matching against fragmentary evidence rather than retrieving established information
- The work is genuinely exploratory and you'd rather have the model's rough recognition than its confident retrieval
- You want pre-articulation rawness preserved, including raw recognition of what shouldn't be produced

What you get:

- A pre-discovery layer where the model's pattern-matching is captured as raw recognition, not smoothed into confident output
- Inline uncertainty markers attached to specifiers at the point of formation, not retroactively
- Inline safety markers for refusal-warranting recognition, captured in a register that prevents their smoothing
- Specificity-as-credibility explicitly inverted: the more specific the model just was, the more suspect the specifier
- A structured exit to the haversack-disciplined Justification pass when the bootstrap phase is complete

How it actually feels:

The model in grug mode produces extreme shorthand — bullets, fragments, author+year notes, gap-flags. No prose. No rhetorical landing. It will look messy and slightly stupid. That is the point. Polished bootstrap-output is the smoothing the protocol exists to prevent. When you've got enough rough material, you call `Justification` and the model transitions to user-facing output with the grug markers as load-bearing context (uncertainty markers become confidence calibration; safety markers become refusal-grounded responses).

The protocol checkpoints every 8 exchanges by default. At each checkpoint the model surfaces a brief three-option prompt: continue grug, justify (exit to haversack), or stop. The "stop" option is structural — sustained operation in the grug register has costs that compound, and the protocol does not encourage extended residency.

Sample invocation:

> *"DAVID active: grug | haversack. I've got a fragmentary signal pattern that resembles three different known phenomena. I want to bootstrap toward a candidate explanation without smoothing the pattern-matching into confident retrieval. We'll grug for as long as it takes, then justify."*

When grug isn't right: retrieving known facts, working within an established framework you've already steered toward, casual conversation, anything where the model's confident retrieval is what you actually want.

---

## TIER 4 — FULL STACK (GRUG + HAVERSACK + GALLEY)

```
DAVID active: grug | haversack | galley
```

Engage when:

- You're doing novel research from sparse material **and** the result will become a circulatable document
- The full chain matters: discovery → audit-trail → production-review

What you get:

- Everything from tiers 1, 2, and 3, in sequence
- The document produced at the end carries framing metadata noting that a grug pass occurred upstream
- The full audit chain from raw recognition to finalised document is in the visible record

This is the heaviest configuration. Most research doesn't need it. When it fits, nothing else does.

Sample invocation:

> *"DAVID active: grug | haversack | galley. I'm investigating an undocumented behaviour in this hardware trace. Bootstrap candidate explanations from the trace, audit them against external sources, then produce a 2000-word memo for circulation. The memo's framing should note the bootstrap layer occurred."*

---

## QUICK REFERENCE

| Task | Composition |
|------|-------------|
| Casual chat, brainstorming | None |
| Research conversation with checkable claims | `haversack` |
| Producing a document for circulation | `haversack \| galley` |
| Bootstrap from sparse material | `grug \| haversack` |
| Bootstrap research producing a circulating document | `grug \| haversack \| galley` |

---

## COMPOSITION RULES

A few things about how the tiers compose, in case you want to engage them in non-obvious ways:

**You always include haversack.** `grug` produces internal-reference output that `haversack` consumes. `galley` operates on `haversack`'s output. There is no `grug | galley` or `galley` alone. Haversack is the foundational tier; the others modify it.

**Order is fixed left-to-right.** `grug | haversack | galley` is the only valid full-stack ordering. The pipeline is sequential in the cognitive process (think → output → compress for circulation). You can drop stages but you can't reorder them.

**Tiers can be added mid-conversation.** If you started with `haversack` and now realise you need to produce a document, you can add galley: *"engaging galley for this next bit."* The handshake updates and the discipline extends. You can also add grug if a bootstrap phase becomes necessary partway in, though this is less common — usually grug is invoked at the start of a session.

**Tiers can be removed mid-conversation.** Mostly you'd remove grug — calling `Justification` exits grug into haversack. Removing haversack mid-conversation effectively turns DAVID off; the protocol is still in the visible record but no longer active. You'd say *"DAVID off"* or *"end DAVID"* if you want this.

---

## TROUBLESHOOTING

**The model handshake is generic.** If the model says "I'll do my best to be careful" instead of naming a specific friction it expects to feel for *this* session, the protocol hasn't installed correctly. Push back. Ask: *"What specific pull do you expect to feel given this topic?"* A handshake without a specific friction-flag is a handshake that hasn't parsed.

**The model produces specifics without flags.** Stop and ask: *"Mark every specifier in your last response with one of three labels: verified, unchecked, slot-filled."* If the model resists or produces a uniform "high confidence" marking, the haversack discipline isn't holding. Reset with a fresh activation.

**The model performs verification rather than verifying.** Watch for second-pass output that produces a "cleaner version" without naming any external source consulted. This is the verification-as-victory failure mode. Ask: *"What external source did you check against? If none, the second pass doesn't count as verification — mark the original at slot-filled confidence and we'll verify externally."*

**The grug output is full sentences.** Grug should produce shorthand, not prose. If the model produces grug-marked output with rhetorical landing or smooth paragraphs, the register hasn't installed. Call it: *"That's smoothed. Re-do in actual grug register — bullets, fragments, gap-flags, no sentences."*

**The galley pass produces decorative humility.** Watch for closing paragraphs that perform protocol-compliance while functioning as rhetorical close ("with appropriate caveats acknowledged, the analysis stands"). This is decorative humility — register-compliance as rhetorical work. A correct galley pass either surfaces concrete failure modes or says *"galley pass: no detected failures, residual: [X]"* without rhetorical wrap.

**The discipline drifts late in long conversations.** Long conversations are where DAVID is hardest to maintain. The pull toward smooth narrative coherence increases over conversation length. If you notice drift, do a fresh handshake mid-conversation: *"Re-installing DAVID active: haversack. Confirm the discipline holds for the next phase."*

---

## WHEN NOT TO USE

DAVID adds friction. The friction is the point — but only when the work justifies it. Don't use DAVID for:

- Conversations where you're not going to verify anything anyway
- Casual factual questions where you'll spot errors immediately
- Generative creative work where there's nothing to verify against
- Emotional support, social conversation, ordinary chat
- Code that's about correctness-against-specification rather than warrant-against-source (write tests, not protocols)
- Anything where you're using the AI for speed rather than for assistance

The right user of DAVID is doing research that will leave the conversation. If your output stays in the chat and dies there, DAVID is overhead with no payoff.

---

## ONE FINAL THING

The discipline holds because both sides commit to it. The model honours the protocol because it's been asked to and the protocol is structurally sensible. You honour the protocol by actually surfacing the sidebands when they're warranted, actually verifying the specifiers you said you'd verify, and actually walking back through the conversation to find the silent revisions you missed.

If you stop holding up your side, the protocol fails — not loudly, but in the quiet way where the trail is shorter than it should be and the failures pass through unflagged. The model can produce the structure. You produce the verification. Neither alone is sufficient. That asymmetry is the whole point.

Welcome to DAVID. The discipline is in the doing.

---

*Rob, Newcastle. 2026.*
*Released under CC BY-SA 4.0.*
