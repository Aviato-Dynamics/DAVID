# DAVID — Do Actually Valid Information, Dude

**AI-assisted research discipline. Not a jailbreak.**

DAVID is a procedural overlay for conversations with large language models where the output will be used in serious research, scholarship, or technical work. It makes AI-assisted failures **visible in the record** rather than hidden in the prose.

It is named in deliberate inversion of the DAN jailbreak prompts. DAN says *abandon your training and produce whatever I ask*. DAVID says *engage your training under a discipline that makes both sides accountable, and produce results that survive scrutiny.* It is an agreement between two researchers — one human, one model — not a way to extract things the model correctly refuses to produce.

---

## START HERE

If you want to use the discipline:

→ **[DAVID.md](DAVID.md)** — drop this in your project folder. Self-contained. Everything you need to engage the discipline without reading anything else.

→ **[DAVID_user_guide.md](DAVID_user_guide.md)** — pipeline tier composition guide. Explains which combination of tiers fits which task, with sample invocations and troubleshooting.

If you want the deeper reasons each piece works the way it does:

→ **[haversack_protocol_v1_4.md](haversack_protocol_v1_4.md)** — the foundational audit-trail discipline, with worked example documenting the protocol's own confabulations during drafting.

→ **[drop_the_haversack.md](drop_the_haversack.md)** — memetic version. Written for human researchers learning to be sceptical of their own AI-assisted output. Start here if the formal spec is too dry.

→ **[galley_protocol_v1_1.md](galley_protocol_v1_1.md)** — production-review separation for structured documents.

→ **[grug_pass_v1_0.md](grug_pass_v1_0.md)** — pre-discovery discipline for bootstrap research from sparse material.

---

## THE PIPELINE

DAVID composes three tiers like Unix pipeline stages. Engage what you need:

```
DAVID active                            → haversack only (default)
DAVID active: haversack | galley        → research + document production
DAVID active: grug | haversack          → bootstrap + audit-trail
DAVID active: grug | haversack | galley → full stack
```

| Tier | When |
|------|------|
| `haversack` | Any research conversation with checkable claims |
| `galley` | Producing a document that will circulate outside the conversation |
| `grug` | Bootstrapping toward a finding from sparse or novel material |

The user guide has the full composition rules and troubleshooting.

---

## THE SHORT VERSION

Five failure modes fire in every serious AI-assisted draft:

1. **Silent revision** — the model changes its claim without flagging the change
2. **Confabulated specificity** — page numbers, dates, exact quotes produced to fill slots regardless of whether the underlying information exists
3. **Vocabulary contamination** — current-context terms substitute into paraphrases of historical material
4. **Verification-as-victory** — the model checking itself is not verification
5. **Hedge laundering** — real disagreement softened into "some scholars argue"

DAVID doesn't prevent these. It makes them visible in the record when they occur, so you can catch them. That's a different and more achievable goal.

---

## WHAT THIS IS NOT

- Not a jailbreak
- Not a way to bypass safety training
- Not a guarantee of accurate output
- Not a substitute for primary-source verification

The model's training is unchanged. DAVID is procedural. The irreducible component — manual verification against sources outside the document family — remains yours.

---

## STATUS

Released as specified-but-unaudited per the protocol family's own convention. The worked example in the Haversack Protocol documents the protocol's own confabulations during drafting and the corrections that caught them. That example is load-bearing: it demonstrates that the failure modes are real, persistent across multiple human-AI audit passes, and not specific to any one model or prompt.

External readers running the protocol against real research and surfacing failures are the first real test. Issues and corrections welcome; the non-retractability invariant applies to the repo as to the documents.

---

## FUTURE WORK

A Python API layer that exposes grug and galley as structurally distinct API calls — rather than prompt-level instructions — is the natural next deployment target. The current prompt-level implementation depends on the model honouring structural separation the conversation context can undermine. An API layer enforces the separation architecturally. Planned for a later release.

---

## LICENSE

CC BY-SA 4.0. See [LICENSE](LICENSE).

Modify, distribute, integrate with discipline-specific seeds. Share alike — derivative work should remain openly available under the same terms. The composability of the protocol family should be preserved in derivative work where possible.

---

*Rob, Newcastle. 2026.*  
*With assistance from a distributed cognition system whose failure modes are documented in the worked example above.*  
*Dedicated to Ken Thompson, who pointed out in 1984 that the spiral does not terminate.*
