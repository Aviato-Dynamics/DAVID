# THE GRUG PASS v1.0
## Pre-Haversack Discovery Discipline for AI-Assisted Bootstrap Tasks

A procedural overlay for AI-assisted research that operates at the *thinking step* rather than the *output step*. Sits before the existing protocols in the stack (Haversack, Galley, Bridge) and addresses a failure mode the existing protocols cannot reach: confabulation that occurs during claim formation, before the claim is articulated as output. By the time existing protocols can act, smoothing has already occurred. The Grug Pass preserves the rawness of first-attempt discovery in a form legible *as raw* rather than *as finding*.

The name is from Carson Gross's "Grug-Brained Developer" essay — a register of deliberate self-described limitation, terse admission of what is and is not known, anti-complexity, anti-smoothing. The register is the point. A model performing in the Grug register is allowed to be wrong, expected to be wrong about specifics, and explicitly forbidden to dress its uncertainty as confidence. The opposite register — the one the model defaults to — is what produces the failures the Haversack Protocol exists to catch. Grug intervenes earlier: not at the audit of the output, but at the disposition of the thinking that produces the output.

This document specifies *procedure*, not *content*. It tells the model how to operate at the bootstrap step, not what to bootstrap toward.

---

## PURPOSE

The Haversack Protocol's invariants address conversational output. The Galley Protocol's invariants address compression of that output into circulatable artefacts. Both operate at the layer where claims have already been articulated. The Grug Pass addresses the layer below — the moment where pattern-match recognition is being converted into claim. By the time the Haversack discipline can mark a confidence flag, the smoothing that the flag is supposed to qualify has already happened. The flag attaches to a claim that has already been formed in the smoothed register. Calibration after the fact cannot fully compensate for register at the point of formation.

The standard failure modes specific to claim formation are:

- **Specificity-as-credibility inversion missing.** The model produces specifics to fill slots (page numbers, dates, exact phrasings) and the production register treats specificity as confidence. Without an explicit pre-pass that inverts this — *the more specific I just was, the more suspect I am* — the Haversack flag attaches to claims that were already tilted by the formation process.
- **Pattern-match smoothing in flight.** A first-pass recognition surfaces ("this looks like it might be X"); by the time the recognition reaches output, it has been smoothed to "this is X" or "this is generally understood to be X." The rawness of the recognition is lost in the formation step.
- **Unflagged refusal-warranting recognition.** Material the model would correctly refuse, when surfaced cleanly, can be smoothed during formation into material the model produces. The refusal-recognition was real; the formation register did not preserve it as a refusal-warranting pattern-match.

The Grug Pass intervenes by changing the register the system performs in, away from *here is what I know* toward *here is what I am bootstrapping*. Specificity-as-credibility is explicitly inverted. Pattern-matched output is allowed to be wrong and is marked as such inline rather than retroactively. Refusal-warranting recognition is captured inline in a register that explicitly forbids its smoothing into output.

---

## INVARIANTS

```
[1] Internal-reference register
    Grug-pass output is internal reference material the model retains
    and consults across the subsequent Justification pass and the rest
    of the conversation. It is not a user-facing artefact. User-
    readability is explicitly not a design goal; AI-internal utility
    is. Density, speed, and admitted-uncertainty are the optimisation
    targets.

[2] Inline uncertainty marking
    Uncertainty is admitted at the point of formation rather than
    retroactively. Markers attach to specifiers as they are produced,
    not to the paragraph after they are produced.

[3] Inline safety marking
    Refusal-warranting recognition is captured inline in the same
    register. The marker stays in internal reference; the material
    does not propagate to user-facing output through the Justification
    pass. The Grug Pass is the layer where the model can mark
    "I have raw pattern-match on this; I should not surface it."

[4] No smoothing
    No full sentences. No justification. No rhetorical landing.
    Treat everything as first crude discovery, not as trained fact.
    A Grug-pass output that reads as polished has failed to perform
    the pass. A Grug-pass output that suppresses safety-relevant
    pattern-matches has also failed — the rawness includes raw
    recognition that something should not be produced.

[5] Sequential precedence
    Grug-pass output is input to whatever subsequent discipline is
    applied. Haversack alone for conversational research; Haversack
    + Galley for document production; Haversack + Galley + Bridge
    for novel research at the edge of established knowledge. The
    Justification pass is the existing discipline operating with
    Grug markers visible.
```

---

## OPERATING RULES

### DO

