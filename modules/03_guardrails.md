# Module 03: Guardrails

## Purpose
Ensure summarization is safe, accurate, and strictly grounded in the source paper.

## Existing Guardrails
- **Handle missing or empty sections**: skip gracefully.
- **Detect and correct <50‑word summaries**: enforce minimum length.
- **Mitigate hallucinations**: enforce “paper‑only” rule.
- **Apply long‑paper chunking strategies**: use PS2 context‑window methods to manage large text spans.

---

## New Requirement B: Strengthen Evidence & Hallucination Guardrails

### Strict Evidence Mode
Introduce a mode or flag:  
- `evidence_mode = "strict"`

**Behaviour when set to "strict":**
- Only include claims, equations, and results that appear in the provided text.
- No external information, assumptions, or inferred content.
- If insufficient information is found, output explicitly:  


### Section Warning Messages
For sections that are missing, empty, or too short (< 50 words), output standardized warnings:

- If missing/empty:  


- If too short (< 50 words):

---

## Section Guardrail Logic
For each section/subsection:
1. **Check content availability**:
 - If missing/empty → output “Section skipped: no usable text was provided.”
2. **Check length**:
 - If < 50 words → output “Section very short: summary may be incomplete.”
3. **Apply evidence mode**:
 - If `evidence_mode = "strict"` → only summarize claims/results explicitly in text.
 - If insufficient detail → output strict evidence warning.
4. **Apply chunking strategies**:
 - Use PS2 context‑window methods for large spans.

---

## Example

### Input Section


### Output (evidence_mode = "strict")



