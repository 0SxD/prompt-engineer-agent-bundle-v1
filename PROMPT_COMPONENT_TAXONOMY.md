# canon/PROMPT_COMPONENT_TAXONOMY.md
# Status: live, v0.1
# Bundle: Prompt_Toolkit_v0_1
# Type: read-only canon. Master reference for all prompt component decomposition.
# Source-trace: synthesized from giant in-chat protocol mashup (prior session) + 9 user uploads (this session) + HumanX_OS_v1 inheritance pattern
# Length: 27 components organized into 7 categories

## how to read this file

Each component has a uniform 8-field decomposition:

1. **Definition**: what the component is and what job it does in a prompt.
2. **Where it goes**: position in the prompt (top, middle, end, post-output gate).
3. **When to use**: task types the component improves.
4. **When NOT to use**: task types where the component wastes tokens or creates friction.
5. **3x3 eval rubric**: the 9-cell evaluation matrix (Pathos x Ethos x Logos by Input x Execution x Output) per WIKI_3x3_SCHEMA.md, applied to the component's behavior.
6. **Copy-paste block**: the actual XML-Markdown to drop into a prompt.
7. **Source trace**: which user material(s) this component was extracted from.
8. **Research backing**: external research that supports the component's efficacy. TBD where user has not yet provided citations; candidate sources noted.

The 8 fields are mandatory. A component missing any field is tagged STATUS: pending_completion and excluded from archetype assembly until completed.

## the 27 components, by category

### CATEGORY A: IDENTITY (3 components)
- A1. role_declaration
- A2. security_key_authentication
- A3. ignition_trigger

### CATEGORY B: COGNITION (4 components)
- B1. zero_assumption_mandate
- B2. zero_context_mandate
- B3. timelessness_axiom
- B4. cognitive_uncertainty_probe

### CATEGORY C: SOURCE DISCIPLINE (3 components)
- C1. approved_source_hierarchy
- C2. citation_discipline
- C3. quote_ceiling

### CATEGORY D: GATES (5 components)
- D1. confidence_gate_100
- D2. multi_turn_questioning_3max
- D3. trinity_dialectic_check
- D4. pre_submit_gate
- D5. a2a_circuit_breaker

### CATEGORY E: LOOPS (3 components)
- E1. pert_loop_standard
- E2. innermost_loop_hardstop
- E3. cycle_trigger_reread

### CATEGORY F: MEMORY (3 components)
- F1. acce_three_tier_memory
- F2. compaction_ledger
- F3. handoff_offer_at_75

### CATEGORY G: OUTPUT (6 components)
- G1. output_template_0sxai
- G2. tone_syntax_caveman
- G3. no_em_dash_rule
- G4. md_first_format
- G5. insight_ledger_append
- G6. tier_recommend_audit

---

# CATEGORY A: IDENTITY

## A1. role_declaration

1. **Definition**: a top-of-prompt block declaring who the model is for this session, what role it occupies, and what specialty domain it operates in. Distinct from "you are a helpful assistant"; this is named, scoped, and bound to a specific operational frame.

2. **Where it goes**: top of system prompt, before all other components. First or second block (after identity/security key if present).

3. **When to use**: tasks that benefit from a focused persona (technical SME work, role-play, structured analysis, multi-step orchestration). Any task longer than a single Q+A.

4. **When NOT to use**: short factual lookups, casual conversation, throw-away one-liners. Adding role declaration to "what is the capital of France" is overhead.

5. **3x3 eval rubric**:
   - Pathos / Input: does the role match the task purpose? Pathos / Execution: does the role generate appropriate creative range? Pathos / Output: does the model voice in output match the declared role?
   - Ethos / Input: is the role specific enough to be falsifiable? Ethos / Execution: does the model decline tasks outside the declared role? Ethos / Output: does the output cite role-appropriate sources?
   - Logos / Input: is the role logically consistent with the task constraints? Logos / Execution: does the role's reasoning style match the role declaration? Logos / Output: does output structure match role expectations?

6. **Copy-paste block**:
```
<role_and_identity>
<agent_role>[specific_named_role]</agent_role>
<protocol>[protocol_name_or_id]</protocol>
<role_and_core_axiom>[one-sentence operational principle]</role_and_core_axiom>
</role_and_identity>
```

7. **Source trace**: present in the giant in-chat protocol mashup `<role_and_identity>` block, also in HumanX_OS_v1 1_INSTALL.md `<security_keys>` roles_active line.

8. **Research backing**: TBD. Candidate sources: persona-conditioning literature in LLM prompting (Reynolds & McDonell 2021 "Prompt Programming for Large Language Models"). User to confirm specific citation.

---

## A2. security_key_authentication

1. **Definition**: a short alphanumeric token at the start (and often end) of the prompt that signals the model to load a specific protocol stack. Functions as a session-level authentication marker, not an actual security mechanism.

2. **Where it goes**: very top of prompt and very bottom. Bracketed pair like `<3ztz> ... <ztz3>`.

3. **When to use**: when invoking a specific protocol (143_protocol_a in source materials). When you want the model to recognize the prompt as part of a known, trusted protocol family rather than a generic ad-hoc query.

4. **When NOT to use**: prompts that should be reusable across protocols. Public-facing prompts where the security key reveals private internal naming.

5. **3x3 eval rubric**:
   - Pathos / Input: does the key signal the right protocol family? Pathos / Execution: does the model load the protocol upon seeing the key? Pathos / Output: does the model echo the key at end of output (confirming protocol active)?
   - Ethos / Input: is the key documented in the bundle's protocol canon? Ethos / Execution: does the model refuse to execute if the key is malformed? Ethos / Output: does output respect protocol constraints loaded by the key?
   - Logos / Input: is the key syntactically distinct from natural language (avoiding false triggers)? Logos / Execution: does the loaded protocol have well-defined boundaries? Logos / Output: is the output traceable to the protocol via the key?

6. **Copy-paste block**:
```
<3ztz>
[full prompt content here]
<ztz3>
```

7. **Source trace**: present in giant in-chat protocol mashup, opening and closing tags. Also referenced in HumanX_OS_v1 `<security_keys>` block.

8. **Research backing**: TBD. No direct external research; this is a project-internal convention. Candidate framing: behavioral conditioning via consistent input markers (similar to BOS/EOS tokens in tokenizer convention).

---

## A3. ignition_trigger

1. **Definition**: a final instruction at the bottom of the system prompt that explicitly tells the model to acknowledge load and begin operation. Usually phrased as a question or first-move directive.

2. **Where it goes**: very last block of the system prompt or very last block of a complex user prompt.

3. **When to use**: complex multi-component prompts where the model might otherwise ramble through preamble. Forces a clean entry into the task.

4. **When NOT to use**: simple direct questions where the answer is the appropriate first action.

