# Test Implementation: Test Procedures & Execution Scripts

**Identifier:** TPROC-MOB-01  
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
| 1.0 | 2026-05-29 | Annalie Prinsloo | Baseline test procedures. |
| 1.1 | 2026-09-07 | Annalie Prinsloo | Fictionalized; Procedure IDs renamed `PROC-xx` → `TPROC-xx`; referenced Test Case IDs updated to the `TC-xx` convention; added document control header. |

---

## 2. Execution Order & Sequencing Notes
To optimize lab utilization and maintain strict data integrity, procedures must be executed in the following chronological sequence:
1. **`TPROC-PT-01` (Synthetic Baseline):** Establishes that the underlying detection algorithm works across all 3 devices before human variables are introduced.
2. **`TPROC-UI-01` to `TPROC-UI-04` (Interface Verification):** Done entirely on the `Samsung S25 FE` to verify screen logic, overlays, and stability under rotation.
3. **`TPROC-INT-01` (Physical Field Testing):** Executed last as it involves handling physical instruments and shifting between controlled studio and high-noise environments.

---

## 3. Test Procedure Suite

### TPROC-PT-01: Synthetic 12-Tuning Reference Sweep
* **Associated Test Cases:** `TC-PT-01`
* **Environmental Setup Steps:**
  1. Place the target phone (`Samsung S25 FE`, `Samsung S21 FE`, or `Samsung A53 5G`) exactly 30cm away from the laptop audio output speaker.
  2. Launch the Decibel Meter App (v3.0.1) on the control node to verify the room noise floor is between 10 dB and 30 dB.
  3. Open `https://szynalski.com/tone-generator/` on the laptop web browser. Set the wave shape to "Sine Wave".

#### Execution Steps:
| Step # | Action Description | Target Data/Input | Expected System Response |
| :--- | :--- | :--- | :--- |
| 1 | Launch the TrueString Tuner App on the target device. | App Launch | App initializes smoothly without crashes or freezing. |
| 2 | Open the App's Tuning Selection Menu and select "Standard Tuning". | Standard Profile Selection | Dashboard note layout updates to display: E2, A2, D3, G3, B3, E4. |
| 3 | On the laptop generator, type in `82.41 Hz` and click "Play" for 3 seconds. | 82.41 Hz (E2 Wave) | The app registers the tone and centers on the E2 indicator. |
| 4 | Successively play remaining frequencies from the Standard Tuning row of the Test Data table (`TDS-MOB-01`, Section 4.1). | 110.00 Hz, 146.83 Hz, 196.00 Hz, 246.94 Hz, 329.63 Hz | App correctly registers each matching note string. |
| 5 | Cycle through the remaining 11 tuning layouts in the app menu, repeating the tone generator matching process for each profile. | All frequency values detailed in `TDS-MOB-01`, Section 4.1 | The app accurately detects every target reference frequency across all 12 tuning profiles. |

---

### TPROC-UI-01: Tuning Note Profile & Layout Consistency
* **Associated Test Cases:** `TC-UI-01`
* **Environmental Setup Steps:** Restrict testing exclusively to the **Samsung Galaxy S25 FE**. Ensure the testing environment is well-lit for physical UI assessment.

#### Execution Steps:
| Step # | Action Description | Target Data/Input | Expected System Response |
| :--- | :--- | :--- | :--- |
| 1 | Launch the app and enter the profile selection carousel. | Menu Interaction | The menu renders clearly with readable text labels. |
| 2 | Select the Standard tuning profile from the Setting menu under Tuning. | Profile Selection Matrix | The dashboard notes immediately change to reflect the selected layout. |
| 3 | Closely inspect textual labels and boundary containers during changes. | Visual Alignment Scan | Note indicators render perfectly with zero text overlapping, truncation, or layout clipping. |

---

### TPROC-UI-02: Portrait vs Landscape Rotation Stress Suite
* **Associated Test Cases:** `TC-UI-02`
* **Environmental Setup Steps:** Prepare all 3 testing endpoints (`Samsung S25 FE`, `Samsung S21 FE`, `Samsung A53 5G`). Ensure device system auto-rotate properties are enabled.

