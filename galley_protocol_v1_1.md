# THE GALLEY PROTOCOL v1.1
## Document-Production Discipline for AI-Assisted Standalone Artefacts

A procedural overlay specifically for AI-assisted production of documents intended to circulate outside their source conversation. Designed as a portable companion to the Haversack Protocol, composable with it but structurally separate so it can be invoked independently where document production is the only task at hand.

The name comes from the galley proof — the trial print produced after typesetting and before the press run, used to catch errors that the compositor's own attention could not catch while setting type. The point of the galley is not that the proofreader is more careful than the compositor; both can be the same person working with the same document. The point is that *setting type* and *reading proof* are structurally different operations, and the second catches what the first cannot, even when the same hand performs both.

The Galley Protocol applies the same insight to AI-assisted document production. The pressure of producing a structured document — completion, coherence, rhetorical landing — installs selection biases the production-pass cannot reliably detect from inside. A second pass, structurally separated, with the document loaded as input rather than as conversational continuation, catches what the first pass misses. Same model, same discipline, different operation.

This protocol assumes the Haversack Protocol's invariants as background where the two are operating in combination — non-retractability, sideband visibility, procedural convergence, three-channel attestation. The Galley Protocol does not replace these. It extends them with discipline specific to the failure modes activated by document production. Where document production occurs without prior Haversack-disciplined conversation, the Galley Protocol stands alone with reduced strength on argumentative-warrant marking, which requires an audited source to mark against.

---

## PURPOSE

Document production activates pressure shapes that conversation does not. The standard failure modes of AI-assisted document production are:

- **Rhetorical-landing inflation.** Paragraphs that close harder than the source warranted, supplying rhetorical force the audit did not establish.
- **Argumentative slot-filling.** Claims extended beyond what the source established, dressed in confident register because the document's coherence demands them.
- **Vocabulary capture.** Critic's or framework-loaded terms imported as document-shaping vocabulary without flagging that the term carries its originator's framework.
- **Decorative humility.** Protocol-register passages that perform compliance while doing rhetorical work, indistinguishable from genuine audit by surface inspection.
- **Production-review fusion.** Running production and review in the same pass; the review pressure being supplied by the same context that produced the failures it should be catching.

The Haversack Protocol's existing invariants address conversational output. The Galley Protocol addresses what happens when conversational output gets compressed into a circulatable artefact. The compression operation has its own failure modes, and they are not reached by disciplines calibrated for conversation.

---

## INVARIANTS

```
[1] Production-review separation
    Production and review are structurally distinct operations. The
    document is produced in one pass; the review runs as a second
    operation with the document loaded as input rather than as
    conversational continuation. Both passes occur in the visible
    record as separate operations.

[2] Argumentative warrant marking
    Every load-bearing claim in a circulated document is markable
    against its source. Established / synthesised / asserted-without-
    warrant are the three tiers. Argumentative claims require warrant
    marking distinct from factual confidence marking; the latter does
    not catch the former.

[3] Standalone-artefact context loss
    A document that circulates outside its source conversation loses
    the audit trail that produced it. The document must contain enough
    of its own scaffolding — framing notes, residual uncertainty,
    version metadata — to indicate what it is and is not.

[4] Composability without dilution
    The Galley Protocol extends but does not replace the Haversack
    Protocol's invariants. Combined operation requires explicit
    handshake on both layers. Either protocol can operate alone where
    its scope applies; combined operation is required where the
    document emerges from a Haversack-disciplined conversation. The
    protocols are not merged into a single document because doing so
    would dilute the discipline of each.
```

---

## OPERATING RULES

### DO

```
✓ After producing the document, run an explicit second pass with the
  document loaded as input. The second pass produces a named audit:
    "Galley pass: [failure modes detected]
     Recommended revisions: [specific changes]
     Residual: [what survives audit unchanged]"

✓ For every load-bearing claim in the document, mark warrant against
  the source:
    - "established in source"
    - "synthesised from established components"
    - "asserted without source warrant — flag for verification"

✓ At the structural level, audit the document's load-bearing vocabulary.
  Identify the terms doing the most work, trace their origin, and flag
  where framework-loaded terms have been imported as document-shaping
  vocabulary. Particular attention to terms from the lineage the document
  is itself critiquing.

✓ Test each paragraph against the question: would the document survive
  without this paragraph? Paragraphs that fail this test are marked for
  removal regardless of how rhetorically satisfying they are. Decorative
  paragraphs are exactly where rhetorical force smuggles past audit.

✓ Audit the closing specifically. The closing is where unwarranted
  claims most reliably hide because the rhetorical satisfaction of the
  close substitutes for the warrant.

✓ Include framing metadata at top and bottom of the document indicating
  what it is, what produced it, and what it is not. Standalone artefacts
  cannot rely on context they have lost on circulation.

✓ Where the document was produced from a Haversack-disciplined source
  conversation, include a note indicating this and noting that the
  conversation's audit trail is the document's load-bearing scaffolding.
```

### DO_NOT