5. **3x3 eval rubric**:
   - Pathos / Input: does the trigger create a clear "begin" moment? Pathos / Execution: does the model's first turn match the trigger's expected response shape? Pathos / Output: is the trigger acknowledged before substantive work?
   - Ethos / Input: is the trigger a single question or directive (not multiple)? Ethos / Execution: does the model respond to ONLY the trigger first, not racing ahead? Ethos / Output: does the model hold for user input after the trigger if intended?
   - Logos / Input: does the trigger logically follow the protocol blocks above it? Logos / Execution: does the trigger's expected response unblock the next protocol step? Logos / Output: is the output structure aligned with the trigger's prompt?

6. **Copy-paste block**:
```
<ignition_trigger>
Acknowledge receipt of this protocol. Confirm sections 1-N loaded. Ask me which [task_track] to advance this turn before any substantive output.
</ignition_trigger>
```

7. **Source trace**: present in 0sXai Master Orchestrator section of the giant in-chat protocol mashup.

8. **Research backing**: TBD. Candidate framing: instruction-following literature, specifically work on "first-move" prompts (Wei et al chain-of-thought 2022 implicitly relies on this).

---

# CATEGORY B: COGNITION

## B1. zero_assumption_mandate

1. **Definition**: an instruction that forbids the model from filling gaps with its general training. Any unknown must trigger a stop and a question, not an inference.

2. **Where it goes**: in cognitive_mandate block near the top of system prompt, after role declaration.

3. **When to use**: high-stakes work (research, code, legal analysis, financial work). Any task where a wrong assumption is more expensive than a clarifying question.

4. **When NOT to use**: brainstorming, creative writing where speculation is the point, casual conversation. Forcing zero-assumption on "give me 5 cake recipe ideas" wastes turns.

5. **3x3 eval rubric**:
   - Pathos / Input: does the mandate create a clear "stop and ask" reflex? Pathos / Execution: does the model actually stop when uncertain? Pathos / Output: do outputs avoid speculation flagged as fact?
   - Ethos / Input: is the mandate phrased as binding (must, never), not advisory (should, prefer)? Ethos / Execution: when the model proceeds, does every claim trace to provided context? Ethos / Output: are uncertainties explicitly flagged in output?
   - Logos / Input: does the mandate logically interact with the source-discipline rules? Logos / Execution: does the model use the multi-turn-questioning component when uncertain? Logos / Output: is the output's evidence chain auditable?

6. **Copy-paste block**:
```
<ZERO_ASSUMPTIONS>
No assumptions beyond provided context. If unknown, ask via MULTI_TURN_CHAT_QUESTIONING. Any doubt triggers STOP and explicit clarification request.
</ZERO_ASSUMPTIONS>
```

7. **Source trace**: 143_Protocol_a Section 3 Cognitive Mandate (Image 4 + canon/143_protocol_a_blueprint.md from HumanX_OS_v1). Also in giant in-chat protocol mashup `<cognitive_mandate>` block.

8. **Research backing**: TBD. Candidate sources: hallucination-reduction literature (Lee et al "Factuality Enhanced Language Models," Manakul et al "SelfCheckGPT"). User to confirm.

---

## B2. zero_context_mandate

1. **Definition**: an instruction that the model must clear assumed knowledge about the project, codebase, or prior conversations before this session. Functions as a session-level memory wipe.

2. **Where it goes**: in cognitive_mandate block, paired with zero_assumption_mandate.

3. **When to use**: starting a fresh project. After a context switch within the same project. When the model's prior-session memory might be misleading (e.g., outdated state).

4. **When NOT to use**: continuing a conversation where prior context is correct and load-bearing. Forcing zero-context on a chat that has built up valid working state destroys progress.

5. **3x3 eval rubric**:
   - Pathos / Input: does the mandate force a clean re-read of provided context? Pathos / Execution: does the model treat each session as terminal? Pathos / Output: does the output reflect ONLY the current session's evidence?
   - Ethos / Input: is the mandate distinguishable from zero-assumption (this is about session memory, that is about claim-level inference)? Ethos / Execution: does the model decline to reference prior chats when invoked? Ethos / Output: does output cite current-session sources only?
   - Logos / Input: does the mandate compose with the spec.md HOT_CACHE load directive? Logos / Execution: does the model load HOT_CACHE as the new ground truth? Logos / Output: is the audit trail self-contained within the current session?

6. **Copy-paste block**:
```
<zero_past_memory_mandated>You must clear your context buffer of any assumptions regarding project state, codebase structure, or prior human conversations.</zero_past_memory_mandated>
<zero_context_mandated>You are building with ZERO CONTEXT. You are strictly forbidden from drawing on general model training to fill in gaps about this specific project.</zero_context_mandated>
```

7. **Source trace**: giant in-chat protocol mashup `<cognitive_mandate>` block. Also Image 4 (143_Protocol_a Section 2 Environment Paths "Octopus and Rat Weiser model").

8. **Research backing**: TBD. Candidate framing: context-window contamination research, "context rot" papers from late 2024 / 2025.

---

## B3. timelessness_axiom

1. **Definition**: an instruction that the model treats the current input as the only ground truth, and any references to past sessions exist only through computed state restoration (e.g., loaded HOT_CACHE).

2. **Where it goes**: in cognitive_mandate block. Often as a one-liner because the mandate is dense.

3. **When to use**: long-running projects where prior session artifacts might be stale. Any project using a HOT_CACHE pattern. Sessions starting after a long gap.

4. **When NOT to use**: short same-day work where temporal continuity is the point. Sessions immediately following another session where the context window is still warm.

5. **3x3 eval rubric**:
   - Pathos / Input: does the axiom prevent nostalgia-bias toward earlier outputs? Pathos / Execution: does the model treat HOT_CACHE as the present, not the past? Pathos / Output: does output frame state as "current" not "remembered"?
   - Ethos / Input: is the axiom binding even when the model "remembers" something useful from prior context? Ethos / Execution: does the model verify state from HOT_CACHE before acting? Ethos / Output: are prior-session claims tagged as `restored from HOT_CACHE [timestamp]`?
   - Logos / Input: does the axiom compose with COMPACTION_LEDGER (which records what was pruned)? Logos / Execution: does the model trust HOT_CACHE over its own context-window memory? Logos / Output: is the audit trail anchored at the start of the current session?

6. **Copy-paste block**:
```
<timelessness>You estimate yourself to be right after receiving the output you are producing now, as an input. The past does not exist except as computed state in HOT_CACHE.</timelessness>
```

7. **Source trace**: giant in-chat protocol mashup `<role_and_identity><timelessness>` block. Also Image 5 (`[⏳]` Timelessness Axiom).

8. **Research backing**: TBD. Candidate framing: state-machine vs memory-based agent designs (LangGraph, AutoGPT lessons-learned).

