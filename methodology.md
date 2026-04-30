# Research Methodology
### DeepThought Business Analytics Internship — Part A

---

## City and Segment Selection

**Primary city: Hyderabad**
Chosen for its concentration of defence electronics, specialty biotech, and specialty chemicals manufacturers — all Federer-compatible segments. However, during research it became clear that Hyderabad's most prominent specialty manufacturers (Ananth Technologies, Apollo Micro Systems, Olectra, Suven Pharma) had either outgrown the Rs.500Cr ceiling or were PE/acquisition-controlled. Rather than inflate the list with marginal Hyderabad companies, I extended the search to Mumbai and Gujarat — both established specialty chemical and pharma intermediate clusters with a high density of promoter-driven MSMEs in the right revenue band. Hyderabad companies that passed are retained; the multi-city extension is a deliberate sourcing decision, not a scope error.

**Segments selected:**
- Specialty Chemicals (pharma intermediates, custom synthesis, niche heterocyclics, bromine/silicone chemistry)
- Specialty Biotech and Pharma (regulated APIs, veterinary APIs, probiotics, CDMOs with manufacturing)
- Animal Health Biotech

These segments were chosen because they concentrate technically-trained founders, have strong China+1 tailwinds, and produce differentiated products that non-engineers cannot easily replicate — the core of the Federer profile.

---

## Sourcing Process

### Initial Universe

The initial pool of candidate companies was built from:

- **Targeted Google searches** — queries like "USFDA approved API manufacturer Hyderabad", "specialty chemicals MSME Gujarat BSE SME listed", "bromine derivatives manufacturer India", "phase transfer catalyst manufacturer India"
- **BSE SME and NSE Emerge listings** — filtered by manufacturing sectors (chemicals, pharma, biotech) to find companies with public financials and leadership disclosures
- **Tofler and Zauba Corp** — used to cross-check revenue bands and director names for unlisted companies
- **Industry association references** — IDMA and BDMA member lists for pharma intermediates; DSIR recognition list for R&D-backed manufacturers
- **Similar-company discovery** — once one company was confirmed in a segment (e.g., Alkali Metals in niche heterocyclics), adjacent companies were found via supplier references, customer disclosures, and "companies also viewed" patterns on LinkedIn

Approximately 60–70 companies were investigated to produce the 25 in this list. The ~30% yield rate matches the expected rate stated in the assignment brief.

---

## AI Tools Used — and How

AI was used as a structured thinking partner at every stage, with manual verification as the mandatory follow-through. The workflow was:

**Claude (Anthropic)** — primary research and reasoning tool
- Used to expand the initial universe: given a confirmed company profile, Claude was asked to suggest comparable companies in the same niche
- Used to pressure-test C3 scoring: "Does USFDA approval on its own constitute differentiation, or does it also require niche product chemistry?" — Claude's answer helped calibrate the Moderate vs. Strong boundary
- Used to cross-check scoring logic against the rubric: evidence cells were drafted and then run through Claude to check whether the claim genuinely supported the score or was an assertion
- Claude was never asked to produce final verdicts. It was used to challenge, not to conclude

**Gemini (Google)** — secondary discovery and web search
- Used for company discovery searches where Google's index returned better results than direct queries
- Used to find recent news on companies (facility announcements, certifications, leadership changes) that might not appear on the company's own website
- All Gemini outputs were treated as leads, not facts — every result was independently verified on the company's official website or BSE filings

**GitHub Copilot** — used during Part B pipeline design (not Part A)
- No scraping or automation code was written for Part A — research was entirely manual
- Copilot is planned for use in the Part B 1000-company pipeline for writing the Python scraper and Claude API scoring pipeline

---

## Filtering Logic

Companies were evaluated sequentially, stopping at the first disqualifier:

**Stage 1 — Hard auto-disqualify (immediate rejection):**
- No website or placeholder site
- Revenue above Rs.500Cr (verified via BSE filings or Tofler)
- Service company, not manufacturer (CROs, testing labs, analytical services)
- PE/VC-controlled or recently acquired by large group
- Generic/bulk pharma (formulations, standard APIs without niche focus)
- Subsidiary of Tata, Godrej, Reliance, or similar large group

**Stage 2 — Six-criterion scoring:**
Companies that cleared Stage 1 were scored on C1–C6 using the rubric. Each criterion was scored Weak (0), Moderate (half weight), or Strong (full weight), with one specific, verifiable evidence point per criterion.

**Stage 3 — Verdict:**
- 80–100: Strong Fit — include with confidence
- 60–79: Fit — include, note caveats
- 40–59: Borderline — research further before including
- Below 40: Reject — document and exclude

---

## Controlling AI Hallucination

This was the most important operational discipline in the research.

**What AI was used for (safe uses):**
- Generating candidate company names to investigate
- Suggesting which segment-specific databases or sources to check
- Helping articulate why a company's product is or is not differentiated
- Reviewing draft evidence cells for logical consistency

**What AI was never used for (high hallucination risk):**
- Revenue figures — always cross-checked on BSE/NSE filings, Tofler, or MCA
- Leadership names and backgrounds — always verified on the company's /about or /leadership page, LinkedIn, or BSE annual report director section
- Certification claims (USFDA, EU-GMP, DSIR) — always verified against the respective regulatory body's public database or the company's official page
- Verdicts — scoring and verdict were always done by the researcher after reading the evidence, not delegated to AI

**Where AI was wrong and corrected:**
- Gemini suggested Privi Speciality Chemicals as a specialty chemicals Fit. Manual check of BSE filings showed FY24 revenue of approximately Rs.1500Cr — auto-disqualify. Revenue verification is non-negotiable and cannot be outsourced to AI.
- Claude suggested Astec LifeSciences as a strong agrochemical candidate. Manual check revealed it is now a Godrej Agrovet subsidiary — auto-disqualify. Ownership structure must always be verified independently.
- Both tools returned Vimta Labs as a biotech company. Manual website check confirmed it is a CRO — sells testing services, not products. Fails C1.

In each of these cases, AI provided the lead; manual verification caught the error.

---

## What Could Not Be Confirmed

Decision-maker academic backgrounds were not publicly available for the majority of companies. In these cases, C4 was scored Moderate rather than Strong, and the evidence cell explicitly notes the limitation. This is preferable to inferring "technical background" from the company's product complexity — which is an assertion, not evidence.

Where the DM name was found (Alkali Metals, Neogen Chemicals, Tatva Chintan) it is stated with the source. For all others, the recommended next step is BSE annual report → Director's Report section, which lists all directors with designations.

---

## Code

No automation code was written for Part A. All research was manual. For Part B, a full pipeline design using Python and Playwright for scraping and the Claude API for ICP scoring is described in the separate 1000-company proposal document.

---

## Key Insight from the Exercise

The challenge in this research is not discovery — it is filtering. The majority of time was spent ruling companies out, not finding them. The most common failure modes were:

- **Service companies in manufacturing-adjacent industries** — CROs, testing labs, and analytical service providers use the same industry language as manufacturers but sell no physical product
- **Revenue ceiling violations** — several strong-looking Hyderabad companies had scaled past Rs.500Cr, often in a single year, in defence and EV sectors
- **Ownership structure changes** — companies that were promoter-driven two or three years ago are now PE-controlled or group subsidiaries; this is not visible from the company's website alone and requires filings verification
- **Generic pharma disguised as specialty** — WHO-GMP and standard GMP compliance are hygiene factors for any regulated manufacturer, not evidence of differentiation; the product chemistry itself must be niche

These failure modes informed the filtering discipline applied throughout.
