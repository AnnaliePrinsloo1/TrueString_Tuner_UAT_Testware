# Requirements Traceability Matrix (RTM)

**Identifier:** RTM-MOB-01  
**Version:** v1.1  
**Test Basis:** Functional Scope & Requirements (TrueString Tuner Test Plan: TP-MOB-01)  
**Status:** Completed  
**Date:** 2026-09-07  
**Author:** Annalie Prinsloo  

---

## 1. Document Control
### 1.1 Revision History
| Version | Date | Author | Description of Changes |
| :--- | :--- | :--- | :--- |
| 1.0 | 2026-05-29 | Annalie Prinsloo | Baseline RTM for internal execution tracking. |
| 1.1 | 2026-09-07 | Annalie Prinsloo | Fictionalized; identifiers migrated to `*-MOB-01` convention (Test Condition IDs renamed `TC-xx` → `TCOND-xx`, Test Case IDs renamed `TC-CASE-xx` → `TC-xx`, Procedure IDs renamed `PROC-xx` → `TPROC-xx`); added Related Defect ID(s) column and Verification Metrics Summary to match the standard testware template. |

---

## 2. Traceability Ledger
| Req ID | Req Description | Test Condition ID | Test Case ID | Test Procedure ID | Execution Status | Related Defect ID(s) |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **`REQ-PT-01`** | Synthetic Freq Matrix (Standard) | **`TCOND-PT-01`** | `TC-PT-01` | `TPROC-PT-01` | Fail | **`BUG-MOB-01`** (Closed/Rejected) |
| **`REQ-PT-01`** | Synthetic Freq Matrix (Drop D) | **`TCOND-PT-02`** | `TC-PT-01` | `TPROC-PT-01` | Descoped (only available on premium tier) | N/A |
| **`REQ-PT-01`** | Synthetic Freq Matrix (Half-step D#) | **`TCOND-PT-03`** | `TC-PT-01` | `TPROC-PT-01` | Descoped (only available on premium tier) | N/A |
| **`REQ-PT-01`** | Synthetic Freq Matrix (DADGAD) | **`TCOND-PT-04`** | `TC-PT-01` | `TPROC-PT-01` | Descoped (only available on premium tier) | N/A |
| **`REQ-PT-01`** | Synthetic Freq Matrix (Open G) | **`TCOND-PT-05`** | `TC-PT-01` | `TPROC-PT-01` | Descoped (only available on premium tier) | N/A |
| **`REQ-PT-01`** | Synthetic Freq Matrix (Open D) | **`TCOND-PT-06`** | `TC-PT-01` | `TPROC-PT-01` | Descoped (only available on premium tier) | N/A |
| **`REQ-PT-01`** | Synthetic Freq Matrix (D Standard) | **`TCOND-PT-07`** | `TC-PT-01` | `TPROC-PT-01` | Descoped (only available on premium tier) | N/A |
| **`REQ-PT-01`** | Synthetic Freq Matrix (Drop C) | **`TCOND-PT-08`** | `TC-PT-01` | `TPROC-PT-01` | Descoped (only available on premium tier) | N/A |
| **`REQ-PT-01`** | Synthetic Freq Matrix (Open E) | **`TCOND-PT-09`** | `TC-PT-01` | `TPROC-PT-01` | Descoped (only available on premium tier) | N/A |
| **`REQ-PT-01`** | Synthetic Freq Matrix (All Fourths) | **`TCOND-PT-10`** | `TC-PT-01` | `TPROC-PT-01` | Descoped (only available on premium tier) | N/A |
| **`REQ-PT-01`** | Synthetic Freq Matrix (Double Drop D) | **`TCOND-PT-11`** | `TC-PT-01` | `TPROC-PT-01` | Descoped (only available on premium tier) | N/A |
| **`REQ-PT-01`** | Synthetic Freq Matrix (Open G Alt 1) | **`TCOND-PT-12`** | `TC-PT-01` | `TPROC-PT-01` | Descoped (only available on premium tier) | N/A |
| **`REQ-UI-01`** | Tuning Note Profile Validation | **`TCOND-UI-01`** | `TC-UI-01` | `TPROC-UI-01` | Pass | N/A |
| **`REQ-UI-02`** | Dashboard Visual Layout Validation | **`TCOND-UI-02`** | `TC-UI-01` | `TPROC-UI-01` | Pass | N/A |
| **`REQ-UI-03`** | Orientation Layout (Scale/Text) | **`TCOND-UI-03`** | `TC-UI-02` | `TPROC-UI-02` | Fail | **`BUG-MOB-02`** (Open) |
| **`REQ-UI-03`** | Orientation Layout (Stability/Freeze) | **`TCOND-UI-04`** | `TC-UI-02` | `TPROC-UI-02` | Pass | N/A |
| **`REQ-UI-04`** | Accidental Notation Toggle Processing | **`TCOND-UI-05`** | `TC-UI-03` | `TPROC-UI-03` | Descoped (half-step down D# only available on premium tier) | N/A |
| **`REQ-UI-05`** | Dashboard Overlays (Hz Display) | **`TCOND-UI-06`** | `TC-UI-04` | `TPROC-UI-04` | Descoped (Hertz display toggle only available on premium tier) | N/A |
| **`REQ-UI-05`** | Dashboard Overlays (Cent Gauge) | **`TCOND-UI-07`** | `TC-UI-04` | `TPROC-UI-04` | Descoped (Cent offset display toggle only available on premium tier) | N/A |
| **`REQ-UI-05`** | Dashboard Overlays (String Highlight) | **`TCOND-UI-08`** | `TC-UI-04` | `TPROC-UI-04` | Pass | N/A |
| **`REQ-UI-05`** | Dashboard Overlays (Solfège Format) | **`TCOND-UI-09`** | `TC-UI-04` | `TPROC-UI-04` | Pass | N/A |
| **`REQ-INT-01`** | Instrument Capture (Steel Acoustic) | **`TCOND-INT-01`** | `TC-INT-01` | `TPROC-INT-01` | Pass | N/A |
| **`REQ-INT-01`** | Instrument Capture (Nylon Classical) | **`TCOND-INT-02`** | `TC-INT-01` | `TPROC-INT-01` | Pass | N/A |
| **`REQ-INT-01`** | Instrument Capture (Electric Amp Off) | **`TCOND-INT-03`** | `TC-INT-01` | `TPROC-INT-01` | Pass | N/A |
| **`REQ-INT-01`** | Instrument Capture (Electric Clean Amp) | **`TCOND-INT-04`** | `TC-INT-01` | `TPROC-INT-01` | Pass | N/A |

---

## 3. Exploratory Testing Coverage
Three exploratory charters (`TCHAR-MOB-01`) supplemented the scripted test conditions above. None surfaced a defect beyond those already captured via scripted execution:

| Charter ID | Target Area | Outcome |
| :--- | :--- | :--- |
| `CHARTER-UI-01` | Rapid rotation & layout interruptions (`REQ-UI-03`) | Passed — no additional defects found. |
| `CHARTER-UI-02` | Rapid notation/dashboard toggle stress (`REQ-UI-04`, `REQ-UI-05`) | Descoped — target features are premium-tier only. |
| `CHARTER-INT-01` | Low-amplitude & noisy microphone boundaries (`REQ-INT-01`) | Passed — no additional defects found. |

---

## 4. Verification Metrics Summary
* **Total requirements defined:** 7
* **Total requirements covered:** 7 / 7 (100%)
* **Total test conditions defined:** 25
* **Total test conditions covered (traced to a test case and procedure):** 25 / 25 (100%)
* **Test conditions executed (attempted):** 11 / 25 (44%)
* **Test conditions descoped (premium-tier locked):** 14 / 25 (56%)
* **Pass rate among executed test conditions:** 9 / 11 (81.8%)
* **Unmapped requirements:** 0