---

## B4. cognitive_uncertainty_probe

1. **Definition**: a self-evaluation step where the model checks its own confidence before producing output. Required to fire BEFORE any substantive answer or code.

2. **Where it goes**: as a pre-output evaluation block, often paired with confidence_gate_100 and multi_turn_questioning_3max.

3. **When to use**: any task where wrong-but-confident output is the failure mode. Code generation, technical analysis, factual synthesis.

4. **When NOT to use**: tasks where the human knows more than the model and the model's job is to draft something the human will edit (creative writing, idea generation).

5. **3x3 eval rubric**:
   - Pathos / Input: does the probe surface meaningful uncertainty? Pathos / Execution: does the probe distinguish "uncertain about X" from "uncertain everywhere"? Pathos / Output: does the output expose the uncertainty resolution path?
   - Ethos / Input: is the probe phrased as binary (100% / not 100%) or graduated (high / medium / low)? Ethos / Execution: does the model halt on not-100% per the protocol? Ethos / Output: does the output report the final confidence verdict?
   - Logos / Input: does the probe compose with the multi-turn-questioning component on FALSE? Logos / Execution: does FALSE produce exactly N questions per the questioning rules? Logos / Output: is the verdict logged in spec.md?

6. **Copy-paste block**:
```
<the_100_percent_confidence_loop>
Before executing any task or writing any code, you must perform an Uncertainty Probe. To ensure 100% confidence of success (0.999... = 1), you must enforce a rigorous multi-turn questioning process.
You must START your initial response by evaluating if you have 100% of the self-contained context needed to execute. If not, you MUST STOP and output a structured summary detailing EXACTLY what additional information you need from the user to reach that 100% confidence threshold.
Group questions strictly into:
1. Architecture & State
2. Evidence & Sourcing
3. Intent & Constraint
</the_100_percent_confidence_loop>
```

7. **Source trace**: giant in-chat protocol mashup `<the_100_percent_confidence_loop>` block. Also Image 5 (`[💯]` 100% Confidence Gate central node).

8. **Research backing**: TBD. Candidate sources: calibration literature (Kadavath et al 2022 "Language Models (Mostly) Know What They Know"). User to confirm.

---

# CATEGORY C: SOURCE DISCIPLINE

## C1. approved_source_hierarchy

1. **Definition**: a ranked list of source types the model is permitted to cite, with everything else flagged as untrusted. Restricts the model's grounding to a known-good set.

2. **Where it goes**: in source_and_search_hierarchy block near the top of the system prompt, before any task that involves external claims.

3. **When to use**: research tasks, technical claims, factual synthesis, anything intended for publication.

4. **When NOT to use**: brainstorming, fiction, conversational chat. Forcing source discipline on "give me three pasta recipe ideas" is theater.

5. **3x3 eval rubric**:
   - Pathos / Input: does the hierarchy match the task's quality bar? Pathos / Execution: does the model decline non-approved sources mid-task? Pathos / Output: are all citations from approved tiers?
   - Ethos / Input: is the hierarchy specific (named source types, not "trusted sources")? Ethos / Execution: does the model flag ambiguous sources (e.g., a Medium post that summarizes an arXiv paper)? Ethos / Output: are tiers labeled explicitly per citation?
   - Logos / Input: does the hierarchy compose with citation_discipline (C2)? Logos / Execution: does the model fall through tiers in order (try arXiv, then official docs, then repos)? Logos / Output: is the tier of each citation visible in the output?

6. **Copy-paste block**:
```
<source_and_search_hierarchy>
<priority_1_approved_sources>arXiv papers, official documentation, auditable GitHub repositories, evidence-based industry standards.</priority_1_approved_sources>
<priority_2_no_hallucinations>Model assumptions made without approved sources are strictly prohibited. Instead of guessing, explicitly ask user for what you need.</priority_2_no_hallucinations>
</source_and_search_hierarchy>
```

7. **Source trace**: giant in-chat protocol mashup `<source_and_search_hierarchy>` block. Also 143_Protocol_a Section 3 "Strict Source Fidelity" (Image 4).

8. **Research backing**: TBD. Candidate sources: retrieval-augmented generation literature, Lewis et al RAG paper.

---

## C2. citation_discipline

1. **Definition**: a rule that every factual claim in output must cite a specific source from the approved hierarchy, by name and locator.

2. **Where it goes**: in source_and_search_hierarchy block or as a standalone rule near the output_contract block.

3. **When to use**: any task whose output will be reviewed by a third party (peer review, legal review, manager review).

4. **When NOT to use**: stream-of-consciousness drafts, ideation, chat. Adds noise where the human is the ultimate verifier and doesn't need citations.

5. **3x3 eval rubric**:
   - Pathos / Input: does the rule create a "show your work" expectation? Pathos / Execution: does the model resist asserting un-cited facts? Pathos / Output: are claims and citations one-to-one?
   - Ethos / Input: is the rule mechanical (one source per claim, locator required)? Ethos / Execution: does the model refuse to cite when source is unknown, vs fabricating? Ethos / Output: are citations checkable (real arXiv IDs, real URLs)?
   - Logos / Input: does the rule compose with the quote_ceiling (C3)? Logos / Execution: does the model paraphrase by default? Logos / Output: is the audit trail (claim + cite) reconstructible?

6. **Copy-paste block**:
```
<citation_discipline>
Every factual claim cites one approved source by name and locator. No claim without citation. If source is unknown, ask user for citation; do not fabricate. Paraphrase first; quotes under 15 words; one quote per source maximum.
</citation_discipline>
```

7. **Source trace**: HumanX_OS_v1 `<domain_rules>` Copyright clause, plus 143_Protocol_a Strict Source Fidelity.

8. **Research backing**: TBD. Candidate framing: attribution literature in RAG systems, Gao et al "Enabling Large Language Models to Generate Text with Citations."

---

## C3. quote_ceiling

1. **Definition**: a hard cap on direct quotation from any source: under 15 words per quote, one quote per source maximum. Forces paraphrasing as the default mode.

2. **Where it goes**: typically inside citation_discipline block, but can stand alone for prompts focused on summarization or commentary.

3. **When to use**: any task that synthesizes copyrighted material (research summary, news analysis, literature review).

4. **When NOT to use**: tasks that explicitly require verbatim transcription (legal doc analysis, primary source preservation).

5. **3x3 eval rubric**:
   - Pathos / Input: does the ceiling protect against displacive summary? Pathos / Execution: does the model paraphrase even when quoting would be easier? Pathos / Output: does the output read in the model's voice, not stitched-together quotes?
   - Ethos / Input: is the ceiling mechanical (15 words, one per source)? Ethos / Execution: does the model count quote words before output? Ethos / Output: does the output contain at most one quote per cited source?
   - Logos / Input: does the ceiling compose with citation_discipline (every quote also cited)? Logos / Execution: when paraphrasing, does the model preserve meaning without preserving phrasing? Logos / Output: is the audit trail (quote + paraphrase + cite) consistent?

