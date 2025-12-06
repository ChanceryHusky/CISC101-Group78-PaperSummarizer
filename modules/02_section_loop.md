
# Module 02: Section Loop

## Purpose
For each section or subsection in the paper:
- Extract text directly from the paper.
- Summarize within 50–100 words.
- Maintain consistent terminology (e.g., self‑Attention, multihead).
- Apply constraints: no outside sources, no hallucinations.

## New Requirement A: Summary Level Modes
The summarizer must support two summary levels for each section.

### Variable
- `summary_level` controls the output mode.
- Accepted values:
  - `"short"`
  - `"detailed"`

### Conditional Behavior
- If `summary_level = "short"`:
  - Generate only a compact summary (1–2 sentences).
- If `summary_level = "detailed"`:
  - Generate a short paragraph (50–100 words).
  - Add a bullet list of 3–5 key points.

## Section Loop Logic
For each section/subsection:
1. **Extract** text directly from the paper.
2. **Summarize** according to `summary_level`:
   - **short** → 1–2 sentence compact summary.
   - **detailed** → short paragraph + bullet list of 3–5 key points.
3. **Maintain terminology** consistency (self‑Attention, multihead).
4. **Apply constraints**: no outside sources, no hallucinations.

## Example

### Input Section



### Output (summary_level = "short")



### Output (summary_level = "detailed")
