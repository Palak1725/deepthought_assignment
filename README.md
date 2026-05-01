# DeepThought Business Analytics Internship — Part A
### Target Company Research: Indian Specialty Manufacturers

---

## What This Is

This repository contains Part A of the DeepThought Business Analytics internship assignment — a structured research exercise to identify 25 Indian manufacturing companies that match DeepThought's "Federer" ICP: promoter-driven specialty manufacturers with active growth signals, technical decision-makers, and differentiated products in the Rs.50Cr–Rs.500Cr revenue band.

---

## Repository Contents

| File | What It Contains |
|------|-----------------|
| `companies.xslx` | 25 profiled companies — passes, borderlines, and documented fails — each scored on 6 criteria with evidence |
| `methodology.md` | Full research process: city selection rationale, sourcing approach, AI tools used, hallucination controls, filtering logic |

---

## City and Segments

**Primary city:** Hyderabad, with extension to Mumbai and Gujarat
Hyderabad's most prominent specialty manufacturers were either above the Rs.500Cr revenue ceiling or PE/acquisition-controlled. The research extended to Mumbai and Gujarat specialty chemical clusters to reach 25 qualified companies. Full rationale in `methodology.md`.

**Segments covered:**
- Specialty chemicals (niche heterocyclics, bromine chemistry, silicone pharmaceuticals, phase transfer catalysts, oleochemicals)
- Regulated pharma API (USFDA-approved, veterinary APIs, CDMO with manufacturing)
- Specialty biotech (human and animal probiotics, fermentation-based products)

---

## Scoring Summary

| Verdict | Count |
|---------|-------|
| Strong Fit (80–100) | 7 |
| Fit (60–79) | 7 |
| Borderline (40–59) | 1 |
| Reject / Auto-disqualify | 10 |
| **Total** | **25** |

Documented rejects include: generic pharma manufacturers, a CRO, a PE-controlled CDMO, a large-group subsidiary, a company above the revenue ceiling, and two undifferentiated agri-biotech SMEs. These are included deliberately — the filtering reasoning is as important as the passes.

---

## AI Tools Used

| Tool | Role |
|------|------|
| **Claude (Anthropic)** | Primary research partner — universe expansion, scoring logic review, evidence quality check |
| **Gemini (Google)** | Secondary discovery — recent news, certification announcements, facility updates |
| **GitHub Copilot** | Used for Part B pipeline design; not used for Part A manual research |

All AI outputs were treated as leads requiring manual verification. Revenue figures, leadership backgrounds, and regulatory approvals were always cross-checked against BSE filings, Tofler, official regulatory databases, or company websites. See `methodology.md` for specific cases where AI was wrong and corrected.

---

## How to Read the CSV

Each row has:
- **C1–C6 Score + Evidence** — one specific, verifiable fact per criterion, not assertions
- **Federer Score** — weighted sum out of 100 following the rubric exactly
- **Verdict** — Strong Fit / Fit / Borderline / Reject, with one-line reasoning
- **Personalization Hook** — one specific, recent, true detail usable as the opening line of an outreach email

Reject rows are fully scored where possible — they show why the company failed, not just that it failed.