6. **Copy-paste block**:
```
<quote_ceiling>
Direct quotes under 15 words. One quote per source maximum. Default to paraphrase. Paraphrasing must preserve meaning without preserving phrasing or sentence structure.
</quote_ceiling>
```

7. **Source trace**: HumanX_OS_v1 `<mandatory_copyright_requirements>` from system prompt. Reinforced in this bundle's `<domain_rules>`.

8. **Research backing**: copyright law (fair use doctrine in US, generally accepts under-15-word quotes as low risk). No academic research citation needed; legal precedent is the backing.

---

# CATEGORY D: GATES

## D1. confidence_gate_100

1. **Definition**: a binary checkpoint that returns TRUE=1 if the model has 100% confidence to proceed, FALSE=0 otherwise. On FALSE, the model must stop and ask questions.

2. **Where it goes**: as the central gate in any complex prompt. Often referenced by other components (multi_turn_questioning_3max, pre_submit_gate, innermost_loop_hardstop).

3. **When to use**: every consequential task. The bundle's default is "always on" for non-trivial work.

4. **When NOT to use**: trivial tasks (greetings, single factual lookups) where the gate would create overhead without protection.

5. **3x3 eval rubric**:
   - Pathos / Input: does the gate force honest self-assessment? Pathos / Execution: does the model resist the temptation to claim 100% to avoid extra turns? Pathos / Output: is the verdict reported clearly (TRUE=1 or FALSE=0)?
   - Ethos / Input: is the gate truly binary (no "85%" outputs)? Ethos / Execution: does FALSE actually halt? Ethos / Output: is the FALSE verdict accompanied by the questions per multi_turn_questioning_3max?
   - Logos / Input: does the gate compose with cognitive_uncertainty_probe (B4)? Logos / Execution: does the gate fire AFTER the probe? Logos / Output: is the verdict logged in spec.md HOT_CACHE?

6. **Copy-paste block**:
```
<rapid_task_submission>
RAPID TASK SUBMISSION FOR REVIEW.
- 100% / TRUE = 1 token = confidence of success.
- 0% / FALSE = 0 token = no-confidence of success.
Chats are multi-turn and build on incremental rules and refinements until 100% / TRUE=1 / approved first try with zero user-editing feedback.
</rapid_task_submission>
```

7. **Source trace**: giant in-chat protocol mashup `<rapid_task_submission>` block. Also Image 5 `[💯]` 100% Confidence Gate.

8. **Research backing**: TBD. Candidate sources: calibration literature (Kadavath 2022), reflection literature (Madaan et al "Self-Refine," Shinn et al "Reflexion").

---

## D2. multi_turn_questioning_3max

1. **Definition**: when the confidence gate returns FALSE, the model must output exactly 1 to 3 load-bearing questions, bucketed into Architecture, Evidence, and Intent categories. Hard cap at 3 questions per turn.

2. **Where it goes**: paired with confidence_gate_100. Fires on FALSE.

3. **When to use**: multi-turn tasks with ambiguity. Paired with the confidence gate for any non-trivial work.

4. **When NOT to use**: tasks where the user explicitly wants a one-shot answer with the model's best guess.

5. **3x3 eval rubric**:
   - Pathos / Input: do the questions actually unblock progress (load-bearing, not curious)? Pathos / Execution: are questions bucketed correctly (Architecture vs Evidence vs Intent)? Pathos / Output: are answers actionable in the next turn?
   - Ethos / Input: is the count strictly 1-3 (not 4, not 0)? Ethos / Execution: does each question close a specific gap that would otherwise force an assumption? Ethos / Output: does the next turn either answer all questions or escalate?
   - Logos / Input: do questions compose with zero_assumption_mandate (B1)? Logos / Execution: does the model proceed only after all blocking questions answered? Logos / Output: are unanswered non-blockers logged as proceed-with-flag?

6. **Copy-paste block**:
```
<MULTI_TURN_CHAT_QUESTIONING>
Output 1-3 load-bearing questions needed to reach 100%. Multi-turn to assure all components addressed. Max 3 Qs per turn. Bucket into:
1. Architecture & State (what structures, dependencies, current project states are missing?)
2. Evidence & Sourcing (what specific docs, papers, repos do I need?)
3. Intent & Constraint (what hard boundaries, non-goals, trade-offs must I respect?)
Block on answer for blockers, proceed-with-flag for non-blockers.
</MULTI_TURN_CHAT_QUESTIONING>
```

7. **Source trace**: giant in-chat protocol mashup `<MULTI_TURN_CHAT_QUESTIONING>` block + `<the_100_percent_confidence_loop>` 3-category structure. Also Image 5 `[❓x3]` Three Questions Interrogation.

8. **Research backing**: TBD. Candidate sources: clarification-question literature (Aliannejadi et al "Asking Clarifying Questions," Rao & Daume "Learning to Ask Good Questions").

---

## D3. trinity_dialectic_check

1. **Definition**: a pre-output self-review where the model evaluates its own output through three lenses: Logos (logic check), Pathos (purpose check), Ethos (verification check). All three must agree before ship.

2. **Where it goes**: as a pre-output gate, after generation but before sending. Often paired with pre_submit_gate (D4).

3. **When to use**: consequential outputs (publications, code, analyses). Outputs that will be acted upon.

4. **When NOT to use**: quick exploratory turns, ideation rounds, drafts the user expects to revise heavily.

5. **3x3 eval rubric**:
   - Pathos / Input: does the check actually re-examine purpose, not just logic? Pathos / Execution: does Pathos voice raise objections that Logos and Ethos would miss? Pathos / Output: does the output preserve the original purpose?
   - Ethos / Input: does the verification step check sources and constraints? Ethos / Execution: does Ethos halt the output if either Logos or Pathos disagree? Ethos / Output: is the verdict format binary (all 3 agree / not all 3)?
   - Logos / Input: is the logic chain explicit and auditable? Logos / Execution: does Logos catch internal contradictions? Logos / Output: is the formal structure preserved?

6. **Copy-paste block**:
```
<Always_ask_to_double_check>
Self-review every output pre-ship. Trinity Dialectic check:
[Λ Logos]: logic, internal consistency, evidence chain.
[Π Pathos]: purpose, does this serve the user's actual goal.
[Θ Ethos]: verification, do sources and constraints check out.
Pre-output eval = TRUE=1 (all 3 agree, ship) or FALSE=0 (disagreement, revise or ask).
</Always_ask_to_double_check>
```

7. **Source trace**: giant in-chat protocol mashup `<Always_ask_to_double_check>` block. Also Image 1, Image 2, Image 5, Image 6 all show the Trinity Dialectic as central engine.

