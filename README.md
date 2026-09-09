<div align="center">

### Tech Stack
![Markdown](https://img.shields.io/badge/markdown-%23000000.svg?style=for-the-badge&logo=markdown&logoColor=white)
![Android](https://img.shields.io/badge/Android-%233DDC84.svg?style=for-the-badge&logo=android&logoColor=white)

### Testing Scope
![UAT](https://img.shields.io/badge/UAT-000080?style=for-the-badge&logo)
![Functional](https://img.shields.io/badge/Functional-000080?style=for-the-badge&logo)
![Non--Functional](https://img.shields.io/badge/Non--Functional-000080?style=for-the-badge&logo)

### Test Environment
![Samsung](https://img.shields.io/badge/Samsung-%231428A0.svg?style=for-the-badge&logo=samsung&logoColor=white&logoSize=auto)
![Android](https://custom-icon-badges.demolab.com/badge/Android%2016-3DDC84?style=for-the-badge&logo=android&logoColor=white)

### Documentation reviewed with
![Claude](https://img.shields.io/badge/claude-%23D97757.svg?style=for-the-badge&logo=claude&logoColor=white)

</div>

# TrueString Tuner App (Beta) - End-to-End User Acceptance Test (UAT) Run

*Note on confidentiality: The app name and branding used in this repository have been fictionalized. Manual testing engagements are confidential by nature and cannot be publicly disclosed; this repository demonstrates the same process, documentation standards, and physical-device testing approach applied on real client work, using a fictional app so it can be shared openly as a portfolio piece.*

An end-to-end user acceptance testing (UAT) testware repository showcasing a fully manual approach to mobile app testing, structured to reflect the ISTQB Foundation Level (CTFL v4.0) fundamental test process.

This repository hosts the complete testware suite and execution records for the UAT validation of a fictional Android guitar tuning application, **TrueString Tuner (Beta v6.0.9)**.

The primary objective of this project was to manually verify the app's real-time pitch detection accuracy across core 6-string tunings using an external frequency reference, while verifying notation toggles, UI responsiveness across screen orientations, and microphone reliability in varying acoustic environments using three physical test devices.

**Note:** Pitch detection, notation toggling, and dashboard overlay coverage were substantially limited by the app's premium-tier paywall — only the Standard tuning profile and 2 of 4 dashboard overlays were accessible on the free-tier test account used. See `TSR-MOB-01` for the full scope-coverage analysis.

## Contents
- [Physical Device & Environment Matrix](#physical-device--environment-matrix)
- [Test Process Documentation Structure](#test-process-documentation-structure)
- [Validation Methodologies & Test Quality Metrics](#validation-methodologies--test-quality-metrics)
- [Active Test Cycle Insights](#active-test-cycle-insights)
- [About the QA Professional](#about-the-qa-professional)

---

## Physical Device & Environment Matrix
Testing was conducted strictly on physical Android devices to expose hardware-specific defects that emulators cannot replicate, such as microphone sensitivity variations, hardware audio routing latencies, and device-specific memory management profiles.

* **Device 1 (Primary Flagship Tier):** Samsung Galaxy S25 FE | Android 16
* **Device 2 (Legacy Flagship Tier):** Samsung Galaxy S21 FE | Android 16
* **Device 3 (Mid-Range Tier):** Samsung Galaxy A53 5G | Android 16

*Acoustic testing profiles covered both isolated quiet studio environments (10–30 dB) and high-ambient-noise environments (70–90 dB) using built-in microphone arrays.*

---

## Test Process Documentation Structure
The repository is organized into sequential testing phases to maintain a clear, auditable execution record:

```text
├── README.md
├── 01_Test_planning/
│   └── TrueString_Tuner_Test_Plan_TP-MOB-01_v1.3.md
├── 02_Test_analysis/
│   ├── TrueString_Tuner_RTM-MOB-01_v1.1.md
│   └── TrueString_Tuner_Test_Conditions_TCOND-MOB-01_v1.1.md
├── 03_Test_design/
│   ├── TrueString_Tuner_Test_Cases_Suite_TC-MOB-01_v1.1.md
│   └── TrueString_Tuner_Test_Charters_TCHAR-MOB-01_v1.1.md
├── 04_Test_implementation/
│   ├── TrueString_Tuner_Test_Data_Setup_TDS-MOB-01_v1.1.md
│   └── TrueString_Tuner_Test_Procedures_TPROC-MOB-01_v1.1.md
├── 05_Test_execution/
│   ├── TrueString_Tuner_Execution_Log_EL-MOB-01_v1.1.md
│   ├── TrueString_Tuner_Defect_Report_BUG-MOB-01.md
│   ├── TrueString_Tuner_Defect_Report_BUG-MOB-02.md
│   ├── S21_GUI_Truncation.jpg
│   └── S25_GUI_Truncation.jpg
└── 06_Test_completion/
    └── TrueString_Tuner_Test_Report_TSR-MOB-01_v1.1.md
```

**Note:** Test Charters (`TCHAR-MOB-01`) are filed under `03_Test_design`, alongside the Test Cases Suite, rather than under Test Implementation or Execution — exploratory charters are a test *design* artifact (they define what will be explored and how), even though the exploration itself happens during the execution phase. Test Data & Environment Setup (`TDS-MOB-01`) remains under `04_Test_implementation`, since per ISTQB CTFL v4.0, *creating* concrete test data and organizing the test environment are Test Implementation activities.

---

## Validation Methodologies & Test Quality Metrics
* **Reference Pitch & Equivalence Partitioning:** Validated real-time pitch detection accuracy for the accessible 6-string tuning profile using an external tone generator, with Equivalence Partitioning applied to the target frequency spectrum.
* **UI & Configuration Resilience:** Verified interface responsiveness, notation display, and visual indicators across 3 test devices, including orientation stability (portrait vs. landscape) under Standard tuning.
* **Acoustic Environment & Hardware Adaptability:** Evaluated microphone stream pickup across four physical guitar types (steel-string acoustic, classical nylon, electric with amp off, electric with clean amp on) in both a controlled studio environment and a high-noise environment.
* **Multi-Device Coverage:** Maintained targeted test execution across 3 designated mobile devices, isolating deep UI component checks to specific hardware (Samsung S25 FE) while scaling layout and pitch-detection tests across the entire device pool.
* **Full Traceability:** Maintained a complete requirement-to-defect trace via the Requirements Traceability Matrix (`RTM-MOB-01`), including explicit tracking of which test conditions were descoped due to premium-tier access limits.

---

## Active Test Cycle Insights
* **Requirements Coverage:** 7 / 7 (100%)
* **Test Conditions Executed:** 11 / 25 (44%) — the remaining 14 were descoped due to premium-tier restrictions on the free-tier test account.
* **Pass Rate (executed conditions):** 9 / 11 (81.8%)
* **Open Defects:** 1 (Medium severity)
* **Closed/Rejected Defects:** 1 (Major severity, closed as a testing-methodology artifact — no software defect found)
* **Deployment Release Status:** Conditional release (free tier only) — see `TSR-MOB-01` for the full recommendation.

### Defects Summary
| Defect ID | Description | Severity | Priority | Status |
| :--- | :--- | :--- | :--- | :--- |
| `BUG-MOB-01` | Synthetic frequency matrix targets (E2, A2, D3) not detected for standard tuning | Major | High | Closed (Rejected/Invalid) |
| `BUG-MOB-02` | Bottom navigation bar truncates vertically when an interstitial ad renders in portrait mode | Medium | Medium | Open |

*Severity reflects technical/functional impact; Priority reflects business urgency to fix — per the [ISTQB Glossary](https://istqb-glossary.page/), these are assessed independently rather than interchangeably.*

---

## About the QA Professional
I am an **ISTQB® Certified Freelance Software Tester** specializing in end-to-end **User Acceptance Testing (UAT)** and digital quality assurance. I partner with businesses to validate and optimize high-impact digital products before market launch, ensuring seamless user experiences and functional reliability across multiple platforms.

### Core Areas of Expertise:
* **Mobile Application Testing:** Native Android app validation, physical device matrix testing, hardware-software interaction testing, and interruption handling.
* **E-Commerce Platforms:** End-to-end checkout flow validation, shopping cart state persistence, search engine routing parameters, and localized user journey verification.
* **Web Application QA:** Cross-browser compatibility validation, responsive web design (RWD) testing, BDD automation framework assembly, and functional regression testing.
