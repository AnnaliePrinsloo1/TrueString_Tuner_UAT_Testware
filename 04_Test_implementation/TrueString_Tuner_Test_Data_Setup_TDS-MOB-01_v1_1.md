# Test Data Requirements & Environment Readiness

**Identifier:** TDS-MOB-01  
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
| 1.0 | 2026-05-29 | Annalie Prinsloo | Baseline test data and environment readiness specification. |
| 1.1 | 2026-09-07 | Annalie Prinsloo | Fictionalized; added document control header for consistency with the standard testware template. |

---

## 2. Test Environment Specification
* **Hardware/OS Requirements:**
  * 1 x Samsung Galaxy S25 FE (Target OS: Android 16) - Primary Node
  * 1 x Samsung Galaxy S21 FE (Target OS: Android 16) - Legacy Node
  * 1 x Samsung Galaxy A53 5G (Target OS: Android 16) - Mid-Range Node
  * 1 x Audio Generation Workstation (Laptop running native web audio synthesis engines)
* **Software/Browser Configurations:**
  * TrueString Tuner App Beta (Version 6.0.9, Build 2025-12-02) installed natively on all three target mobile nodes.
  * Google Chrome v124 (or higher) running on the laptop station to access the online synthesizer interface.
* **Network & Access Requirements:** Local Wi-Fi network connectivity is required on the mobile endpoints during setup to verify stable application initialization.

## 3. Environment Verification Checklist
* [ ] All 3 testing mobile nodes are charged to at least 50% battery capacity.
* [ ] Storage space verified on all 3 phones to ensure zero memory thrashing or installation caching constraints.
* [ ] Decibel Meter App (v3.0.1) is installed, calibrated, and operational on the primary Samsung S25 FE node.
* [ ] Laptop audio output speaker is clean and checked for physical hardware rattle or distortion across low frequencies (60 Hz–400 Hz).
* [ ] The 4 physical 6-string instrument assets are placed in the testing lab and checked for structural integrity (e.g., no loose tuning pegs or cracked bridges).

---

## 4. Test Data Inventory

### 4.1 Synthetic Audio Frequencies (Laptop Reference Master Table)
The following frequencies represent the exact text values to be manually inputted into the laptop generator interface across the 12 prioritized instrument tuning profiles:

| Profile Name | String 1 (Low) | String 2 | String 3 | String 4 | String 5 | String 6 (High) |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **Standard** | 82.41 Hz | 110.00 Hz | 146.83 Hz | 196.00 Hz | 246.94 Hz | 329.63 Hz |
| **Drop D** | 73.42 Hz | 110.00 Hz | 146.83 Hz | 196.00 Hz | 246.94 Hz | 329.63 Hz |
| **Half-step down D#** | 77.78 Hz | 103.83 Hz | 138.59 Hz | 185.00 Hz | 233.08 Hz | 311.13 Hz |
| **DADGAD** | 73.42 Hz | 110.00 Hz | 146.83 Hz | 196.00 Hz | 220.00 Hz | 293.66 Hz |
| **Open G** | 73.42 Hz | 98.00 Hz | 146.83 Hz | 196.00 Hz | 246.94 Hz | 293.66 Hz |
| **Open D** | 73.42 Hz | 110.00 Hz | 146.83 Hz | 185.00 Hz | 220.00 Hz | 293.66 Hz |
| **D Standard** | 73.42 Hz | 98.00 Hz | 130.81 Hz | 174.61 Hz | 220.00 Hz | 293.66 Hz |
| **Drop C** | 65.41 Hz | 98.00 Hz | 130.81 Hz | 174.61 Hz | 220.00 Hz | 293.66 Hz |
| **Open E** | 82.41 Hz | 123.47 Hz | 164.81 Hz | 207.65 Hz | 246.94 Hz | 329.63 Hz |
| **All Fourths** | 82.41 Hz | 110.00 Hz | 146.83 Hz | 196.00 Hz | 261.63 Hz | 349.23 Hz |
| **Double Drop D** | 73.42 Hz | 110.00 Hz | 146.83 Hz | 196.00 Hz | 246.94 Hz | 293.66 Hz |
| **Open G Alt 1** | 98.00 Hz | 123.47 Hz | 146.83 Hz | 196.00 Hz | 246.94 Hz | 293.66 Hz |

### 4.2 Cent Offset Boundary Values (Micro-Increment Verification Data)
For micro-increment needle validation during dashboard testing on the Samsung S25 FE, use these slight detune variances against a standard A4 reference tuning center (440.00 Hz):

| Data Set ID | Target Pitch State | Microtune Frequency Target | Expected Gauge Interface Behavior |
| :--- | :--- | :--- | :--- |
| **DATA-OFFSET-01** | Perfect Center | 440.00 Hz | Needle locks exactly at 0 Cent (Dead Center/Green Highlight) |
| **DATA-OFFSET-02** | Flat Deviation | 437.46 Hz | Needle registers exactly -10 Cents to the Left |
| **DATA-OFFSET-03** | Sharp Deviation | 442.54 Hz | Needle registers exactly +10 Cents to the Right |

### 4.3 Physical Instrument Registry
The following live physical structural parameters are allocated for real-world acoustic capture validation runs:

| Instrument ID | Physical Guitar Style | String Setup Matrix | Signal Output Path Configuration |
| :--- | :--- | :--- | :--- |
| **GUITAR-A-01** | Steel-String Acoustic | 6-String standard bronze wrap | Direct unamplified physical sound output |
| **GUITAR-C-01** | Nylon-String Classical | 6-String silver/nylon wrap | Direct unamplified physical sound output |
| **GUITAR-E-01** | Electric Solid-Body | 6-String nickel-wound wrap | Amplifier completely switched off (Acoustic string snap only) |
| **GUITAR-E-02** | Electric Solid-Body | 6-String nickel-wound wrap | Connected to Line 6 amplifier (Clean tone configuration active) |
