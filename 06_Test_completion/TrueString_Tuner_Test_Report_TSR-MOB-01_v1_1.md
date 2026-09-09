# User Acceptance Test Summary Report: TrueString Tuner App Beta

Identifier: TSR-MOB-01  
Test Level: User Acceptance Testing (UAT)  
Current Status: Completed  
Version: v1.1  
Date: 2026-09-07  
Author: Annalie Prinsloo  

---

## 1. Document Control
### 1.1 Revision History
| Version | Date | Author | Description of Changes |
| :--- | :--- | :--- | :--- |
| 1.0 | 2026-06-05 | Annalie Prinsloo | Baseline Test Summary Report. |
| 1.1 | 2026-09-07 | Annalie Prinsloo | Fictionalized; rebuilt on the standard TSR template (matching `TSR-WEB-01`) with a full exit-criteria evaluation, verification metrics, residual risk assessment, and identifier updates to the `*-MOB-01` convention. |

### 1.2 References
* Test Plan: `TP-MOB-01`
* Requirements Traceability Matrix: `RTM-MOB-01`
* Test Conditions: `TCOND-MOB-01`
* Test Cases Suite: `TC-MOB-01`
* Test Data & Environment Setup: `TDS-MOB-01`
* Test Charters: `TCHAR-MOB-01`
* Test Procedures: `TPROC-MOB-01`
* Execution Log: `EL-MOB-01`
* Defect Reports: `BUG-MOB-01`, `BUG-MOB-02`
* ISTQB Foundation Level Syllabus (CTFL v4.0)

---

## 2. Summary of Testing Performed
This report summarizes the UAT phase of the TrueString Tuner App Beta (Version 6.0.9), executed against the scope, strategy, and criteria defined in `TP-MOB-01`. Testing was entirely manual and combined:

* **Synthetic pitch reference testing** using the Szynalski online tone generator against the app's frequency detection algorithm (`REQ-PT-01`).
* **Manual UI and dashboard verification** covering note profile display, layout integrity, orientation handling, notation toggles, and metric overlays, largely restricted to the Samsung Galaxy S25 FE (`REQ-UI-01` to `REQ-UI-05`).
* **Empirical physical instrument testing** across four real 6-string guitar configurations in both quiet-studio and high-noise acoustic environments (`REQ-INT-01`).
* **Exploratory testing** via three time-boxed charters (`TCHAR-MOB-01`) targeting rotation robustness, rapid notation/dashboard stress, and low-amplitude/noisy microphone boundaries.

Execution took place across four sessions between **2026-06-01** and **2026-06-05**, on the three physical Android devices defined in the Physical Device & Environment Matrix (`TP-MOB-01`, Section 4).

### 2.1 Requirements & Test Condition Coverage
| Metric | Result |
| :--- | :--- |
| Requirements in scope | 7 (`REQ-PT-01` to `REQ-INT-01`) |
| Requirements covered | 7 / 7 (100%) |
| Test conditions defined | 25 |
| Test conditions covered (traced to a test case and procedure) | 25 / 25 (100%) |
| Test conditions actually executed | 11 / 25 (44%) |
| Test conditions descoped (premium-tier locked) | 14 / 25 (56%) |

Every in-scope requirement and test condition is fully traced per `RTM-MOB-01`. However, coverage traceability is not the same as verification: 14 of the 25 defined test conditions — 11 of the 12 tuning profiles under `REQ-PT-01`, plus the Hz overlay, Cent gauge, and accidental notation toggle under `REQ-UI-04`/`REQ-UI-05` — could not be executed at all, because those features sit behind the app's premium-tier paywall and the test account used was free-tier. This was discovered during execution rather than anticipated in `TP-MOB-01`'s original Assumptions/Constraints (Section 3.4); see the Deviation Note in Section 3.1 below.

---

## 3. Evaluation Against Exit Criteria
This section evaluates actual results against the Exit Criteria defined in `TP-MOB-01`, Section 6.2.

