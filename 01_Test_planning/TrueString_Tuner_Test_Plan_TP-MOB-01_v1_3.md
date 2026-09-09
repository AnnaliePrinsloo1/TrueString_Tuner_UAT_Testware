# User Acceptance Test Plan: TrueString Tuner App Beta

Identifier: TP-MOB-01  
Test Level: User Acceptance Testing (UAT)  
Current Status: Completed  
Version: v1.3  
Date: 2026-09-07  
Author: Annalie Prinsloo  

---

## 1. Document Control
### 1.1 Revision History
| Version | Date | Author | Description of Changes |
| :--- | :--- | :--- | :--- |
| 1.1 | 2026-05-22 | Annalie Prinsloo | Baseline UAT Test Plan |
| 1.2 | 2026-05-29 | Annalie Prinsloo | UAT Test Plan structure updated for Beta Version 6.0.9, based on ISTQB CTFL v4.0 and ISO/IEC/IEEE 29119-3. |
| 1.3 | 2026-09-07 | Annalie Prinsloo | Fictionalized for public portfolio (app renamed to TrueString Tuner); identifiers migrated to the `*-MOB-01` convention; document restructured to align with the standard testware template (Test Objectives and Deliverables sections added, Device Matrix relocated from Appendix A into the main body, Test Monitoring & Control subsection added to Section 6). |

### 1.2 References
* TrueString Tuner App Beta Specifications (Version 6.0.9, Updated Dec 2, 2025)
* ISTQB Foundation Level Syllabus (CTFL v4.0)
* ISO/IEC/IEEE 29119-3 Standard for Software Testing Documentation
* Online Tone Generator (Szynalski) via <https://www.szynalski.com/tone-generator/>
* Decibel Meter Mobile Application (Version 3.0.1)

---

## 2. Test Objectives
The primary objective of this User Acceptance Testing (UAT) phase is to validate the real-world tuning accuracy, interface reliability, and physical microphone performance of the TrueString Tuner App Beta ahead of public deployment. Testing confirms that the free-tier core experience — pitch detection for Standard tuning, dashboard note display, screen orientation handling, and acoustic capture across varied physical guitar types and noise environments — behaves reliably across the designated device matrix before the app is advanced toward general release.

---

## 3. Context & Scope
### 3.1 Context of Testing (System Under Test)
The System Under Test (SUT) is the **TrueString Tuner App (Beta Version 6.0.9)** for Android. This UAT phase evaluates real-world tuning accuracy, user interface behavior, notation scaling, and physical microphone sensitivity under varying environmental noise floors before public deployment.