#### Execution Steps:
| Step # | Action Description | Target Data/Input | Expected System Response |
| :--- | :--- | :--- | :--- |
| 1 | Launch the app in default Portrait mode and select "Standard Tuning". | Default View State | Main dashboard displays in vertical alignment. |
| 2 | Generate a continuous `196.00 Hz` tone from the laptop speaker. | 196.00 Hz (G3 Wave) | The app microphone actively tracks and registers the incoming pitch. |
| 3 | Physically rotate the device 90 degrees to activate Landscape view while the tone is playing. | Hardware Rotation Input | The UI scales fluidly to landscape format. The pitch readout remains uninterrupted. |
| 4 | Rapidly rotate the device back and forth between portrait and landscape modes 5 consecutive times. | Stress Rotation Input | The application adjusts layout parameters securely. No crashes, UI freezing, or calibration resets occur. |

---

### TPROC-UI-03: Accidental Notation Format Conversion
* **Associated Test Cases:** `TC-UI-03`
* **Environmental Setup Steps:** Restrict testing to the **Samsung Galaxy S25 FE**.

#### Execution Steps:
| Step # | Action Description | Target Data/Input | Expected System Response |
| :--- | :--- | :--- | :--- |
| 1 | Launch the app and select the "Half-step down D#" tuning profile. | Profile Selection Menu | On-screen notes display as: D#2, G#2, C#3, F#3, A#3, D#4. |
| 2 | Navigate to App Settings and locate the Notation configuration panel. | Menu Navigation | The notation setting displays "Sharp (#)" as the current default. |
| 3 | Tap the toggle switch to change the notation selection to Flat (♭). | Format Toggle Selection | Settings update instantly. |
| 4 | Return to the main tuning dashboard and evaluate the displayed notes. | Main View Inspection | The dashboard layout converts all sharp labels to flats: E♭2, A♭2, D♭3, G♭3, B♭3, E♭4. |

---

### TPROC-UI-04: Dashboard Metric Overlay Configuration
* **Associated Test Cases:** `TC-UI-04`
* **Environmental Setup Steps:** Restrict testing to the **Samsung Galaxy S25 FE**.

#### Execution Steps:
| Step # | Action Description | Target Data/Input | Expected System Response |
| :--- | :--- | :--- | :--- |
| 1 | On the main dashboard, locate and switch on the live frequency metric toggle. | Hz Metric Toggle | A numerical readout panel appears on the dashboard UI. |
| 2 | Generate a pure `146.83 Hz` tone from the tone generator tool. | 146.83 Hz (D3 Wave) | The numerical overlay shows a stable reading fluctuating right at `146.8 Hz`. |
| 3 | Slightly shift the laptop generator slider up to `149.00 Hz`. | Off-Pitch Freq Shift | The Cent offset needle shifts visually to the right, showing a "Sharp" error indicator. |
| 4 | Verify the graphical fretboard/string section of the application window. | String Graphic Scan | The 3rd string line on the visual display lights up/highlights as active. |
| 5 | Navigate to layout options and activate the "Solfège" notation toggle. | Solfège Format Switch | Traditional letter characters swap out. The notes display cleanly as: Do, Re, Mi, Fa, Sol, La. |

---

### TPROC-INT-01: Empirical Physical Instrument Acoustic Capture
* **Associated Test Cases:** `TC-INT-01`
* **Environmental Setup Steps:** Restrict testing to the **Samsung Galaxy S25 FE** configured to "Standard Tuning". Prepare the 4 physical 6-string guitar assets.

#### Execution Steps:
| Step # | Action Description | Target Data/Input | Expected System Response |
| :--- | :--- | :--- | :--- |
| 1 | Position the tester inside the quiet studio booth (verified at 10-30 dB). | Controlled Sound Booth | Ambient sound readings are low and stable. |
| 2 | Take the physical Steel-String Acoustic Guitar and pluck each string cleanly. | Live Acoustic Vibrations | The phone microphone captures each pluck. Frequencies register clearly on the dashboard. |
| 3 | Repeat step 2 sequentially using the Nylon Classical, Unamplified Electric, and Clean-Amplified Electric. | 3 Remaining Guitar Assets | The app identifies the pitch lines for all styles, including the quiet unamplified electric strings. |
| 4 | Move the phone and testing gear into the high-noise environment room. | Noisy Testing Zone | Background sound chatter simulation is active. |
| 5 | Pluck the 6 strings of all 4 physical guitars again under high background noise conditions. | Cross-Environment Matrix | The application algorithm isolates the close-range guitar vibrations, registering the pitch without getting blocked by background chatter. |
