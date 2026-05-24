# Binek-Porosity
Freeware image analysis for porosity, hardness (Vickers/Knoop), length/area measurements, and ROI management. Supports multi‑method binarization, live camera capture, Word/Excel reports, and full UI customization. Ideal for materials science and industrial inspection.
# Coating Analyzer Binek 2.4 Beta

**Advanced material image analysis tool**  
– porosity, length measurements, hardness, Word/Excel reports.

---

## Table of Contents
- [Description](#description)
- [System Requirements](#system-requirements)
- [Running the Application](#running-the-application)
- [Basic Workflow](#basic-workflow)
- [Main Features](#main-features)
- [Configuration Files and Logs](#configuration-files-and-logs)
- [Keyboard Shortcuts](#keyboard-shortcuts)
- [Troubleshooting](#troubleshooting)
- [Contact and Support](#contact-and-support)

---

## Description
Coating Analyzer Binek 2.4 Beta is an application designed for image analysis from microscopes, digital cameras, and other sources. It enables:

- Calculation of porosity (pore area fraction) on the entire image or selected regions (ROIs).
- Advanced binarization methods: Otsu, Multi‑Otsu, adaptive, manual thresholding, voting fusion, watershed, and others.
- Linear (length) and area measurements.
- Hardness measurement using the Vickers or Knoop method.
- Scale calibration (µm, mm, inches).
- Export of results to Word (.docx) and Excel (.xlsx) reports with charts and images.
- Live USB camera preview and frame capture.

The application runs as a standalone executable – no Python installation or additional libraries are required.

---

## System Requirements
- **Operating system**: Windows 10 / 11 (64-bit)
- **Processor**: any (2 cores recommended)
- **RAM**: minimum 4 GB (8 GB recommended)
- **Graphics card**: any with OpenGL support (for image display)
- **USB camera (optional)**: DirectShow compatible
- **Hard disk**: approx. 200 MB free space (for the program and temporary files)

---

## Running the Application
1. Download the `CoatingAnalyzer.exe` file (or the appropriate version).
2. Place it in any folder (e.g., `C:\Program Files\CoatingAnalyzer\`).
3. Run by double‑clicking (administrator rights are not required unless saving files in a system directory).
4. On first launch, the program will create configuration files in its working directory.

> **Note:** If Windows displays a warning about an unknown publisher, click “More info” and then “Run anyway”.

---

## Basic Workflow
1. **Load an image** – via `File → Open Image`, from the `Clipboard` tab, or from a camera (`Camera` → `Start` → `Capture Image`).
2. **Perform calibration** (`Calibration` tab): draw a line over a known distance, enter the actual length, and click `Calibrate`.
3. **Adjust the image** (`Adjustments` tab): brightness, contrast, gamma, filters.
4. **Select a binarization method** (`Porosity` tab) – e.g., `Otsu` or `Manual Range`.
5. Click `Whole Image` – it will compute porosity and display the binary and fusion images.
6. **(Optional) Create ROIs** – press `New ROI`, draw a shape, click `Finish ROI`, then `Selected ROI`.
7. **Perform linear measurements** (`Thickness` tab) – enable `Measure Length`, drag a line.
8. **Save results** – Word/Excel reports, images (buttons in the `Porosity` tab).

---

## Main Features

| Area                | Description                                                                                             |
|---------------------|---------------------------------------------------------------------------------------------------------|
| **Porosity**        | 12 binarization methods, porosity calculation, pore size distribution (histograms).                    |
| **ROI**             | Rectangle, ellipse, polygon, freeform – up to 5 regions.                                                |
| **Length measurements** | Draw lines, automatic conversion to µm/mm/inches, statistics, table.                                   |
| **Area measurements**   | Automatic for ROIs – available in reports.                                                             |
| **Hardness**        | Vickers and Knoop, any load, draw diagonals, measurement history.                                      |
| **Calibration**     | Manual line + known length, store up to 5 calibrations, save/load JSON.                                 |
| **Scale bar**       | Automatically added to images (requires calibration).                                                   |
| **Camera**          | Live preview, frame capture (DirectShow).                                                              |
| **Reports**         | Word (with charts and images) and Excel (tables) – select sections, background generation.              |
| **UI settings**     | Colors, fonts, line thickness, legend scale – customizable.                                            |

---

## Configuration Files and Logs
The program saves the following files in its working directory (the folder from which it was launched):

- `settings.ini` – UI settings, last used binarization parameters, calibration.
- `session.json` – last state (ROIs, measurements, diagonals, scale bar, calibration line).
- `multi_calibration.json` – list of saved calibrations (max 5).
- `material_analyzer.log` – event and error log (useful when reporting issues).

> **Tip:** To clear all settings and start fresh, delete (or move) these files.

---

## Keyboard Shortcuts

| Shortcut          | Action                                                       |
|-------------------|--------------------------------------------------------------|
| `Ctrl+O`          | Open image (file) – adds to clipboard and loads.            |
| `Ctrl+S`          | Save image from the current tab.                            |
| `Ctrl+D`          | Open porosity details window.                               |
| `Ctrl+M`          | Toggle length measurement drawing mode.                     |
| `Ctrl+R`          | Create a new ROI.                                           |
| `Ctrl+Z`          | Undo the last measurement (length or area).                 |
| `Ctrl + mouse wheel` | Zoom in the active view.                                   |
| `Ctrl + LMB + drag`  | Pan the image after zooming.                               |

---

## Troubleshooting

**The program does not start (no response / system error)**
- Make sure Windows is up‑to‑date (especially the VC++ Redistributable libraries).
- Run as administrator (right‑click → “Run as administrator”).
- Check the system event log or the `material_analyzer.log` file.

**Cannot open the camera**
- Ensure the camera is not being used by another application (e.g., Teams, Zoom).
- Try a different camera index (drop‑down list after clicking `Refresh`).
- If the camera requires a non‑DirectShow driver, the program may not detect it.

**Porosity results are incorrect**
- Check the calibration – is `px/µm` correct?
- Try a different binarization method (e.g., `Manual Range` with visual threshold preview).
- Make sure the image has sufficient contrast (adjust using the `Adjustments` tab).

**Word report does not generate**
- Verify that you have write permissions for the selected folder.
- Try saving an Excel report – if that works, the issue may be related to the `python-docx` library (in the `.exe` version it should be built‑in). Report the problem.

**The application closed unexpectedly**
- Locate the `material_analyzer.log` file and send it to support.

---

## Contact and Support
**Author:** Marek Goral  
**E‑mail:** `mgoral@hub.pl`

For questions, bug reports, or suggestions, please contact us by email. Attach the following:
- a short description of the problem,
- the log file `material_analyzer.log`,
- (if applicable) the input image and the parameters used.

Thank you for using Coating Analyzer Binek 2.4 Beta.
