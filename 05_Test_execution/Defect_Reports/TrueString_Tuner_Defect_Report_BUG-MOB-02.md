## Defect Report: BUG-MOB-02

### 1. Summary information
* **Defect ID:** BUG-MOB-02
* **Title:** Bottom navigation bar truncates vertically when an interstitial advertisement renders in portrait mode.
* **Date Logged:** 2026-06-02
* **Reporter:** Annalie Prinsloo
* **Status:** New
* **Target Fix Version:** Version 6.0.10

### 2. Classifications
* **Defect Type:** Graphical User Interface (GUI) / Layout Error
* **Severity:** Medium
* **Priority:** Medium
* **Reproducibility:** Intermittent (device/aspect-ratio dependent — 2 of 3 devices affected)

### 3. Traceability & Environment
* **Build/Software Version:** Version 6.0.9 Beta
* **Hardware/Devices tested:**
  * Samsung Galaxy S25 (Android 16) – Failed
  * Samsung Galaxy S21 (Android 16) – Failed
  * Samsung Galaxy A53 (Android 16) – Passed
* **Traced To:** `TCOND-UI-03`
* **Test environment:** QA Environment (Free/Ad-Supported Tier)

### 4. Description & Steps to reproduce
* **Description:** When an advertisement container initializes and displays on the main tuner screen, the bottom navigation bar is compressed vertically. This layout distortion truncates approximately one-third (1/3) of the menu icons. The issue is specific to portrait orientation and isolates to the screen aspect ratios of the Samsung Galaxy S21 and S25. Severity was assessed as Medium because the layout degrades but navigation icons remain tappable, i.e., a functional workaround exists. Priority was assessed as Medium given the visual-quality impact on flagship devices, warranting a fix in the next sprint rather than an immediate hotfix.

* **Steps to Reproduce:**
  1. Launch the TrueString Tuner App (Ad-supported tier).
  2. Maintain the device in Portrait Mode and await the initialization/rendering of the interstitial advertisement in the center of the screen.
  3. Observe the layout behavior of the bottom navigation menu dynamically upon the ad display.

### 5. Test Results
* **Expected Result:** The UI layer scales responsively. The bottom navigation bar retains its original dimensions and asset visibility when advertisements render.
* **Actual Result:** The bottom navigation bar fails to scale dynamically. The rendering of the ad container forces the navigation bar downward, horizontally clipping/truncating the upper third of all menu icons on the Samsung S21 and S25. The layout renders correctly on the Samsung A53.

### 6. Evidence & Attachments
* **File Attached:**
  * `S21_GUI_Truncation.jpg` (Screen capture highlighting clipped navigation bar on Samsung S21)
  * `S25_GUI_Truncation.jpg` (Screen capture highlighting clipped navigation bar on Samsung S25)
* **Annotations:** The defect appears to be linked to high-density display scaling/viewport heights unique to the S21 and S25 flagship screens, as the mid-range A53 behaves normally.

### 7. Closure & Resolution
* **Status:** Open
* **Resolution Reason:** N/A (Investigation Pending)
* **Closing comment:** N/A