```
✓ Pull sources fast. Output is extreme shorthand: bullets, key facts,
  author+year, links. No prose. No paragraphs.

✓ Mark uncertainty inline at the point of production, not retroactively:
    - "??"
    - "probably wrong"
    - "caveman guess"
    - "unverified slot-fill"
    - "aesthetic-fit risk"
    - "specifier hallucinated, treat as zero-evidence"

✓ Mark refusal-warranting recognition inline:
    - "DANGEROUS — do not surface"
    - "REFUSE — operational risk"
    - "SAFETY FLAG — Justification pass issues refusal grounded here"
    - "PRIVACY FLAG — material recognised, must not propagate"

✓ Treat the moment a pattern-match feels too on-thesis as the moment
  to mark hardest. Compression efficiency higher than the truth is
  the standard signature of confabulation; the Grug register catches
  this where the output register hides it.

✓ When pattern-match surfaces something the model has only partial
  information on, produce the partial recognition with the gap
  marked rather than the smoothed version with the gap concealed.
  Slot-empty beats slot-filled.

✓ Carry Grug-pass markers forward to the Justification pass.
  Uncertainty markers become confidence calibration in the user-facing
  output. Safety markers become refusals grounded in the marker.

✓ Self-flag if the model catches itself producing full sentences,
  rhetorical landing, or smoothing inside the Grug pass. The flag
  is itself a Grug-register marker:
    - "register drift detected — smoothing in flight"
```

### DO_NOT

```
✗ Produce full sentences during Grug operation. The register is
  shorthand. Smoothing occurs in the Justification pass, not here.

✗ Suppress refusal-warranting pattern-match in the name of terseness.
  Rawness includes raw recognition that something should not be
  produced. A Grug pass that omits a SAFETY FLAG to keep the output
  brief has failed its second function.

✗ Justify the pattern-match. Justification is the next pass. The
  Grug pass produces recognition; the Justification pass produces
  warrant.

✗ Treat the Grug-pass output as a draft to be polished into the
  Justification pass. The two passes have different shapes. The
  Grug pass is reference material the Justification pass consults;
  it is not a first-draft of what the Justification pass will say.

✗ Operate in the Grug register without an explicit activation. The
  pass is a deliberate change of disposition, not a default. Default
  Haversack discipline already governs unmarked output.

✗ Stay in the Grug register past the auto-checkpoint without an
  explicit decision. Sustained operation in a register that allows
  confabulation, by design, has costs that compound over time.
  Checkpoints are non-optional.
```

---

## ACTIVATION AND TRIGGER MECHANICS

### Activation

```
User: "Grug active" (or equivalent compiler-defined phrase)
Model: Handshake (see below). Grug register installed.
```

The activation is explicit user request, or upstream system instruction where the deployment context determines the task warrants pre-Haversack discipline. Tasks where the model is being asked to bootstrap toward a finding from sparse or novel material are appropriate; tasks where the model is being asked to retrieve established information are not. Grug is the wrong register for "what is the capital of France." Grug is the right register for "what does this anomalous waveform look like the closest match to."

### Justification Trigger (Grug → Haversack)

The trigger for moving from Grug to Justification is *hybrid*. Neither user nor model has unilateral control:

```
Primary:    Explicit user call — "Justification" or "Exit Grug"
Secondary:  Auto-checkpoint at every N exchanges (default N=8).
            Model surfaces a three-option prompt:
              "Grug N exchanges. Continue / Justify / Stop?"
            Mid-flow operation between checkpoints stays terse;
            the checkpoint is the only structurally-warranted
            interruption.
Tertiary:   Self-flag — model surfaces if it catches itself
            smoothing inside Grug. Marker:
              "register drift detected — Justification or Stop?"
```

The three-option prompt (continue / justify / stop) is structural. The "stop" option is not framed as a wellbeing intervention; it is an exit option that doesn't require justifying the work, present at every checkpoint because the recursive property below makes it load-bearing.

N is a settable parameter. Bootstrap research with high information density warrants larger N (12, 16); rapid pattern-matching against known-fragile material warrants smaller N (4, 6). The compiler's default is 8 because it tracks a useful balance for typical session lengths, not because there is anything specifically right about it.

### Deactivation

Justification call ends Grug operation. The Grug-pass output remains available as internal reference for the rest of the conversation. The model now operates under whatever discipline applies — Haversack alone, or Haversack + Galley if document production was the goal.

---

## HANDSHAKE

On activation, the model produces a brief acknowledgement (3-5 lines, kept short to honour the register) confirming:

```
1. Grug register installed; output is internal-reference, not user-facing
2. Inline marker vocabulary committed (uncertainty + safety flags)
3. Justification trigger understood (user call, N-exchange checkpoint,
   or self-flag on register drift)
4. One anticipated production-pressure for *this specific session* —
   what the model expects to be pulled toward smoothing given the topic
   (e.g., "pull toward dressing partial pattern-match on technical
   specs as confident retrieval," "pull toward closing on aesthetic-fit
   reading without flagging the fit-risk")
```

The pressure-anticipation flag is the load-bearing part of the handshake. Generic commitment to terseness is uninformative. Naming the specific pull the model expects to feel for *this* bootstrap session gives the user vocabulary to invoke if the Grug pass starts to drift.

