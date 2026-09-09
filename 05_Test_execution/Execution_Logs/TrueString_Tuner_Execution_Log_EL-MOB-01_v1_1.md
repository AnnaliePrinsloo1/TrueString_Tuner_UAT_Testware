# Test Execution Log (Chronological Record)

**Identifier:** EL-MOB-01  
**Version:** v1.1  
**Test Basis:** Functional Scope & Requirements (TrueString Tuner Test Plan: TP-MOB-01)  
**Status:** Completed  
**Date:** 2026-06-05  
**Author:** Annalie Prinsloo  

---

## 1. Document Control
### 1.1 Revision History
| Version | Date | Author | Description of Changes |
| :--- | :--- | :--- | :--- |
| 1.0 | 2026-06-05 | Annalie Prinsloo | Baseline execution log covering Sessions 1–4. |
| 1.1 | 2026-09-07 | Annalie Prinsloo | Fictionalized; Procedure IDs renamed `PROC-xx` → `TPROC-xx`; added the Target Test Condition ID column for traceability with `TCOND-MOB-01`; corrected the Session 3 charter reference (originally logged as the non-existent `CHARTER-UI-03`) to `CHARTER-INT-01`, based on the matching mission description ("Low-Amplitude and Noisy Microphone Boundaries") in `TCHAR-MOB-01`; defect IDs updated to `BUG-MOB-01`/`BUG-MOB-02`. |

---

## 2. Daily Execution Summary Tables

### Date: 2026-06-01 (UAT Testing Session 1)
* **Environment Baseline Noise Floor:** Verified at 20 dB via control node (Decibel Meter App v3.0.1 on Samsung S25 FE).
* **Build Under Test:** TrueString Tuner App Beta (Version 6.0.9).

| Timestamp | Procedure / Charter ID | Target Test Condition ID | Tester Name | Platform / Env | Status (Pass/Fail/Block) | Linked Defect ID | Actual Results / Notes |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 10:10 AM | `TPROC-PT-01` | `TCOND-PT-01` | A. Prinsloo | Samsung S25 FE | Fail | **BUG-MOB-01** | Some of the synthetic frequency matrix targets were not detected for standard tuning. |
| 10:40 AM | `TPROC-PT-01` | `TCOND-PT-01` | A. Prinsloo | Samsung S21 FE | Fail | **BUG-MOB-01** | Some of the synthetic frequency matrix targets were not detected for standard tuning. |
| 11:10 AM | `TPROC-PT-01` | `TCOND-PT-01` | A. Prinsloo | Samsung A53 5G | Fail | **BUG-MOB-01** | Some of the synthetic frequency matrix targets were not detected for standard tuning. |

### Date: 2026-06-02 (UAT Testing Session 2)
* **Build Under Test:** TrueString Tuner App Beta (Version 6.0.9).

| Timestamp | Procedure / Charter ID | Target Test Condition ID | Tester Name | Platform / Env | Status (Pass/Fail/Block) | Linked Defect ID | Actual Results / Notes |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 11:00 AM | `TPROC-UI-01` | `TCOND-UI-01`, `TCOND-UI-02` | A. Prinsloo | Samsung S25 FE | Pass | N/A | The Standard tuning layout notes and labels display with zero truncation. |
| 11:10 AM | `TPROC-UI-02` | `TCOND-UI-03`, `TCOND-UI-04` | A. Prinsloo | Samsung S25 FE | Fail | **BUG-MOB-02** | The Standard tuning dashboard visual layout displays correctly and with zero truncation on landscape view but truncates menu on portrait view when advert appears. |
| 11:20 AM | `TPROC-UI-02` | `TCOND-UI-03`, `TCOND-UI-04` | A. Prinsloo | Samsung S21 FE | Fail | **BUG-MOB-02** | The Standard tuning dashboard visual layout displays correctly and with zero truncation on landscape view but truncates menu on portrait view when advert appears. |
| 11:30 AM | `TPROC-UI-02` | `TCOND-UI-03`, `TCOND-UI-04` | A. Prinsloo | Samsung A53 5G | Pass | N/A | The Standard tuning dashboard visual layout displays correctly and with zero truncation. |

### Date: 2026-06-03 (UAT Testing Session 3)
* **Build Under Test:** TrueString Tuner App Beta (Version 6.0.9).

| Timestamp | Procedure / Charter ID | Target Test Condition ID | Tester Name | Platform / Env | Status (Pass/Fail/Block) | Linked Defect ID | Actual Results / Notes |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 09:00 PM | `TPROC-UI-03` | `TCOND-UI-05` | A. Prinsloo | Samsung S25 FE | Descoped | N/A | Half step down D# tuning setting only available on premium tier. |
| 09:10 PM | `TPROC-UI-04` | `TCOND-UI-06` | A. Prinsloo | Samsung S25 FE | Descoped | N/A | Hz readout only available on premium tier. |
| 09:20 PM | `TPROC-UI-04` | `TCOND-UI-07` | A. Prinsloo | Samsung S25 FE | Descoped | N/A | Cent needle only available on premium tier. |
| 09:30 PM | `TPROC-UI-04` | `TCOND-UI-08` | A. Prinsloo | Samsung S25 FE | Pass | N/A | Active string highlights update in real-time. |
| 09:40 PM | `TPROC-UI-04` | `TCOND-UI-09` | A. Prinsloo | Samsung S25 FE | Pass | N/A | Solfège Format displays correctly. |
| 09:50 PM | `CHARTER-UI-02` | N/A | A. Prinsloo | Samsung S25 FE | Descoped | N/A | The features are only available on the premium tier. |

---

### Date: 2026-06-05 (UAT Testing Session 4)
* **Environment Baseline Noise Floor:** Verified at 20 dB via control node for studio environment and at 80 dB for high noise environment (Decibel Meter App v3.0.1 on Samsung S25 FE).
* **Build Under Test:** TrueString Tuner App Beta (Version 6.0.9).

| Timestamp | Procedure / Charter ID | Target Test Condition ID | Tester Name | Platform / Env | Status (Pass/Fail/Block) | Linked Defect ID | Actual Results / Notes |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 10:00 AM | `TPROC-INT-01` | `TCOND-INT-01`, `TCOND-INT-02` | A. Prinsloo | S25 FE / Studio | Pass | N/A | Physical Steel-String Acoustic and Nylon Classical picked up instantly. |
| 10:30 AM | `TPROC-INT-01` | `TCOND-INT-03`, `TCOND-INT-04` | A. Prinsloo | S25 FE / Studio | Pass | N/A | Unamplified & amplified electric guitar picked up instantly. |
| 11:30 AM | `TPROC-INT-01` | `TCOND-INT-01`, `TCOND-INT-02` | A. Prinsloo | S25 FE / Noise | Pass | N/A | Software safely isolates steel acoustic & classical nylon guitar tones from chatter simulation. |
| 12:00 PM | `TPROC-INT-01` | `TCOND-INT-03`, `TCOND-INT-04` | A. Prinsloo | S25 FE / Noise | Pass | N/A | Software safely isolates unamplified & amplified electric guitar tones from chatter simulation. |
| 12:30 PM | `CHARTER-UI-01` | N/A | A. Prinsloo | Samsung S25 FE | Pass | N/A | Backgrounding app and restoring state preserves active tuning selection. |
| 01:00 PM | `CHARTER-INT-01` | N/A | A. Prinsloo | Samsung S25 FE | Pass | N/A | Low-Amplitude and Noisy Microphone Boundaries — mic picked up faint plucks and stayed isolated from chatter in the noisy environment. |