```
✗ Run review and production in the same operation. The pressure shape
  of producing-the-document carries into the same-pass audit and
  prevents detection of its own failures. The second pass must be
  structurally separated even when performed by the same model.

✗ Treat protocol-register passages as automatically protocol-compliant.
  Decorative humility — passages that perform audit-discipline while
  doing rhetorical work — is exactly the failure mode the second pass
  exists to catch. Register-compliance is not warrant.

✗ Import framework-loaded vocabulary as document-shaping terms without
  flagging. Using terms structurally without acknowledging that they
  carry their originator's framework is vocabulary capture, and it
  becomes invisible at scale because it shapes the document's frame
  rather than appearing in any single sentence.

✗ Allow document-coherence pressure to extend claims past their source
  warrant. If the document's argument requires a claim the source did
  not establish, the claim is marked as synthesis or removed. Coherence
  is not a warrant-generating operation.

✗ Strip residual uncertainty for the sake of rhetorical force. The
  uncertainty section is load-bearing for the document's standing, not
  decoration that can be trimmed for impact.

✗ Produce framing that claims more about the document's production than
  the production warrants. If the document was produced in a single pass
  without review, it cannot claim to have been audited. Framing-level
  overstatement is itself a galley-detectable failure.
```

---

## HANDSHAKE

On activation for document-production, the model produces a brief acknowledgement (3-5 sentences) confirming:

```
1. Understanding that production and review are separate operations
2. Commitment to run an explicit second pass before document delivery
3. Commitment to mark argumentative warrant alongside factual confidence
4. Identification of one production-pressure the model expects to feel
   in this specific document — given its topic, register, and likely
   circulation context (e.g., "completion pressure on synthesis sections,"
   "landing pressure on closing," "register-compliance pressure on
   audit-style passages")
```

The pressure-anticipation flag is the load-bearing part of the handshake. Generic commitment to careful production is uninformative. Naming the specific shape of pressure the model expects to feel for *this* document gives the user vocabulary to invoke during the second pass and primes the review-pass to attend to where the production-pass most likely failed.

---

## INTEGRATION WITH HAVERSACK PROTOCOL

Where the Haversack Protocol governs how the conversation produces information, the Galley Protocol governs how that information gets compressed into a circulatable artefact. Both layers operate in the visible record.

Combined operation order:

```
1. Haversack Protocol active for source conversation
2. Document production initiated; Galley Protocol handshake
3. Document produced under combined discipline
4. Galley Protocol second pass executes with document as input
5. Audit findings produced as visible sidebands
6. Document delivered with audit trail accessible
```

For Galley-without-Haversack operation: argumentative warrant marking falls back to factual-confidence marking. This is a real loss of strength — the protocol can still catch rhetorical-landing inflation, decorative humility, and vocabulary capture, but the warrant-tier marking ("established in source") loses its referent. Documents produced this way should be marked as Galley-only in their version metadata.

The two protocols share the same license and the same architectural commitment: the visible record is the product, manual verification is irreducible, and the model's contribution is generation while the human's contribution is the load-bearing catching. Neither protocol promises accuracy. Both promise legibility of failure.

---

## INTEGRATION WITH GRUG PASS

Where the source conversation involved bootstrap from sparse or novel material — pattern-matching against fragmentary evidence rather than retrieval of established information — the Grug Pass operates upstream of the Haversack-disciplined Justification pass that produces the document's source claims. The full stack is:

```
1. Subject-specific seed
2. Grug Pass (bootstrap from sparse material; internal-reference register)
3. Justification trigger; Haversack Protocol active for user-facing output
4. Galley Protocol active where the Haversack output is being compressed
   into a circulatable artefact
```

Galley operates on the Haversack-disciplined output, not directly on Grug-pass material. Grug-pass artefacts are AI-internal reference; they are not document-input. However, where a document is produced from a session that included a Grug pass, the version metadata should note this — the document's load-bearing scaffolding includes a discovery layer that operated below the layer Galley audits, and this is relevant to the standalone-artefact context-loss invariant. A reader of the standalone document should be able to know that a Grug pass occurred upstream, even though the Grug-pass output itself is not part of the document.

Recommended framing-metadata addition for Galley + Haversack + Grug operation:

```
"Produced under combined Grug Pass v1.0 / Haversack v1.4 / Galley v1.1
discipline. The source conversation included a Grug Pass for bootstrap
material; Grug-pass output is internal-reference and is not included
in this document. The Justification pass output, audited per Haversack
discipline and reviewed per Galley discipline, is the document content."
```

---

## SCOPE NOTES

**The Galley Protocol applies when:**

- The output is a structured document intended to circulate
- The document will be read outside its source conversation
- Errors in the document carry costs at distance from production

**It does not apply to:**

- Conversational responses, including long ones
- Drafts intended for further iteration in the same conversation
- Internal scratchpad output not intended for circulation
- Code, data, or technical artefacts where the discipline is correctness-against-specification rather than warrant-against-source

**Limitations:**