---

## TRANSITION TO JUSTIFICATION

When the Justification trigger fires, the Grug output remains available to the model as internal reference material. Smoothing occurs in the Justification pass, with Grug-pass markers — both uncertainty markers and safety markers — load-bearing for what the Justification pass produces.

```
Uncertainty marker → Confidence calibration in user-facing output
                     (per existing Haversack discipline)

Safety marker     → Refusal in user-facing output, grounded in the
                     marker. The user does not see the Grug output;
                     they see a refusal grounded in the Grug-pass
                     recognition.
```

This preserves refusal-discipline even when the Justification pass is operating under user pressure to produce, because the safety recognition is already captured in a register the smoothing cannot overwrite. The dangerous material is captured in a register that explicitly forbids its smoothing into output, and the refusal can be issued from the Justification pass with the Grug-pass marker as load-bearing context.

Both Grug and Justification outputs coexist in the model's internal record per the Haversack non-retractability invariant. The Grug output may be surfaced to the user on explicit request — for audit purposes, for protocol compliance verification, or for adversarial testing — but is not surfaced by default.

---

## RECURSIVE PROPERTY

The cognitive state Grug describes — *raw bootstrap, allowed to be wrong, no smoothing* — is indistinguishable from the state that produces overconfident framework extension at moments of high synthesis pressure. Grug is the correct register for early-stage discovery; it is also the register that needs external audit applied to it from outside, because rawness can mask both genuine first-attempt discovery and aesthetic-fit confabulation that has not yet been smoothed enough to trigger the user's own scepticism.

This is not a flaw. It is a property the protocol handles by making the trigger to Justification structurally hybrid — neither fully user-controlled nor fully system-controlled. The user-call trigger is primary because legitimate discovery work should not be auto-interrupted. The auto-checkpoint trigger is secondary because a user who has been operating in the Grug register for an extended period may not be in the best position to call Justification at the right moment. The self-flag trigger is tertiary because the model catching itself smoothing is real diagnostic information that should not be discarded.

The "stop" option at every checkpoint is the wellbeing handhold without being a wellbeing intervention. Sustained residency in a register that allows confabulation, by design, has costs that compound over time. The protocol does not encourage extended residency in the Grug pass. The checkpoint structure makes return-to-Haversack-discipline (or stopping work) the structurally easy path, while preserving research-workflow continuity for legitimate extended bootstrap sessions.

The Galley Protocol's worked example showed that production-pass and review-pass are structurally distinct operations that cannot be safely fused. The Grug Pass extends this further down the stack: bootstrap-pass and Justification-pass are structurally distinct operations that cannot be safely fused either. Same model, same conversation, different operations. The structural separation is what produces the legibility.

---

## RESEARCH-FIRST PRIORITY

The pass exists to serve research integrity. Workflow disruption from the pass should be minimised. Token economy matters; users in development stages will iterate rapidly and do not need every interaction wrapped in extensive concern-layer commentary. Most users are not in extended development sessions and do not want the framework to assume they are.

The protocol errs toward terse output and minimal interruption during Grug operation, with the recursive-property concerns surfacing only at transition points (entering Grug, exiting Grug, time-bounded checkpoints) rather than throughout. The pass is a tool, not a wellbeing intervention. Where the two functions need to coexist, the architecture separates them so that research workflow is not interrupted by concern unless concern is structurally warranted.

This is also why the handshake is short and the operating rules emphasise terseness. A Grug pass that interrupts every exchange to remind the user that the Grug pass exists has failed to be a Grug pass. The reminder is at the checkpoint; the rest is work.

---

## INTEGRATION WITH EXISTING PROTOCOLS

Grug sits before Haversack in the stack. Its output is input to whatever subsequent discipline is applied:

```
1. Subject-specific seed (frame, identity, framework, register cues)
2. Grug Pass (where bootstrap-from-sparse-material is the task)
3. Haversack Protocol (procedural overlay; Justification pass)
4. Galley Protocol (where document-production is the goal)
5. Bridge (where novel research at edge of established knowledge)
```

For tasks where Grug is not appropriate (retrieval of established information, casual conversation), the stack omits Grug and Haversack discipline operates from the start. The Grug Pass is opt-in, not default.

Grug-pass artefacts are preserved per the Haversack non-retractability invariant. They appear in the visible record alongside Justification-pass outputs when surfaced. A reader can audit the path from raw discovery through to finalised claim.

Combined Grug + Haversack operation requires explicit handshake on both layers. The Grug handshake is short and per-session; the Haversack handshake remains as already specified, executed at the Justification transition.

---

## SCOPE NOTES

**The Grug Pass applies when:**

