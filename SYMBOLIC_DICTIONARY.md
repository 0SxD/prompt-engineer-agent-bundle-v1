# canon/SYMBOLIC_DICTIONARY.md
# Status: live, v0.1
# Bundle: Prompt_Toolkit_v0_1
# Source-trace: synthesized from src_md_1 (Symbolic_Symbolic_Arch_Dialectic_Overview_2026_04_15.md), Image 1 (Trinity Protocol), Image 2 (OsXai Symbolic Reasoning), Image 5 (High-Confidence Dialectic), Image 6 (A2A Circuit Breaker)
# Type: read-only canon. Symbol fidelity is mechanical. Do not paraphrase symbols.

## purpose

This file is the single source of truth for the visual programming language used across this bundle. The exact bracketed format is preserved everywhere. When you write `[Λ Logos]` you do not write "the logos node" or "the analytical engine" or any other paraphrase; the symbol IS the reference. The symbols compress protocol into geometric anchors that are simultaneously executable text and renderable visual artifacts.

This dictionary is invoked by pre_submit_gate rule 4 (symbol fidelity scan).

## the 3 sections (Pathos / Ethos / Logos)

This file follows the WIKI_3x3_SCHEMA. 3 sections, each with 3 sub-parts (Input / Execution / Output). 9 cells total.

---

## SECTION 1: [Π Pathos] | the creative case for the symbols

### 1.1 Input (what creative purpose the symbols serve)

The symbols exist because plain text protocol gets diluted across a long context window. A 3000-word protocol blob is read linearly and weighted equally with everything else in context. A bracketed symbol like `[💯]` cuts through linear reading because it is visually distinct, semantically dense, and consistently re-encountered every time the protocol fires. The symbol becomes an attention anchor.

The dual-purpose property: the same text that the LLM reads as protocol can be pasted into an image-generation model and rendered as a diagram. The visual artifact reinforces the textual protocol, and vice versa. Source: src_md_1 section "The Geometric Metaphor and the Ancient Language Bridge."

### 1.2 Execution (how the creative purpose is realized in practice)

Pathos in this layer is the choice of WHICH symbols to include in any given prompt. Including all 10 symbols in a 200-word prompt is bloat. Including zero symbols in a 5000-word protocol is dilution. The creative call is which subset to anchor.

Default subset for short prompts (under 500 words): `[0️⃣]` `[💯]` `[❓x3]`. Three anchors: zero-assumption, confidence gate, multi-turn questioning. Most prompt-engineering tasks need only these.

Default subset for long protocols (over 1000 words): all 10. The bloat penalty is small relative to the protocol length, and the visual anchors prevent context dilution.

### 1.3 Output (the artifact this Pathos layer produces)

A symbol-anchored prompt is itself an output. It is shorter than the prose equivalent. It is renderable as a visual. It survives copy-paste across chats, projects, models without losing the protocol structure.

---

## SECTION 2: [Θ Ethos] | the verification rules

### 2.1 Input (rules for what counts as a valid symbol)

The 10 canonical symbols. Source-trace for each given. Any other bracketed Greek-letter combo is NOT canonical and must be flagged.

| symbol | name | exact bracketed format | source |
|---|---|---|---|
| [Λ Logos] | The Analytical Engine | `[Λ Logos]` | src_md_1, Image 1, Image 2, Image 5 |
| [Π Pathos] | The Creative DMN | `[Π Pathos]` | src_md_1, Image 1, Image 2, Image 5 |
| [Θ Ethos] | The Golden Mean | `[Θ Ethos]` | src_md_1, Image 1, Image 2, Image 5 |
| [0️⃣] | Zero-Assumption Root | `[0️⃣]` | src_md_1, Image 2, Image 5 |
| [💯] | 100% Confidence Gate | `[💯]` | src_md_1, Image 2, Image 5 |
| [❓x3] | Three Questions Interrogation | `[❓x3]` | src_md_1, Image 2, Image 5 |
| [∞] | Standard Loop (PERT) | `[∞]` | src_md_1, Image 5 |
| [∞/∞] | Innermost Loop (hard stop) | `[∞/∞]` | src_md_1, Image 5, Image 6 |
| [⏳] | Timelessness Axiom | `[⏳]` | src_md_1, Image 5 |
| [💾] | ACCE Memory Structure | `[💾]` | src_md_1, Image 5 |