| Exit Criterion (TP-MOB-01 §6.2) | Actual Result | Status |
| :--- | :--- | :--- |
| **Acoustic Accuracy** — 100% successful detection of target reference frequencies across all 12 tunings on all 3 phones. | Only 1 of 12 tunings (Standard) was testable; the other 11 are premium-tier locked and were never executed. The one testable tuning also initially failed via synthetic tone (`BUG-MOB-01`), later closed as invalid after physical-instrument retesting confirmed correct detection. | **Not Met** (as literally scoped) |
| **UI Precision** — Zero display anomalies, misalignments, or incorrect note names on the S25 FE for the Standard tuning profile. | `TCOND-UI-01` and `TCOND-UI-02` both passed cleanly; no anomalies observed in Standard tuning note display or dashboard layout. | **Met** |
| **Orientation Security** — App scales cleanly between portrait and landscape across all devices without losing calibration or freezing. | `TCOND-UI-04` (stability/freeze) passed on all tested devices — no crashes, freezes, or calibration loss occurred. `TCOND-UI-03` (scaling/text) failed on the S25 FE and S21 FE due to `BUG-MOB-02` (ad-triggered navigation bar truncation in portrait mode). | **Partially Met** |
| **Dashboard Indicator Integrity** — Perfect visual alignment of Hz, Cent, string highlight, and Solfège indicators on the S25 FE. | String highlight (`TCOND-UI-08`) and Solfège (`TCOND-UI-09`) passed cleanly. Hz (`TCOND-UI-06`) and Cent (`TCOND-UI-07`) are premium-tier locked and were never executed. | **Not Fully Verifiable** (half the criterion is untestable on the free tier) |
| **Microphone Resilience** — Reliable pitch capture across all 4 physical guitar styles in both studio and noisy environments for standard tuning. | All four instrument/environment combinations (`TCOND-INT-01` to `TCOND-INT-04`) passed in both the studio and high-noise environments. | **Met** |

### 3.1 Deviation Note
Two structural deviations from the plan surfaced during execution, both stemming from the same root cause — premium-tier feature restrictions on the test account:

* **Scope accuracy gap:** `TP-MOB-01` scoped `REQ-PT-01` around all 12 tuning profiles and `REQ-UI-05` around all four dashboard overlays, but 11 tuning profiles and 2 of the 4 overlays turned out to be inaccessible on the free tier used for testing. This was not identified as a Constraint in the original Test Plan (Section 3.4) and was only discovered once execution was underway (Session 1, `TCOND-PT-02` onward; Session 3, `TCOND-UI-06`/`TCOND-UI-07`). Per `TP-MOB-01` Section 6.4.3 (Control Actions), this deviation is documented here rather than silently rewritten into the original plan.
* **False-positive risk from synthetic test input:** `BUG-MOB-01` was ultimately closed as invalid — the app's pitch-detection algorithm requires the harmonic overtones present in real string vibrations, which pure sine-wave tone generators don't produce. This is a testing-methodology risk rather than a scope gap, and is carried forward as a lesson learned in Section 9.

Neither deviation triggered the formal Suspension Criteria in `TP-MOB-01` Section 6.3 — no 5xx-equivalent system failure or crash occurred, and the noise floor stayed within tolerance throughout.

---

## 4. Test Execution Metrics
| Metric | Result |
| :--- | :--- |
| Test condition coverage (traced) | 25 / 25 (100%) |
| Test condition execution rate | 11 / 25 executed (44%); 14 / 25 descoped (56%) |
| Pass rate among executed conditions | 9 / 11 (81.8%) |
| Requirements coverage | 7 / 7 (100%) |
| Open defect count | 1 (`BUG-MOB-02`) |
| Closed/rejected defect count | 1 (`BUG-MOB-01`, closed as invalid) |
| Exploratory charters executed | 3 (`CHARTER-UI-01`, `CHARTER-UI-02`, `CHARTER-INT-01`) — 2 passed, 1 descoped |

*Note on methodology: the metrics above are counted at the test-condition level (per `RTM-MOB-01`), since a single test condition (e.g. `TCOND-PT-01`) may be exercised across multiple devices in separate `EL-MOB-01` rows. Counted at the raw execution-log row level instead, `EL-MOB-01` contains 19 individual logged actions across the 4 sessions: 10 Pass, 5 Fail, 4 Descoped. This corrects the original TSR, which reported an inconsistent row total of 14 (8 Pass / 2 Fail / 4 Descoped) that undercounted the three-device failure spread of `BUG-MOB-01` and two of the `TPROC-UI-02` rows.*

---

## 5. Defect Summary
| Defect ID | Title | Severity | Priority | Status | Related Requirement |
| :--- | :--- | :--- | :--- | :--- | :--- |
| `BUG-MOB-01` | App fails to detect E2, A2, D3 synthetic frequency targets during standard tuning | Major | High | Closed (Rejected/Invalid) | `REQ-PT-01` |
| `BUG-MOB-02` | Bottom navigation bar truncates vertically when an interstitial ad renders in portrait mode | Medium | Medium | Open | `REQ-UI-03` |

**By severity:** 1 Major (closed/rejected), 1 Medium (open).
**By priority:** 1 High (closed/rejected), 1 Medium (open).
**Resolution status:** `BUG-MOB-01` is closed — root cause was a testing-methodology artifact (synthetic sine waves lack the harmonic overtones the algorithm relies on), not an app defect; physical-instrument retesting confirmed correct behavior. `BUG-MOB-02` remains open, targeted for `Version 6.0.10`.

---