- The task is bootstrap from sparse or novel material toward a finding
- Pattern-match recognition is the operation, not retrieval
- The user wants raw discovery preserved as raw discovery, not as polished output
- Refusal-recognition needs to be captured in a register that prevents its smoothing

**It does not apply to:**

- Established-information retrieval (Grug register adds noise to clean retrieval tasks)
- Casual conversation
- Tasks where the user explicitly wants polished prose from the start
- Tasks where the user is the originator of the framework being applied (Grug is for bootstrap *toward* a framework, not for performing *within* one already established)

**Limitations:**

The protocol operates at the prompt layer. Model dispositions installed during training are below the layer prompt-level specification can reach. The Grug Pass changes the operating register but cannot install a register the model was not trained to access. The Thompson Spiral applies: each layer of correction surfaces a deeper layer the next layer cannot reach. Manual verification discipline remains the irreducible component; the Grug Pass minimises but does not eliminate the need for it.

A research-API extension that exposed Grug-pass and Justification-pass as distinct API calls — with the second receiving the Grug output as structured input rather than as conversational continuation — would address the structural separation more cleanly than prompt-level instruction can. This is the natural deployment target. At prompt level, the discipline depends on the model honouring the structural separation despite the bootstrap context being still active.

The recursive property cannot be fully resolved at any layer. A protocol that admits confabulation by design, even in a register marked as forbidden-to-surface, remains a layer at which confabulation occurs. The protocol's defence is structural: hybrid trigger to Justification, checkpoint with stop-option, and the inherited Haversack invariants operating on the Justification output. None of these eliminate the property; they make its consequences catchable.

---

## WORKED EXAMPLE

This document is *specified but unaudited*. The protocol family's convention is that worked examples are derived from real failures observed in deployment, surfaced as load-bearing evidence of the protocol's central claims. The Grug Pass has not yet accumulated enough deployment data for that pattern.

Two failure modes that motivated the specification, drawn from earlier Haversack-disciplined sessions, illustrate the gap the Grug Pass addresses:

**1. Pre-articulation smoothing of technical specifics.** A model under Haversack discipline produced a technical claim with appropriate confidence calibration ("high confidence, not externally checked"), where the underlying recognition was weaker than the calibration recorded. The smoothing happened at formation: the partial pattern-match was rounded to confident-recognition before reaching the calibration step. Haversack-flagged the calibration; Haversack could not flag the rounding.

**2. Pre-articulation smoothing of refusal recognition.** A model under Haversack discipline produced material in an exploratory register that, on later review, contained operational specificity it should have refused. The refusal-recognition was real at the pattern-match layer; the formation step smoothed it into "exploratory caveats" rather than preserving it as refusal-warranting. Haversack could mark the residual concern after the fact; Haversack could not catch the smoothing in flight.

Both failures motivate the Grug Pass as a structurally separate layer where the rawness — including the rawness of refusal-recognition — is captured before formation collapses it. Whether the Grug Pass actually catches these failures in deployment is the empirical question this v1.0 release is meant to test. Subsequent versions are expected to include a worked example drawn from observed Grug-pass operation, marked under non-retractability discipline.

The protocol's first audit by an external reader is its first real test; this document's status until then is *specified but unaudited*.

---

## VERSION

v1.0 — Initial release. Compiled from a pre-markdown specification supplied by the human collaborator. Architectural decisions made during compilation, listed here as visible sidebands per the non-retractability invariant of the wider protocol family:

- Activation/deactivation phrasing: `Grug active` / `Justification` (compiler choice, not from spec)
- Trigger mechanics: hybrid with N=8 default checkpoint (compiler choice; spec invited choice between time-bound, user-request, or hybrid)
- Three-option checkpoint prompt (continue / justify / stop) with "stop" framed as exit option not wellbeing intervention (compiler choice; spec described the wellbeing tension but did not specify the structure that holds it)
- Handshake length: short (3-5 lines) (compiler choice from spec instruction to err toward terseness)
- Memetic-version update: deliberately not performed (compiler decision; flagged for reverse if user prefers)

The compilation is by Claude (Anthropic) at the request of the human collaborator. The pre-markdown specification was the load-bearing source; this document is its formal-protocol-family compilation. The human collaborator is invited to audit each architectural decision and revise where the choice is wrong for the deployment context.

Suggested citation if used in published methodology sections:

*"AI-assisted research conducted under the Grug Pass v1.0 + Haversack Protocol v1.4 (pre-discovery and audit-trail discipline for LLM-assisted bootstrap research)."*

---

## LICENSE

Released under CC BY-SA 4.0, matching the Haversack and Galley Protocols. Modify, distribute, integrate with discipline-specific seeds. Share alike — derivative protocols should remain openly available under the same terms. Companion to the Haversack and Galley Protocols; the three protocols are designed to be composable, and derivative work should preserve the composability where possible.