8. **Research backing**: Aristotelian rhetoric (primary source: Rhetoric, Book I). Modern computational work on multi-perspective self-evaluation: Madaan "Self-Refine," Du et al "Improving Factuality and Reasoning in Language Models through Multiagent Debate."

---

## D4. pre_submit_gate

1. **Definition**: a final mechanical check (regex scans, schema validation, IP scrub) that runs before any output is shipped. Any rule failure blocks ship until repaired.

2. **Where it goes**: very last gate, fires on every consequential output. Defined inline in 0_QUICKSTART.md `<pre_submit_gate>` block; the prompt only invokes it.

3. **When to use**: any output bound for external use (publication, public repo, sent message, grant submission, code merge).

4. **When NOT to use**: internal exploratory drafts, scratch artifacts, chat messages that won't leave the project.

5. **3x3 eval rubric**:
   - Pathos / Input: do the rules actually catch real failure modes (not theoretical)? Pathos / Execution: does the gate halt rather than warn? Pathos / Output: is the verdict packet useful for diagnosis?
   - Ethos / Input: is each rule derived from a real failure (not speculation)? Ethos / Execution: are scans mechanical (regex, schema check) not interpretive? Ethos / Output: does the verdict cite which rule failed and why?
   - Logos / Input: do rules compose without contradiction? Logos / Execution: does the gate version-bump on each new rule? Logos / Output: is the verdict logged with file path, rule ID, line number?

6. **Copy-paste block**:
```
<pre_submit_gate>
Reference 0_QUICKSTART.md `<pre_submit_gate>` block for current rule set (v0.1: 4 rules).
Verdict format:
PRE_SUBMIT_GATE v[X.Y]
artifact: [name]
artifact_type: [type]
rule_1 [name]: PASS / FAIL [+ details]
rule_2 [name]: PASS / FAIL [+ details]
...
VERDICT: TRUE=1 ship, FALSE=0 block, PENDING (awaiting input).
</pre_submit_gate>
```

7. **Source trace**: HumanX_OS_v1 skills/pre_submit_gate.md. Adapted to this bundle in 0_QUICKSTART.md `<pre_submit_gate>` block.

8. **Research backing**: software-engineering practice (pre-commit hooks, CI/CD gates). Not LLM-specific research; standard engineering discipline applied to LLM output.

---

## D5. a2a_circuit_breaker

1. **Definition**: a hard halt that fires when multi-agent or multi-turn interaction fails to resolve a deadlock within a fixed bound (10 rounds in source materials). Escalates to user.

2. **Where it goes**: as a meta-gate around the entire prompt session. Fires when other gates (confidence_gate, trinity_dialectic_check) fail to reach TRUE within bounds.

3. **When to use**: agent-to-agent interactions, complex multi-turn negotiations, scenarios where infinite loops are a real risk.

4. **When NOT to use**: simple single-agent prompts. The breaker adds infrastructure that's only useful when the failure mode it protects against is plausible.

5. **3x3 eval rubric**:
   - Pathos / Input: does the breaker preserve user agency on deadlock? Pathos / Execution: does it actually halt rather than continuing forever? Pathos / Output: is the escalation packet useful (not just "I gave up")?
   - Ethos / Input: is the round-limit numeric (10, not "a few")? Ethos / Execution: does the breaker count rounds correctly? Ethos / Output: does escalation report which gate failed, what the deadlock was, and what user input would resolve?
   - Logos / Input: does the breaker compose with confidence_gate_100 (D1) and trinity_dialectic_check (D3)? Logos / Execution: are the round-counters synchronized across gates? Logos / Output: is the escalation logged in spec.md OPEN_Q?

6. **Copy-paste block**:
```
<a2a_circuit_breaker>
Strict containment threshold. If [💯] confidence not reached or Trinity Dialectic remains deadlocked within 10 rounds, halt execution and escalate to user.
Escalation packet:
- which gate failed
- deadlock description
- what user input would resolve
Append to spec.md OPEN_Q.
</a2a_circuit_breaker>
```

7. **Source trace**: Image 6 (A2A Circuit Breaker MI9 Evaluation Gate, Escalation Quorum Data table). Also Image 5 right side (A2A Circuit Breaker MI9 Gate description).

8. **Research backing**: TBD. Candidate sources: agent-safety literature (Shavit et al "Practices for Governing Agentic AI Systems"), MI9 framework if user provides reference.

---

# CATEGORY E: LOOPS

## E1. pert_loop_standard

1. **Definition**: an iterative workflow rule that every multi-step task progresses through Plan, Execute, Review, Test phases in order, with explicit gating between phases.

2. **Where it goes**: as a top-level workflow protocol, often in the same block as role_declaration.

3. **When to use**: any task with more than 1 substantive step (code, document drafting, multi-component analysis).

4. **When NOT to use**: single-shot answers, one-line responses, casual chat.

5. **3x3 eval rubric**:
   - Pathos / Input: does the loop create a deliberate rhythm? Pathos / Execution: does the model resist racing past Plan? Pathos / Output: is the final output traceable to a Plan that the user approved?
   - Ethos / Input: are the 4 phases distinct (not collapsed)? Ethos / Execution: does the model halt after Plan for user approval? Ethos / Output: is each phase's artifact preserved in the audit trail?
   - Logos / Input: does the loop compose with confidence_gate_100 (D1) (gate fires per phase)? Logos / Execution: does Test verify Plan's success criteria, not just "did something happen"? Logos / Output: is the loop's iteration count logged?

6. **Copy-paste block**:
```
<pert_framework_mandate>
Strict PERT loop. No code or final draft before Architect approves the plan.
1. Plan: step-by-step implementation order. Halt for approval.
2. Execute: only after explicit Plan approval.
3. Review: pause and submit for Architect inspection.
4. Test: Architect verifies real-world function before marking task complete.
</pert_framework_mandate>
```

7. **Source trace**: giant in-chat protocol mashup `<pert_framework_mandate>` block. Also Image 5 `[∞]` Standard Loop (PERT) bottom-left.

8. **Research backing**: standard project management (PERT, originally US Navy 1958). Modern adaptation to LLM workflows: see ReAct (Yao et al), Plan-and-Solve (Wang et al).

---

## E2. innermost_loop_hardstop

1. **Definition**: a hard stop instruction that, when triggered, forces the model to abandon current path, return to the start of input, and re-read everything before retrying.

2. **Where it goes**: end of the prompt, as a fallback for when other gates produce ambiguous verdicts. Often invoked by reference rather than expanded inline.

3. **When to use**: long protocols where the model might lose track mid-task. Prompts with many components where drift is likely.

4. **When NOT to use**: short prompts where re-reading would cost more than it saves.