## 6. Residual Risk Assessment
Referencing the Product Risks identified in `TP-MOB-01` Section 8.2:

* **PR-01** (real-world audio vs. synthetic tone mismatch) did materialize initially as `BUG-MOB-01`, but was resolved through the mitigation the risk register anticipated — early testing with physical instruments confirmed the underlying algorithm is sound. Residual risk: **Low**.
* **PR-02** (UI breaking under orientation change) partially materialized as `BUG-MOB-02` — not a crash or calibration loss, but a real layout defect tied to ad rendering in portrait mode on 2 of 3 devices, including the primary flagship (S25 FE). Residual risk: **Medium**, concentrated on the ad-supported free tier.
* **PR-03** (background noise blocking tuning detection) did not materialize — all instrument/environment combinations passed at up to 80 dB simulated noise.

One residual risk emerges that wasn't anticipated in Section 8.2:
* **Premium-tier coverage gap:** 11 of 12 tuning profiles and 2 of 4 dashboard overlays have **never been executed** under this UAT cycle, scripted or exploratory. This isn't a defect — it's an absence of verification. Residual risk: **High** for any premium-tier release decision, since there is currently zero UAT evidence for the majority of the app's paid feature set.

---

## 7. Deliverables Produced
| Deliverable | Identifier | Status |
| :--- | :--- | :--- |
| Test Plan | `TP-MOB-01` | Delivered |
| Requirements Traceability Matrix | `RTM-MOB-01` | Delivered |
| Test Conditions | `TCOND-MOB-01` | Delivered |
| Test Cases Suite | `TC-MOB-01` | Delivered |
| Test Data & Environment Setup | `TDS-MOB-01` | Delivered |
| Test Charters | `TCHAR-MOB-01` | Delivered |
| Test Procedures | `TPROC-MOB-01` | Delivered |
| Execution Log | `EL-MOB-01` | Delivered |
| Defect Reports | `BUG-MOB-01`, `BUG-MOB-02` | Delivered |
| Test Summary Report | `TSR-MOB-01` (this document) | Delivered |

---

## 8. Comparison to Plan
* **Schedule:** `TP-MOB-01`'s Milestones 1–3 (Section 7.4) tracked closely to Day 1–2 as planned. Milestones 5–6 (physical instrument trials and final sign-off, originally planned for separate Day 4 and Day 5 slots) were compressed into a single session on 2026-06-05, with no logged activity on the originally planned Day 4. The overall 5-day execution window (2026-06-01 to 2026-06-05) was still respected.
* **Effort:** Execution was carried out entirely by the sole assigned resource (Annalie Prinsloo), consistent with the staffing plan in `TP-MOB-01` Section 7.2.
* **Scope:** As detailed in Section 3.1, actual testable scope was materially smaller than planned scope for `REQ-PT-01` and `REQ-UI-05`, due to premium-tier restrictions not identified at planning time.

---

## 9. Lessons Learned
* **Synthetic tone generators carry false-positive risk for audio-processing software.** Pure sine waves lack the harmonic overtone structure of real instrument strings, which this app's detection algorithm depends on. Future Test Plans for pitch/audio-detection features should mandate physical instruments or high-fidelity recorded samples as the primary test input, using synthetic generators only for coarse sanity checks.
* **Tier/feature-gating should be verified during Test Analysis, not discovered during execution.** Add an explicit Entry Criterion to future mobile app Test Plans confirming which in-scope features are actually accessible on the test account's subscription tier before test conditions are finalized — this would have caught the 14 descoped conditions before execution began rather than partway through.
* **Retrofitting document control headers and ID conventions after the fact is more effort than establishing them upfront.** This document set originally had no Identifier/Version/Status header block on most artifacts and used inconsistent ID prefixes (`TC-` used for both test conditions and, via `TC-CASE-`, test cases). Future projects should apply the `REQ-` / `TCOND-` / `TC-` / `TPROC-` / `CHARTER-` / `BUG-` naming convention from the first document onward.

---

## 10. Overall Assessment & Release Recommendation
The free-tier core experience of TrueString Tuner — Standard tuning pitch detection (once validated against real instruments), dashboard note display, and physical microphone resilience across environments and guitar types — is solid. One defect remains open (`BUG-MOB-02`), affecting layout on 2 of 3 target devices including the primary flagship. Separately, the majority of the app's tuning-profile and dashboard-overlay feature set sits entirely outside this cycle's tested scope due to premium-tier access constraints.

**Recommendation:** **Conditional release for the free tier only**, contingent on `BUG-MOB-02` being resolved before the ad-supported experience ships broadly. **The premium tier is not cleared for release** on the basis of this UAT cycle — a follow-up UAT pass with premium-tier access is needed to verify the 11 untested tuning profiles and the Hz/Cent dashboard overlays before that tier can be considered production-ready.
