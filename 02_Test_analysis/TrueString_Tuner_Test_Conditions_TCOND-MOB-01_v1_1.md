# Test Analysis: Test Conditions

**Identifier:** TCOND-MOB-01  
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
| 1.0 | 2026-05-29 | Annalie Prinsloo | Baseline Test Conditions inventory. |
| 1.1 | 2026-09-07 | Annalie Prinsloo | Fictionalized; identifiers renamed `TC-xx` → `TCOND-xx` to distinguish test conditions from test cases; added document control header for consistency with the standard testware template. |

---

## 2. Purpose and Methodology
Test conditions in this document define exactly **what** must be verified during the User Acceptance Testing (UAT) phase for the TrueString Tuner App Beta (Version 6.0.9). These conditions are directly derived from the core functional scope, historical end-user review pain points (user stories), and the technical parameters established in the master Test Plan.

By analyzing the application specifications alongside user feedback, specific testing focus areas were extracted to target frequency accuracy limits, user interface layout stability under rotation, dynamic notation updates, and physical hardware microphone compatibility across different acoustic environments.

## 3. Test Conditions Inventory
| Condition ID | Source Requirement / Feature | Test Condition (What to Test) | Priority |
| :--- | :--- | :--- | :--- |
| **TCOND-PT-01** | `REQ-PT-01` (Synthetic Frequency Matrix) | Verify that the application algorithm accurately detects and identifies the 6 specific pitch frequencies for "Standard Tuning" using pure sound waves. | High |
| **TCOND-PT-02** | `REQ-PT-01` (Synthetic Frequency Matrix) | Verify that the application algorithm accurately detects and identifies the 6 specific pitch frequencies for "Drop D" tuning using pure sound waves. | High |
| **TCOND-PT-03** | `REQ-PT-01` (Synthetic Frequency Matrix) | Verify that the application algorithm accurately detects and identifies the 6 specific pitch frequencies for "Half-step down D#" tuning using pure sound waves. | High |
| **TCOND-PT-04** | `REQ-PT-01` (Synthetic Frequency Matrix) | Verify that the application algorithm accurately detects and identifies the 6 specific pitch frequencies for "DADGAD" tuning using pure sound waves. | Medium |
| **TCOND-PT-05** | `REQ-PT-01` (Synthetic Frequency Matrix) | Verify that the application algorithm accurately detects and identifies the 6 specific pitch frequencies for "Open G" tuning using pure sound waves. | Medium |
| **TCOND-PT-06** | `REQ-PT-01` (Synthetic Frequency Matrix) | Verify that the application algorithm accurately detects and identifies the 6 specific pitch frequencies for "Open D" tuning using pure sound waves. | Medium |
| **TCOND-PT-07** | `REQ-PT-01` (Synthetic Frequency Matrix) | Verify that the application algorithm accurately detects and identifies the 6 specific pitch frequencies for "D Standard" tuning using pure sound waves. | High |
| **TCOND-PT-08** | `REQ-PT-01` (Synthetic Frequency Matrix) | Verify that the application algorithm accurately detects and identifies the 6 specific pitch frequencies for "Drop C" tuning using pure sound waves. | High |
| **TCOND-PT-09** | `REQ-PT-01` (Synthetic Frequency Matrix) | Verify that the application algorithm accurately detects and identifies the 6 specific pitch frequencies for "Open E" tuning using pure sound waves. | Low |
| **TCOND-PT-10** | `REQ-PT-01` (Synthetic Frequency Matrix) | Verify that the application algorithm accurately detects and identifies the 6 specific pitch frequencies for "All Fourths" tuning using pure sound waves. | Low |
| **TCOND-PT-11** | `REQ-PT-01` (Synthetic Frequency Matrix) | Verify that the application algorithm accurately detects and identifies the 6 specific pitch frequencies for "Double Drop D" tuning using pure sound waves. | Low |
| **TCOND-PT-12** | `REQ-PT-01` (Synthetic Frequency Matrix) | Verify that the application algorithm accurately detects and identifies the 6 specific pitch frequencies for "Open G Alt 1" tuning using pure sound waves. | Low |
| **TCOND-UI-01** | `REQ-UI-01` (Note Profile Validation) | Verify that the target note naming conventions (e.g., E2, A2, D3, G3, B3 & E4) displayed on-screen exactly match the Standard tuning profile. | High |
| **TCOND-UI-02** | `REQ-UI-02` (Dashboard Layout) | Verify that text, alignment, and graphic elements on the dashboard remain clean, un-truncated, and readable when selecting the Standard tuning profile. | Medium |
| **TCOND-UI-03** | `REQ-UI-03` (Orientation Shift) | Verify that the active standard tuning dashboard scales smoothly and preserves text readability when rotated from portrait to landscape view. | High |
| **TCOND-UI-04** | `REQ-UI-03` (Orientation Shift) | Verify that rotating the device orientation does not cause application lockups, freezes, or calibration resets during active tuning. | High |
| **TCOND-UI-05** | `REQ-UI-04` (Accidental Notation) | Verify that toggling the flat (♭) format instantly translates sharp notes (e.g., D#2 shifts visually to E♭2) across all relevant tuning configurations. | Medium |
| **TCOND-UI-06** | `REQ-UI-05` (Dashboard Overlays) | Verify that turning on the numerical metric displays live, fluctuating frequency values in Hertz (Hz) matching the input sound. | High |
| **TCOND-UI-07** | `REQ-UI-05` (Dashboard Overlays) | Verify that the micro-increment Cent offset gauge displays visual indicators for sharp or flat deviations from the target note. | High |
| **TCOND-UI-08** | `REQ-UI-05` (Dashboard Overlays) | Verify that the display highlights the correct active graphic guitar string whenever a matching frequency is caught by the microphone. | High |
| **TCOND-UI-09** | `REQ-UI-05` (Dashboard Overlays) | Verify that the application converts traditional letter note notation into accurate Solfège naming formats (Do, Re, Mi) when the toggle is on. | Low |
| **TCOND-INT-01** | `REQ-INT-01` (Acoustic Capture) | Verify that a steel-string acoustic 6-string guitar can be picked up and processed cleanly in both a quiet studio and a high-noise environment. | High |
| **TCOND-INT-02** | `REQ-INT-01` (Acoustic Capture) | Verify that a nylon-string classical 6-string guitar can be picked up and processed cleanly in both a quiet studio and a high-noise environment. | High |
| **TCOND-INT-03** | `REQ-INT-01` (Acoustic Capture) | Verify that an electric 6-string guitar with the amplifier turned off can be picked up and processed cleanly in both testing environments. | Medium |
| **TCOND-INT-04** | `REQ-INT-01` (Acoustic Capture) | Verify that an electric 6-string guitar running a raw, unmodified clean tone through an active amplifier can be processed cleanly in both environments. | High |