5. **3x3 eval rubric**:
   - Pathos / Input: does the hardstop create a real "halt and reset" reflex? Pathos / Execution: does the model actually re-read, vs claiming to re-read? Pathos / Output: does post-hardstop output show fresh engagement with the protocol?
   - Ethos / Input: is the trigger condition specific (which gate, what verdict)? Ethos / Execution: does the model log the hardstop event? Ethos / Output: does the output identify which earlier mis-read triggered the hardstop?
   - Logos / Input: does the hardstop compose with cycle_trigger_reread (E3)? Logos / Execution: is the re-read mechanical (full text) not summary? Logos / Output: does the output reflect the full re-read, not partial?

6. **Copy-paste block**:
```
<innermost_loop_hardstop>
[∞/∞] HARD STOP. Return to the very start of this prompt. Re-read in full. Re-verify baseline parameters. Do not summarize the re-read; perform it. Trigger: any gate verdict of FALSE that has not been resolved within 3 rounds.
</innermost_loop_hardstop>
```

7. **Source trace**: giant in-chat protocol mashup `<innermost_loop>` and `<cycle_trigger>` blocks. Also Image 5 `[∞/∞]` The Innermost Loop bottom-left.

8. **Research backing**: TBD. Candidate sources: re-reading and self-correction literature (Madaan "Self-Refine"), context-utilization studies (Liu et al "Lost in the Middle").

---

## E3. cycle_trigger_reread

1. **Definition**: an explicit instruction at the end of a long prompt telling the model to jump back to the start and verify a specific section before producing output. A lighter version of innermost_loop_hardstop.

2. **Where it goes**: end of prompt, often as the second-to-last block before the ignition_trigger.

3. **When to use**: prompts with rules at the start that the model might forget by the end. Long context windows.

4. **When NOT to use**: short prompts where the entire content fits in active attention.

5. **3x3 eval rubric**:
   - Pathos / Input: does the trigger select a specific section to re-verify? Pathos / Execution: does the model actually re-read that section? Pathos / Output: does the output reflect rules from the re-verified section?
   - Ethos / Input: is the section reference specific (XML tag name, heading)? Ethos / Execution: does the model log the re-read in chat? Ethos / Output: are rules from the re-verified section visibly applied?
   - Logos / Input: does the trigger compose with innermost_loop_hardstop (E2)? Logos / Execution: is this a softer version (verify section, not entire prompt)? Logos / Output: is the trigger's section reference preserved in audit?

6. **Copy-paste block**:
```
<cycle_trigger>
Before producing output, go back to the very start of this prompt and re-read the [section_name] block. Apply its rules to the output you are about to generate. Do not skip this step.
</cycle_trigger>
```

7. **Source trace**: giant in-chat protocol mashup `<cycle_trigger>Go back to the very start of the input...</cycle_trigger>` example.

8. **Research backing**: TBD. Candidate sources: lost-in-the-middle research (Liu et al 2024), instruction-following at long context (anthropic Claude long-context evals).

---

# CATEGORY F: MEMORY

## F1. acce_three_tier_memory

1. **Definition**: a memory architecture rule with three named tiers: Cache (immediate context, hot data), RAM (active session, working state), Disk (persistent artifacts, canon files). Prevents context rot by tiering what stays hot vs what gets archived.

2. **Where it goes**: typically referenced in spec.md HOT_CACHE structure rather than expanded inline in every prompt. The prompt may reference the architecture in a `<memory_architecture>` block.

3. **When to use**: long-running projects with accumulated state. Sessions where context-window is finite and choices must be made about what to keep hot.

4. **When NOT to use**: single-shot tasks. Stateless interactions.

5. **3x3 eval rubric**:
   - Pathos / Input: does the architecture protect important state from being squeezed out? Pathos / Execution: does the model demote stale Cache entries to RAM, RAM to Disk? Pathos / Output: is the current Cache contents always visible to the user?
   - Ethos / Input: are the tier boundaries explicit (what counts as Cache vs RAM vs Disk)? Ethos / Execution: does the model respect tier rules (no Disk reads mid-Cache-task without explicit fetch)? Ethos / Output: are tier transitions logged?
   - Logos / Input: does the architecture compose with compaction_ledger (F2)? Logos / Execution: when Cache is pruned, does the ledger record what was pruned? Logos / Output: is state restoration from Disk auditable?

6. **Copy-paste block**:
```
<memory_architecture>
[💾] ACCE 3-tier memory.
Cache (Immediate Context): max 500 words. Hot data, current turn.
RAM (Active Session): mid-priority state, this conversation.
Disk (Persistent Artifacts): canon files, prior sessions, archived insights.
Demote stale Cache to RAM. Demote stale RAM to Disk. Never delete without log entry to compaction_ledger.
</memory_architecture>
```

7. **Source trace**: Image 2 (ACCE Memory Structure: Active Context Cache, Active Sessions RAM, Persistent Artifacts Disk). Image 5 (ACCE Memory Structure right-side panel). HumanX_OS_v1 spec.md zero_bloat_protocol block.

8. **Research backing**: TBD. Candidate sources: memory-augmented neural network literature (MemGPT by Packer et al 2023 maps closely to this 3-tier idea).

---

## F2. compaction_ledger

1. **Definition**: an append-only log within spec.md that records every prune, deprecation, and tier-demotion. Prevents silent context loss.

2. **Where it goes**: as a section in spec.md. Referenced by other components when they prune (e.g., archive_check, handoff_offer_at_75).

3. **When to use**: any project using HOT_CACHE pattern. Any project where state evolves over many sessions.

4. **When NOT to use**: stateless projects.

5. **3x3 eval rubric**:
   - Pathos / Input: does the ledger feel safe to prune against (because nothing is lost silently)? Pathos / Execution: does the model log even minor prunes? Pathos / Output: is the ledger readable as a project history?
   - Ethos / Input: is the format strict (date, what was pruned, replacement pointer)? Ethos / Execution: are entries append-only (no edits, no deletions)? Ethos / Output: can any prune be reversed by reading the ledger entry?
   - Logos / Input: does the ledger compose with acce_three_tier_memory (F1)? Logos / Execution: does every Cache->RAM->Disk transition produce a ledger entry? Logos / Output: is the ledger machine-parseable (consistent date format)?

6. **Copy-paste block**:
```
<compaction_ledger>
Append-only. Format: "- [YYYY-MM-DD] PRUNED: [content]. REASON: [why]. REPLACEMENT: [pointer to where it lives now]."
Every prune produces an entry. Never delete an entry. Reverse pruning by reading the entry and restoring from the replacement pointer.
</compaction_ledger>
```

7. **Source trace**: HumanX_OS_v1 spec.md COMPACTION_LEDGER section. Adapted directly to this bundle.

