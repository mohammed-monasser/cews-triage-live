# Clinical Early Warning System (CEWS)
### Low-Latency Critical Triage Engine & Forensic Audit Pipeline

An event-driven biomedical informatics pipeline engineered in **n8n** to eliminate human triage latency for acute laboratory anomalies.

## Architecture Overview
- **Trigger (Ingestion Layer):** Interactive Point-of-Care Form (`formTrigger`) capturing Patient ID, Age, RBS level, and INR level[cite: 3].
- **Temporal Normalization:** Standardizes timestamps to ISO-compliant structure (`yyyy-MM-dd HH:mm`) while preserving full payload state[cite: 1, 3].
- **Deterministic Rule Engine (Switch Node):** Multi-branch clinical evaluation logic:
  - **Dual Critical Risk (خطر مزدوج):** Concurrent elevation of INR (> 3.5–4.5) and RBS (> 300–400 mg/dL)[cite: 1, 3].
  - **Bleeding Liability (خطر نزيف):** Isolated critical INR elevation (> 3.5–4.5)[cite: 1, 3].
  - **Metabolic Crisis (خطر أيضي):** Acute glycemic spike (> 300–400 mg/dL; DKA/HHS risk)[cite: 1, 3].
- **Dispatch & Audit Layer:** Instant prioritized escalation alerts via Gmail REST API and parallel immutable audit persistence to Google Sheets[cite: 1, 3].

## Import & Deployment
1. Download `cews-workflow.json` from this repository.
2. Open your self-hosted or cloud **n8n** instance.
3. Navigate to **Workflows** -> click `...` (top right) -> **Import from File**.
4. Select `cews-workflow.json`[cite: 11].
5. Configure your Google Sheets and Gmail OAuth2 credentials to activate the dispatch and logging endpoints[cite: 3].

## Verification & Authorship
- **Lead Architect & Developer:** MOHAMMED JAMAL MOHAMMED ABDULRAHMAN MONASSER[cite: 2]
- **Passport Identification:** 16494003 (Republic of Yemen)[cite: 2]
- **Workflow Identifier:** CEWS-Triage-Live[cite: 1]
- **Research Scope:** Computer Science & Applied Artificial Intelligence in Healthcare[cite: 1]