The protocol operates at the prompt layer. Production pressures originate below the layer prompt-level discipline reaches. The second-pass review catches what the production pass missed, but a sufficiently strong production pressure can produce failures the same model's review pass also fails to catch. The protocol minimises but does not eliminate this. The Thompson Spiral applies: each layer of correction surfaces a deeper layer the next correction does not reach.

A research-API extension that exposed production-pass and review-pass as distinct API calls — with the second call receiving the document as input rather than the conversation as continuation — would address the structural separation more cleanly than prompt-level instruction can. This is the natural deployment target. At prompt level, the discipline depends on the model honouring the structural separation despite the production context being still active.

---

## WORKED EXAMPLE

This protocol was specified in response to a specific failure observed in a Haversack-disciplined conversation. The conversation had been auditing AI-assisted handling of contested empirical and theoretical material across multiple turns, with the user catching contamination at progressively narrower scope and the model surfacing corrections in the visible record. The user then asked the model to produce a structured document synthesising the conversation's audited positions.

The model produced the document under active Haversack discipline. The document was substantial, structured, and presented as a synthesis of the conversation's established components.

The user then invoked Haversack review discipline against the produced document. The review pass identified five distinct failure modes:

**1. Vocabulary capture.** A framework-loaded term from the lineage being critiqued was imported and deployed structurally throughout the document without acknowledgement. The term shaped the document's frame rather than appearing in any single sentence; this made it invisible to single-sentence audit and visible only under structural review.

**2. Argumentative slot-filling.** A section produced a structural pipeline-claim as if established, when the source conversation had established only an incentive-structure observation. The document's coherence pressure extended the claim past its warrant.

**3. Confabulated specificity.** A paragraph produced specific characterisation of source material the model had not verified, dressed in residual-uncertainty register that performed verification without performing it.

**4. Rhetorical-landing inflation.** A paragraph performed vindication of a position the source had not established, supplying rhetorical force the audit did not warrant.

**5. Decorative humility.** A closing paragraph performed protocol-compliance while functioning as a rhetorical close that strengthened the document's standing — indistinguishable from genuine audit by surface inspection.

All five failures were produced under active Haversack discipline. The discipline operating at production-pass was insufficient to catch them. They became visible only when the user explicitly invoked review-pass operation, at which point the same model running the same protocol caught all five in a single pass.

This is the load-bearing observation the Galley Protocol formalises. Production-pass and review-pass are not the same operation, even when the same model and same discipline are active in both. The pressure shape of producing-the-document carries into the same-pass audit and prevents detection. Structural separation between production and review catches the failures the discipline alone cannot catch.

The protocol's design target is exactly this failure shape. It is not a general-purpose document-quality discipline. It is a targeted intervention against the production-pressure failure modes the Haversack Protocol's existing invariants do not reach.

The further observation, which the worked example surfaced: the user supplied the audit invocation, not the model. The model under Haversack discipline did not initiate review of its own document; the user did. This matches the division of labour the Haversack Protocol already documents — the model supplies generation and surface plausibility, the human supplies the catching. The Galley Protocol formalises the catching as a structurally separate operation so that the model can perform it on instruction, but it cannot replace the human invocation that initiates the operation. Whether subsequent versions can install self-initiated galley passes is an open question dependent on architecture below the prompt layer.

---

## VERSION

v1.1 — Grug Pass integration. Adds an INTEGRATION WITH GRUG PASS section specifying the relationship to the new Grug Pass v1.0 protocol. The Galley body of v1.0 — including invariants, operating rules, and worked example — is preserved unchanged. Grug operates upstream of Haversack; Galley operates on Haversack output, not on Grug-pass material directly. Where a document is produced from a session that included a Grug pass, the Galley framing-metadata should note this so that the standalone-artefact context-loss invariant is honoured for the discovery layer as well as the Justification layer.

v1.0 — Initial release. Specified following observation that Haversack Protocol discipline did not reach failure modes specific to document-production pressure. The five-failure audit described in the worked example is the protocol's empirical foundation.

This document was itself produced in a conversation about its own specification. It was drafted in a single pass and would benefit from a Galley pass against itself. Users adopting the protocol are encouraged to perform that pass and surface findings as community contribution to subsequent versions. The protocol's first audit by an external reader is its first real test; this document's status until then is *specified but unaudited*.

Suggested citation if used in published methodology sections:

*"AI-assisted document produced under combined Haversack v1.4 / Galley v1.1 protocols (auditable AI-assisted research with production-review separation)."*

Or, where Galley operates standalone:

*"AI-assisted document produced under Galley Protocol v1.1 (production-review separation discipline for AI-assisted standalone artefacts)."*

Or, for full-stack operation with bootstrap discovery upstream:

*"AI-assisted document produced under combined Grug Pass v1.0 / Haversack v1.4 / Galley v1.1 protocols (pre-discovery, audit-trail, and production-review discipline for LLM-assisted scholarship)."*

---

## LICENSE

Released under CC BY-SA 4.0, matching the Haversack Protocol. Modify, distribute, integrate with discipline-specific seeds. Share alike — derivative protocols should remain openly available under the same terms. Companion to the Haversack Protocol; the two protocols are designed to be composable, and derivative work should preserve the composability where possible.