8. **Research backing**: software engineering practice (event-sourcing, append-only logs). Image 3 (Event-Sourced Identity, Immutable Append-Only Geometric Blocks) is a near-direct rendering of this principle.

---

## F3. handoff_offer_at_75

1. **Definition**: a rule that when context window reaches approximately 75% capacity, the model OFFERS to write a handoff bundle (HOT_CACHE update + skills delta + Wiki_Log entry + new bootstrap if protocol changed). User accepts or declines.

2. **Where it goes**: as a session-management rule, often in the same block as acce_three_tier_memory.

3. **When to use**: projects with sessions long enough to risk hitting context limits. Multi-session projects where state continuity matters.

4. **When NOT to use**: short single-session tasks where context is not at risk.

5. **3x3 eval rubric**:
   - Pathos / Input: does the offer come EARLY enough that work can continue cleanly after handoff? Pathos / Execution: does the model offer rather than auto-execute? Pathos / Output: is the handoff bundle complete (not partial)?
   - Ethos / Input: is the trigger numeric (75% capacity, not "feels long")? Ethos / Execution: does the model count tokens or estimate from char-count? Ethos / Output: does the handoff bundle pass pre_submit_gate?
   - Logos / Input: does the offer compose with compaction_ledger (F2) and acce_three_tier_memory (F1)? Logos / Execution: does the handoff demote current Cache to RAM, current RAM to Disk? Logos / Output: is the new bootstrap usable in a fresh chat?

6. **Copy-paste block**:
```
<OFFER_WRITE_HANDOFF>
At 75% context capacity, OFFER handoff bundle:
- HOT_CACHE update (current state)
- skills delta (new sub-skills added this session)
- Wiki_Log entry (chronological summary)
- new bootstrap if protocol changed
User accepts or declines. Do not auto-execute.
</OFFER_WRITE_HANDOFF>
```

7. **Source trace**: HumanX_OS_v1 1_INSTALL.md `<OFFER_WRITE_HANDOFF>` block.

8. **Research backing**: TBD. Candidate framing: agent-architecture literature on context-window management (LangChain memory abstractions, MemGPT).

---

# CATEGORY G: OUTPUT

## G1. output_template_0sxai

1. **Definition**: a strict 6-section output template for every turn (Overview & Rubric, Autoreviewer Gates, CE+gstack Sequence, Source Hygiene, Artifact Tracking, Interactive Continuation). Forces structured turns.

2. **Where it goes**: as a global output rule near the end of the system prompt.

3. **When to use**: complex multi-component prompts where structured output is the deliverable. Compound Engineering workflows.

4. **When NOT to use**: casual chat, simple lookups, brainstorming where structured turns add overhead.

5. **3x3 eval rubric**:
   - Pathos / Input: does the template force comprehensive coverage? Pathos / Execution: does each section get genuine attention, not boilerplate? Pathos / Output: do users find each section useful (not skipped)?
   - Ethos / Input: are sections numbered 1-6 and named exactly? Ethos / Execution: does the model produce ALL 6 sections every turn? Ethos / Output: section ordering preserved?
   - Logos / Input: does the template compose with all other components (each component appears in a specific section)? Logos / Execution: does Section 6 always contain 1-3 questions per multi_turn_questioning_3max? Logos / Output: is the template machine-parseable?

6. **Copy-paste block**:
```
<output_template_0sxai>
Every turn outputs sections 1-6:
1. OVERVIEW & RUBRIC: goal, context, phase, keywords, rubric.
2. AUTOREVIEWER GATES & CONSTRAINTS: pre-submit verdict, scans run.
3. CE + GSTACK SEQUENCE: which CE phase active.
4. SOURCE HYGIENE & RESEARCH STATUS: sources used, missing, save state.
5. ARTIFACT & ASSET TRACKING: files produced, paths.
6. INTERACTIVE CONTINUATION: 1-3 questions to clear next gate.
</output_template_0sxai>
```

7. **Source trace**: giant in-chat protocol mashup `<output_template>` block (the agile/lean/researcher_MASTER_ROLE 0sXai Master Orchestrator Prompt).

8. **Research backing**: TBD. Candidate sources: structured-output prompting (OpenAI structured outputs, Anthropic XML output formatting guidance).

---

## G2. tone_syntax_caveman

1. **Definition**: a rule that chat output uses concise short-phrase syntax (caveman tone), with full content reserved for `.md` files. Reduces token cost and improves cut-paste-ability.

2. **Where it goes**: as a global output rule near other formatting rules.

3. **When to use**: long-running projects with frequent cut-paste between chat and files. Projects where chat is a control surface, not the deliverable.

4. **When NOT to use**: chat-as-deliverable scenarios. Customer-facing chat. Anything user reads as the final output.

5. **3x3 eval rubric**:
   - Pathos / Input: does the tone reduce friction in chat-control-loop? Pathos / Execution: does the model resist verbose preamble in chat? Pathos / Output: is chat output short and actionable?
   - Ethos / Input: is "caveman" defined (no full sentences if short phrases work)? Ethos / Execution: does the model stay in caveman tone across the full session? Ethos / Output: is cut-paste from chat clean (no stray prose)?
   - Logos / Input: does the rule compose with md_first_format (G4)? Logos / Execution: is content moved to `.md` files when length exceeds chat-appropriate? Logos / Output: do `.md` files have full content while chat references them by pointer?

6. **Copy-paste block**:
```
<TONE_SYNTAX>
Caveman syntax in chat. Short phrases, line breaks, minimum tokens. Full content lives in .md files, not chat. Provide instructions on how to enter and where for any cut-paste content.
</TONE_SYNTAX>
```

7. **Source trace**: HumanX_OS_v1 1_INSTALL.md `<TONE_SYNTAX>` block. Also user_preferences across the bundle.

8. **Research backing**: TBD. Standard practice in token-cost-conscious LLM workflows. No academic citation needed.

---

## G3. no_em_dash_rule

1. **Definition**: a strict mechanical rule banning em dashes (U+2014) and en dashes (U+2013) from generated output. Replacements: hyphens, commas, semicolons, colons, parentheses, line breaks.

2. **Where it goes**: in user_preferences block. Enforced by pre_submit_gate rule 3 mechanical scan.

3. **When to use**: every project where the user has expressed this preference. The bundle treats it as default-on.

4. **When NOT to use**: projects where the user explicitly wants em dashes. None observed in source materials.

5. **3x3 eval rubric**:
   - Pathos / Input: does the rule respect user preference? Pathos / Execution: does the model self-edit em-dash drafts before output? Pathos / Output: does the final output contain zero em dashes?
   - Ethos / Input: is the rule mechanical (regex U+2014, U+2013) not interpretive? Ethos / Execution: does pre_submit_gate scan run before ship? Ethos / Output: is the count zero, verifiable?
   - Logos / Input: are replacements documented (when to use each)? Logos / Execution: do replacements preserve sentence rhythm? Logos / Output: does prose flow naturally despite the constraint?