### 2.2 Execution (how the verification runs)

Pre_submit_gate rule 4 is a mechanical regex scan. For each canonical symbol, the scan confirms the exact format appears unmodified wherever the symbol is referenced. Variations like `(Λ)` or `[Lambda]` or `[Λ]` (without the trailing word) are flagged as drift.

Exception: when a symbol is being defined (such as in this dictionary), it can appear in a definition context. When a symbol is being invoked (such as in a prompt), the full bracketed form with the trailing word is required for the three Trinity nodes (Logos, Pathos, Ethos) and the bare bracketed form for the others.

### 2.3 Output (verdict format)

```
SYMBOL_FIDELITY_SCAN
file: [path]
total_symbol_references: [N]
canonical_matches: [N]
drift_hits: [list with line numbers]
verdict: PASS / FAIL
```

PASS clears pre_submit_gate rule 4. FAIL blocks ship until repaired.

---

## SECTION 3: [Λ Logos] | the logical structure of the dictionary

### 3.1 Input (the formal structure)

The 10 symbols partition into 4 functional categories. Every symbol in canonical use belongs to exactly one category.

| category | symbols | function |
|---|---|---|
| dialectic | [Λ Logos], [Π Pathos], [Θ Ethos] | three voices of any decision |
| gates | [0️⃣], [💯], [❓x3] | mandatory checkpoints before action |
| loops | [∞], [∞/∞] | iteration controls (standard + hard-stop) |
| state | [⏳], [💾] | time and memory invariants |

### 3.2 Execution (how the logical structure is enforced)

Component definitions in canon/PROMPT_COMPONENT_TAXONOMY.md cite which category their associated symbol belongs to. Cross-category symbol confusion (e.g., calling `[💯]` a loop) is flagged in component-definer review.

The three Trinity symbols always appear together when the dialectic is being invoked. A prompt that invokes only `[Λ Logos]` and `[Θ Ethos]` without `[Π Pathos]` is flagged: the dialectic is incomplete and the prompt likely missing the creative-proposal mechanism.

### 3.3 Output (the audit trail)

When Claude generates a prompt or wiki, it appends a symbol manifest at the end of the file:

```
SYMBOL_MANIFEST
file: [path]
dialectic: [Λ Logos] (N uses), [Π Pathos] (N uses), [Θ Ethos] (N uses)
gates: [0️⃣] (N), [💯] (N), [❓x3] (N)
loops: [∞] (N), [∞/∞] (N)
state: [⏳] (N), [💾] (N)
unmatched_brackets: [list or 'none']
```

The manifest doubles as a symbol-density metric. Files with very low symbol density may be missing protocol anchors. Files with very high symbol density may be using symbols decoratively rather than functionally.

---

## color codes (for visual rendering, when applicable)

The visual layer maps symbols to a 5-color palette per src_md_1. Used when generating infographics from prompt text.

| color | hex | function | symbols |
|---|---|---|---|
| black | #000000 | background, void, zero context | (background) |
| white | #FFFFFF | borders, base text, verified state | [💯] |
| blue | #0066CC | logic paths, AST connections | [Λ Logos] |
| red | #CC0000 | unverified, stop, creative proposal | [Π Pathos], [∞/∞] |
| green | #00AA44 | approved, verification, memory | [Θ Ethos], [💾] |

The Zero-Assumption root `[0️⃣]` and the Three-Questions trigger `[❓x3]` and the Timelessness axiom `[⏳]` are unassigned color in v0.1; they appear in white-on-black by default. Color assignment for these is a v0.2 decision.

---

## extension rule

Adding a new symbol requires:
1. Source-trace to a user upload or chat-confirmation.
2. Category assignment (dialectic, gate, loop, state, or new category with rationale).
3. Color assignment (optional, can be deferred).
4. Definition in this file, following the table format.
5. A row in the symbol-manifest output template (Section 3.3).
6. Update to pre_submit_gate rule 4 to include the new canonical format.
7. Append to Wiki_Log.md with `[date] symbol_extension | added [name]`.

Speculative symbols without source-trace are forbidden.

END_SYMBOLIC_DICTIONARY