### 3.2 Features to be Tested (In-Scope)
* **`REQ-PT-01` (Pitch Accuracy Synthesis Frequency Matrix):** Verification of pitch calculations for 12 standardized tunings using synthesized wave frequencies on all 3 target devices.
* **`REQ-UI-01` (Tuning Note Profile Validation):** Verification that the correct expected notes display cleanly for the Standard tuning profile (Restricted to Samsung Galaxy S25 FE).
* **`REQ-UI-02` (Dashboard Visual Layout Validation):** Verification of layout design, asset placement, and structural UI integrity for the Standard tuning profile (Restricted to Samsung Galaxy S25 FE).
* **`REQ-UI-03` (Screen Orientation Responsive Layout):** Verification of layout scaling, stability, and text retention when changing between Portrait and Landscape views in Standard Tuning (Executed on all 3 target devices).
* **`REQ-UI-04` (Accidental Notation Toggle Processing):** Verification that note values dynamically update correctly when toggled between Sharp (#) and Flat (♭) states (Restricted to Samsung Galaxy S25 FE).
* **`REQ-UI-05` (Tuning Metric Overlay Configuration):** Validation of key UI indicators in Standard Tuning when individual dashboard toggles are adjusted (Restricted to Samsung Galaxy S25 FE):
  * Real-time frequency display in Hertz (Hz).
  * Micro-increment Cent offset gauge.
  * Active/Highlighted graphic guitar string indicator.
  * Solfège notation format display conversion.
* **`REQ-INT-01` (Acoustic Environment Instrument Capture):** Empirical execution checks utilizing 4 specific physical 6-string guitar configurations across two distinct acoustic environments (Studio vs High Noise) in Standard Tuning only.

### 3.3 Features Not to be Tested (Out-of-Scope)
* **Paid Platform / Paywall Mechanisms:** Testing the $9.26 premium transaction loop, ad network configurations, ad dismissal close-button hitboxes, or monetization pathways is completely out of scope.
* **Alternative Multi-String Formats:** Any physical testing utilizing instruments with atypical string counts (e.g., 7-string guitars, 4-string basses, mandolins, ukuleles) is strictly excluded.
* **Unlisted Physical Hardware:** Any testing on physical devices or operating system variants outside the 3 specified testing phones.

### 3.4 Assumptions, Constraints, and Dependencies
* **Assumptions:**
  * The T.P. Szynalski Online Tone Generator provides an accurate, stable reference standard for sinusoidal pitch checking.
* **Constraints:**
  * Advanced UI and component testing (`REQ-UI-01`, `REQ-UI-02`, `REQ-UI-04`, and `REQ-UI-05`) are physically restricted to the Samsung Galaxy S25 FE hardware profile.
  * Physical instrument testing is limited exclusively to 6-string instrument configurations.
* **Dependencies:**
  * Maintenance of a strict 10 dB to 30 dB sound environment monitored by the Decibel Meter App (v3.0.1) on the Samsung S25 FE for baseline controls and for the studio environment.
  * Maintenance of 70 dB to 90 dB for noisy environments monitored by the Decibel Meter App (v3.0.1) on the Samsung S25 FE.

---

## 4. Physical Device & Environment Matrix
| Device Model | Hardware Tier | Target OS | Test Suite Execution Scope | Acoustic Environments |
| :--- | :--- | :--- | :--- | :--- |
| Samsung Galaxy S25 FE | Flagship (Current) | Android 16 | `REQ-PT-01`, `REQ-UI-01`, `REQ-UI-02`, `REQ-UI-03`, `REQ-UI-04`, `REQ-UI-05`, `REQ-INT-01` | Studio Floor (10–30 dB), High Noise Environment (70–90 dB) |
| Samsung Galaxy S21 FE | Flagship (Legacy) | Android 16 | `REQ-PT-01`, `REQ-UI-03` | Studio Floor (10–30 dB) |
| Samsung Galaxy A53 5G | Mid-Range | Android 16 | `REQ-PT-01`, `REQ-UI-03` | Studio Floor (10–30 dB) |

---

## 5. Test Strategy & Approach
### 5.1 Test Levels and Test Types
* **Test Level:** User Acceptance Testing (UAT) / Beta Phase.
* **Test Types:**
  * **Functional Testing:** Validating accurate frequency identification, interface rendering correctness, notation state persistence, and screen re-orientation handling.
  * **Environmental Accessibility Testing:** Evaluating microphone detection thresholds across quiet and noisy environments.

### 5.2 Techniques for Test Design
* **Specification-Based Techniques:** Equivalence Partitioning applied to the target frequency spectrum, and explicit Use-Case validation of real musician setup paths.

### 5.3 Test Automation Approach
* Completely manual execution. The testing requires human instrumentation of physical guitars and manual verification of laptop tone generator output.

---

## 6. Entry, Exit & Suspension Criteria
### 6.1 Entry Criteria
* TrueString Tuner App Beta (Version 6.0.9) is installed successfully across all 3 test devices.
* Ambient room noise is verified between 10 dB and 30 dB via Decibel Meter App 3.0.1 on the Samsung S25 FE for baseline checks.
* The 4 physical 6-string guitar assets are present, functional, and ready for deployment.

### 6.2 Exit Criteria (Acceptance Criteria)
* **Acoustic Accuracy:** 100% successful detection of target reference frequencies across all 12 tunings on all 3 phones.
* **UI Precision:** Zero display anomalies, misalignments, or incorrect note names visible on the Samsung S25 FE for the Standard tuning profile.
* **Orientation Security:** The application scales cleanly between portrait and landscape modes across all devices without losing calibration or freezing.
* **Dashboard Indicator Integrity:** Perfect visual alignment of Hz readouts, cent adjustments, highlighted strings, and Solfège variations when toggled on the Samsung S25 FE.
* **Microphone Resilience:** Reliable pitch capture across all 4 target physical 6-string guitar styles in both studio and noisy environments for standard tuning.

### 6.3 Suspension and Resumption Criteria
* **Suspension Criteria:** If background sound metrics exceed 30 dB during controlled synth-tone capture, or if an app crash occurs during device orientation changes.
* **Resumption Criteria:** Testing will resume once ambient noise levels settle back to the 10–30 dB range, or when a stable build fix is deployed.

### 6.4 Test Monitoring & Control
#### 6.4.1 Metrics Collected
* Test condition execution progress: % of planned test conditions executed to date.
* Pass/fail/descoped rate: % of executed test conditions passing, tracked against the Exit Criteria thresholds in Section 6.2.
* Defect metrics: open defect count by severity, logged against `BUG-MOB-01` onward.
* Requirements coverage: % of in-scope requirements (`REQ-PT-01` to `REQ-INT-01`) with at least one executed test condition, tracked via the RTM (`RTM-MOB-01`).
* Descope tracking: count and proportion of test conditions descoped due to premium-tier restrictions, monitored so that free-tier coverage claims stay accurate.

#### 6.4.2 Reporting Cadence
* Progress is reviewed against each milestone defined in Section 7.4, with a status summary recorded at the completion of each milestone.
* The Execution Log (`EL-MOB-01`) is updated on each test session, providing a continuous record between milestones.

#### 6.4.3 Control Actions
* If defect density or severity trends indicate a blocking risk to Exit Criteria (Section 6.2), remaining execution is re-prioritized toward the highest-risk requirements (see Section 8.2 Product Risks) before continuing lower-priority coverage.
* If a Suspension Criterion (Section 6.3) is triggered, testing halts and is resumed only once the corresponding Resumption Criterion is met.
* Any deviation from the schedule in Section 7.4, or from the planned scope in Section 3.2 (e.g. features found to be inaccessible at execution time), is documented in the Test Report (`TSR-MOB-01`) along with the root cause.

---

## 7. Logistics, Resources & Schedule
### 7.1 Test Environment and Tools Requirements
* **Primary Audio Output:** Laptop workspace executing reference audio via the Szynalski platform.
* **Acoustic Environment Control Node:** Decibel Meter App (Version 3.0.1) active on the Samsung Galaxy S25 FE.
* **Physical Testing Asset Registry:**
  1. Steel-string acoustic guitar (6-string)
  2. Nylon-string classical guitar (6-string)
  3. Electric guitar (Unamplified/Amp off)
  4. Electric guitar connected to amplifier (Output set to an unmodified, raw clean tone)

### 7.2 Roles, Responsibilities, and Staffing
* **UAT Project Lead & Execution Specialist:** Annalie Prinsloo
  * *Responsibilities:* Calibrating the noise floor, running tone checks, handling physical guitars, capturing display anomalies, and logging defects.

### 7.3 Work Breakdown and Estimates
| Task Item | Target Resource | Estimated Effort |
| :--- | :--- | :--- |
| Environment Setup & Noise Floor Verification | Annalie Prinsloo | 0.5 Hours |
| `REQ-PT-01`: Synthetic 12-Tuning Reference Run (3 Devices) | Annalie Prinsloo | 2.0 Hours |
| `REQ-UI-01`, `REQ-UI-02` & `REQ-UI-04`: UI Content & Notation (S25 Only) | Annalie Prinsloo | 3.0 Hours |
| `REQ-UI-03`: Portrait vs Landscape Rotation Stress Suite (3 Devices) | Annalie Prinsloo | 1.0 Hours |
| `REQ-UI-05`: Dashboard Component Toggle Analysis (S25 Only) | Annalie Prinsloo | 1.0 Hour |
| `REQ-INT-01`: Physical 4-Guitar Acoustic Environment Matrix | Annalie Prinsloo | 2.0 Hours |

### 7.4 Milestones and Schedule
* **Milestone 1:** Laboratory Environment Acoustic Calibration Sign-off — Day 1 (08:30)
* **Milestone 2:** Synthetic Freq Sweep (`REQ-PT-01`) Complete — Day 1 (10:10)
* **Milestone 3:** UI, Rotation, and Metric Dashboard Tests (`REQ-UI-01` to `REQ-UI-03`) Complete — Day 2 (11:00)
* **Milestone 4:** UI, Rotation, and Metric Dashboard Tests (`REQ-UI-04` to `REQ-UI-05`) Complete — Day 3 (09:00)
* **Milestone 5:** Empirical Instrument Trials (`REQ-INT-01`) Complete — Day 4 (10:00)
* **Milestone 6:** Final UAT Documentation Complete & Signed Off — Day 5 (16:00)

---

## 8. Communication & Risk Management
### 8.1 Communication Protocols and Status Reporting
* Testing results, layout issues, or frequency tracking failures will be captured in Markdown and delivered to development teams at the close of each testing window.

### 8.2 Product Risks (Quality Risks)
| Risk ID | Risk Description | Impact level | Mitigation Action |
| :--- | :--- | :--- | :--- |
| **PR-01** | The application fails to process real-world physical guitar audio frequencies while passing ideal synthetic tone tests (`REQ-INT-01`). | High | Test early with the unamplified electric guitar to identify baseline physical microphone pickup issues. |
| **PR-02** | The UI layout breaks, truncates text, or crashes when transitioning between landscape and portrait views (`REQ-UI-03`). | Medium | Run rapid back-and-forth rotation tests on all 3 target devices to check for memory leaks or display errors. |
| **PR-03** | High ambient background chatter completely blocks standard tuning verification in the noisy environment test step (`REQ-INT-01`). | Medium | Use a clear, step-by-step scaling approach for the background noise to find the exact point the tuner fails. |

### 8.3 Project Risks (Management Risks)
| Risk ID | Risk Description | Impact level | Mitigation Action |
| :--- | :--- | :--- | :--- |
| **OR-01** | External environment noise leaks into the lab, spiking past the 30 dB cap during synthetic frequency checks. | Medium | Conduct critical synthetic tone matching sessions during low-traffic, off-peak laboratory hours. |

---

## 9. Deliverables
* **Test Plan:** This document (TP-MOB-01 v1.3)
* **Requirements Traceability Matrix (RTM):** RTM-MOB-01
* **Test Conditions:** TCOND-MOB-01
* **Test Cases Suite:** TC-MOB-01
* **Test Data & Environment Setup:** TDS-MOB-01
* **Test Charters:** TCHAR-MOB-01
* **Test Procedures:** TPROC-MOB-01
* **Execution Log:** EL-MOB-01
* **Defect Reports:** BUG-MOB-01 to BUG-MOB-02
* **Test Report:** TSR-MOB-01