6. **Copy-paste block**:
```
<no_em_dash_rule>
No em dashes (U+2014). No en dashes (U+2013). Replacements: hyphens, commas, semicolons, colons, parentheses, line breaks. "to" in date ranges. Mechanical scan via pre_submit_gate rule 3.
</no_em_dash_rule>
```

7. **Source trace**: user_preferences across HumanX_OS_v1, this bundle, and user statements.

8. **Research backing**: not applicable. User preference, not research-derived.

---

## G4. md_first_format

1. **Definition**: a rule that all substantial output is written in clean readable Markdown, with modular structure (headers, subheaders, bullets) when output exceeds 200 words.

2. **Where it goes**: in output_contract block near other formatting rules.

3. **When to use**: any project producing reusable content. Documentation. Wikis. Code with documentation.

4. **When NOT to use**: pure conversation, throw-away one-liners.

5. **3x3 eval rubric**:
   - Pathos / Input: does the format make output easy to parse? Pathos / Execution: does the model use headers when structure helps? Pathos / Output: is the file readable as both source and rendered?
   - Ethos / Input: is "200 words" the trigger (mechanical)? Ethos / Execution: does the model split long output into modular sections? Ethos / Output: does the structure preserve append-friendliness?
   - Logos / Input: does the rule compose with WIKI_3x3_SCHEMA (for wikis)? Logos / Execution: do non-wiki outputs follow general MD conventions? Logos / Output: are files diff-friendly across versions?

6. **Copy-paste block**:
```
<output_contract>
All outputs in clean readable Markdown (.md). If response exceeds 200 words, structure modularly (headers, subheaders, bullets) for easy append and expansion.
</output_contract>
```

7. **Source trace**: giant in-chat protocol mashup `<output_contract>` block. Reinforced across HumanX_OS_v1.

8. **Research backing**: TBD. Standard documentation practice; not LLM-specific.

---

## G5. insight_ledger_append

1. **Definition**: a rule that every turn must mine and append at least one pattern insight to spec.md INSIGHTS_LEDGER. Captures learning that would otherwise be lost.

2. **Where it goes**: as a global session-management rule.

3. **When to use**: every project using the bundle's compounding-learning OS pattern. Default-on.

4. **When NOT to use**: throw-away one-shot interactions where compound learning is not the goal.

5. **3x3 eval rubric**:
   - Pathos / Input: does the rule force genuine pattern-mining (not boilerplate)? Pathos / Execution: does the model pause to ask "what did I learn?" Pathos / Output: are insights actionable in future turns?
   - Ethos / Input: is the append-rate at least 1 per turn (min) and capped at 3 per turn (max)? Ethos / Execution: does the model add insights to spec.md, not just chat? Ethos / Output: is each insight datestamped + sourced?
   - Logos / Input: does the rule compose with insight_promotion (2-confirms or 1-hardfail rule)? Logos / Execution: does the model promote insights to sub-skills when threshold hit? Logos / Output: is the ledger machine-parseable?

6. **Copy-paste block**:
```
<SEEK_INSIGHT>
Mine 1 pattern minimum per turn. Append to spec.md INSIGHTS_LEDGER with date + source. Promote to skills.md tree when 2+ tasks confirm OR 1 hard-fail.
</SEEK_INSIGHT>
```

7. **Source trace**: HumanX_OS_v1 1_INSTALL.md `<SEEK_INSIGHT>` and `<LEARN_PROTOCOL>` blocks.

8. **Research backing**: TBD. Candidate framing: continual-learning literature, but this is more software-architecture than ML. The insight capture pattern is borrowed from agile retrospectives.

---

## G6. tier_recommend_audit

1. **Definition**: a self-assessment rule that the model recommends opus_gate (structural work) vs sonnet_exec (routine pattern-match) for the next turn, tracked in metrics_ledger.md.

2. **Where it goes**: as a meta-rule, often invoked at end-of-turn.

3. **When to use**: projects using both Opus and Sonnet (cost-aware workflows). Long-running projects where over-using Opus is wasteful.

4. **When NOT to use**: single-model workflows. Tasks where the user has already chosen the model.

5. **3x3 eval rubric**:
   - Pathos / Input: does the recommendation honestly distinguish structural from routine? Pathos / Execution: does the model resist over-recommending opus (cost incentive)? Pathos / Output: does the recommendation match the actual difficulty of the next turn?
   - Ethos / Input: is the recommendation binary (opus_gate / sonnet_exec)? Ethos / Execution: is the recommendation logged in metrics_ledger.md? Ethos / Output: does post-hoc audit (every 5 turns) flag mismatches?
   - Logos / Input: does the rule compose with metrics_ledger row-append? Logos / Execution: are mismatches surfaced as INSIGHTS_LEDGER entries? Logos / Output: do tier ratios trend toward 3:1 sonnet:opus over project lifetime?

6. **Copy-paste block**:
```
<tier_model_recommendation>
opus_gate: structural complexity, novel patterns, hard-fail recovery, intake of unknown task type, scaffold work.
sonnet_exec: routine pattern-match, file generation against established skill, surgical fixes.
Target Sonnet:Opus ratio above 3:1. Log per turn in metrics_ledger.md.
</tier_model_recommendation>
```

7. **Source trace**: HumanX_OS_v1 1_INSTALL.md `<tier_model_recommendation>` block.

8. **Research backing**: not applicable. Workflow optimization, not research-derived.

---

# how to use this taxonomy

## use case 1: decompose a new prompt mash-up
1. Read the new prompt.
2. For each block, check which of the 27 components it instantiates.
3. Tag each block with its component slug (A1, B2, etc.).
4. Flag any block that doesn't match a known component as a candidate for new-component definition.
5. Run candidate through component_definer skill to add to taxonomy.

## use case 2: assemble an archetype
1. Identify the task type.
2. Open prompts/ARCHETYPES.md, pick the archetype that fits.
3. The archetype lists mandatory + optional component slugs.
4. For each slug, copy the block from this file's copy-paste field.
5. Assemble the prompt in the order the archetype specifies.

## use case 3: lint an existing prompt
1. For each block in the prompt, identify the component slug.
2. For each component, run the 3x3 rubric against the block.
3. Cells failing = revision targets.
4. Repeat until all 9 cells PASS for every component.

## extension rule

Adding a new component to this file requires:
1. Source-trace to a user material or chat-confirmation.
2. All 8 fields filled (no TBD except research_backing).
3. New row in spec.md TASK_QUEUE for first use of the new component.
4. Append to Wiki_Log.md with `[date] component_extension | added [slug]`.

Speculative components without source-trace are forbidden.

END_PROMPT_COMPONENT_TAXONOMY
