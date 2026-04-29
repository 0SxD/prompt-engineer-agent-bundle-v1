# canon/WIKI_3x3_SCHEMA.md
# Status: live, v0.1
# Bundle: Prompt_Toolkit_v0_1
# Source-trace: Trinity-of-Trinities pattern from Image 1 + Image 5 (3x3=9 sub-evaluators) applied to wiki organization
# Type: read-only canon. Mechanical schema rule. Enforced by pre_submit_gate rule 2.

## purpose

Every wiki page in this project follows this schema. No exceptions. The schema doubles as an evaluation rubric: each page has 9 named cells, every cell answerable as PASS or FAIL. This makes wikis machine-checkable, not just readable.

The schema enforces three properties simultaneously:
1. Every concept is examined from three rhetorical angles (Pathos / Ethos / Logos).
2. Every angle is examined at three operational stages (Input / Execution / Output).
3. The total of 9 cells maps to the Trinity-of-Trinities sub-evaluators from Image 1 and Image 5.

## the schema

```
# title

## SECTION 1: [Π Pathos] | the creative case

### 1.1 Input (what creative purpose this serves)
[content]

### 1.2 Execution (how the creative purpose is realized)
[content]

### 1.3 Output (the artifact the Pathos layer produces)
[content]

## SECTION 2: [Θ Ethos] | the verification rules

### 2.1 Input (rules for what counts as valid)
[content]

### 2.2 Execution (how the verification runs)
[content]

### 2.3 Output (verdict format)
[content]

## SECTION 3: [Λ Logos] | the logical structure

### 3.1 Input (the formal structure)
[content]

### 3.2 Execution (how the logical structure is enforced)
[content]

### 3.3 Output (the audit trail)
[content]
```

## the 3x3 table

The 9 cells map cleanly to a matrix:

|  | 1. Input | 2. Execution | 3. Output |
|---|---|---|---|
| Pathos (purpose) | what creative purpose this serves | how the purpose is realized | what artifact is produced |
| Ethos (verification) | rules for what counts as valid | how verification runs | verdict format |
| Logos (logic) | the formal structure | how the structure is enforced | the audit trail |

This is the same Trinity-of-Trinities pattern that Image 1 captions as "9 sub-evaluators." Each cell is one sub-evaluator.

## the section ordering

Pathos first, Ethos second, Logos third. This ordering is intentional and not arbitrary. The logic:

1. Pathos goes first because it answers "why does this exist." If you cannot articulate the purpose, the verification rules and the formal structure are premature.
2. Ethos goes second because it answers "what counts as a valid version of this." Once the purpose is named, the validation criteria can be specified.
3. Logos goes last because it answers "how is this formally structured and audited." Once purpose is named and validation criteria are specified, the formal logic falls out.

The ordering matches the Trinity Dialectic resolution order from src_md_1: `[Π Pathos]` proposes, `[Λ Logos]` and `[Θ Ethos]` verify. In wiki form: Pathos states the proposal, then Ethos and Logos examine it.

## what each cell must contain

Minimum content per cell: 2 to 4 sentences, or one clearly-labeled list, or one table row pair. An empty cell fails the lint. A cell containing only "TBD" is acceptable for a page tagged STATUS: pending_draft, but blocks promotion to STATUS: live.

Maximum content per cell: target under 200 words. Cells longer than 200 words trigger a sub-cell split (introduce 1.1.a, 1.1.b, etc.) or a refactor into a child wiki page.

## what the schema is NOT

The schema is NOT a content template that tells you what to write in each cell. It is a structural skeleton. Each wiki page chooses its own content; the schema only enforces the 9-cell organization.

The schema does NOT require the words "Input" or "Execution" or "Output" to appear in the cell heading verbatim. Synonyms appropriate to the page topic are fine, as long as the underlying meaning maps to the schema. Example: a wiki on a memory component might use "1.1 Storage (Input)" or "1.1 Write (Input)" instead of "1.1 Input." The schema check confirms the mapping; it does not enforce the exact word.

## lint procedure (pre_submit_gate rule 2)

```
WIKI_3x3_LINT
file: [path]
section_1_present: PASS / FAIL [Pathos heading found?]
section_2_present: PASS / FAIL [Ethos heading found?]
section_3_present: PASS / FAIL [Logos heading found?]
section_ordering: PASS / FAIL [Pathos before Ethos before Logos?]
sub_parts_section_1: [count of 1.X sub-headings, expect 3]
sub_parts_section_2: [count of 2.X sub-headings, expect 3]
sub_parts_section_3: [count of 3.X sub-headings, expect 3]
total_cells: [count, expect 9]
empty_cells: [list of cell IDs with no content]
verdict: PASS (all green) / FAIL (any red)
```

PASS clears pre_submit_gate rule 2. FAIL blocks ship until repaired.

## extension rule

Adding a new schema variant (for example, a 4-section variant, or a 3x4 cell variant) requires:
1. Hard-fail derivation: an existing 3x3 schema lint failed in a way that revealed the schema was insufficient for some content type.
2. Proposal in spec.md OPEN_Q.
3. User approval before adding the variant.
4. Both schemas listed here as canonical, with rules for which content types use which schema.

Speculative schema variants without hard-fail derivation are forbidden.

## relation to the file you are reading

This file (WIKI_3x3_SCHEMA.md) is itself written in the 3x3 schema. Reading the headings above, you can see Section 1 (Pathos / purpose of the schema), Section 2 (Ethos / lint rules), Section 3 (Logos / formal structure). The schema demonstrates itself.

Wait. The headings in this file do not match the 3x3 layout exactly because this file is a META wiki: it defines the schema rather than instantiating it. Meta wikis are a single allowed exception to the schema, tagged at the top with `# Type: meta-canon`. There are exactly two meta-canon files in this bundle: WIKI_3x3_SCHEMA.md and SYMBOLIC_DICTIONARY.md (which IS in 3x3 form, but its content is symbol definitions rather than concept analysis). All non-meta wikis follow the schema.

END_WIKI_3x3_SCHEMA
