<p align="center">
  <img src="docs/logo.png" alt="Zirchron logo" height="140">
</p>

<h1 align="center">Zirchron</h1>

<p align="center">
  <strong>A desktop application for zircon petrochronology</strong><br>
  from raw analyses to publication-ready diagrams in a single, reproducible workflow.
</p>

Zirchron brings U–Pb geochronology, Lu–Hf isotope evolution, Ti-in-zircon
thermometry and trace-element / REE geochemistry together in one place, so a
zircon dataset can be reduced, filtered, interpreted and plotted without moving
between spreadsheets, statistical packages and drawing programs.

Developed at the **Laboratorio de Estudios Isotópicos (LEI)**, Instituto de
Geociencias, UNAM (Juriquilla, México).

> **Status: v1.0.1 — beta.** Zirchron is in active testing. If you find a bug or
> something behaves unexpectedly, please [open an issue](../../issues) — that
> feedback is exactly what this release is for.
>
> **If you are on v1.0, please update.** That build could not export figures to
> PDF, SVG or EPS, and the figure compositor could not draw any panel
> ([#1](../../issues/1)). Fixed in v1.0.1.

---

## Download and install

Zirchron runs on **Windows** and **macOS**. Go to the
[**Releases**](../../releases) page and download the file for your system:

| System | Download |
|---|---|
| **macOS** 13+, Apple Silicon | `Zirchron-1.0.1-arm64.dmg` |
| **macOS** 13+, Intel | `Zirchron-1.0.1-intel.dmg` |
| **Windows** 10 / 11 (64-bit) | `Zirchron-1.0.1-windows-setup.exe` |

Step-by-step instructions for both systems, with troubleshooting, are in
[INSTALL.md](INSTALL.md).

---

### Windows

**Requirements**

| | |
|---|---|
| **Windows** | 10 or 11, 64-bit |
| **Processor** | any 64-bit Intel or AMD |
| **Disk space** | ~350 MB |

**Steps**

1. Go to the [**Releases**](../../releases) page and download
   `Zirchron-1.0.1-windows-setup.exe`.
2. Double-click it. Windows will show a blue **"Windows protected your PC"**
   screen — click **More info**, then **Run anyway** (see below).
3. Follow the wizard: choose a language, accept the licence, confirm the
   folder. Zirchron installs into your user folder and **does not ask for an
   administrator password**. If you are an administrator and want it available
   to everyone on the computer, you can change that in the wizard.
4. Open Zirchron from the **Start menu** or from the desktop shortcut.

**First launch — the SmartScreen warning**

Windows shows that warning for any program not signed with a *code-signing
certificate*, which is a paid commercial service. It is not a detection of
anything harmful — SmartScreen is simply reporting that it does not recognise
the publisher. Click **More info** → **Run anyway**. You only need to do this
**once**, when you run the installer.

If your antivirus quarantines the installer, that is the same phenomenon: some
scanners flag any application bundled with PyInstaller. Restore the file and
add an exception if needed.

---

### macOS

**Requirements**

| | |
|---|---|
| **macOS** | 13 (Ventura) or later |
| **Processor** | Apple Silicon **or** Intel — a separate download for each |
| **Disk space** | ~500 MB |

**Which file do I need?** Open the  menu → *About This Mac* and read the line
just above the macOS version:

| That line says | Download |
|---|---|
| **Chip:** Apple M1 / M2 / M3 / M4 / M5 | `Zirchron-1.0.1-arm64.dmg` |
| **Processor:** Intel Core i5 / i7 / i9 / Xeon | `Zirchron-1.0.1-intel.dmg` |

Both files are the same Zirchron, compiled for a different processor. You do
not need Rosetta, and downloading the wrong one is harmless — macOS simply
refuses to open it.

**Steps**

1. Go to the [**Releases**](../../releases) page and download the `.dmg` that
   matches your processor (see the table above).
2. Double-click the downloaded file. A window opens showing the **Zirchron**
   icon next to a shortcut to your **Applications** folder.
3. **Drag the Zirchron icon onto the Applications folder.** That is the whole
   installation — macOS apps are self-contained, there is no installer wizard.
4. Eject the disk image (click the ⏏ symbol next to *Zirchron 1.0.1* in the
   Finder sidebar). You can delete the `.dmg` afterwards.
5. Open Zirchron from **Launchpad**, from the Applications folder, or via
   Spotlight (⌘ Space → "Zirchron").

**First launch — the security warning**

The first time you open Zirchron, macOS will refuse and show a message saying
it *"cannot verify that this app is free of malware"*. This is expected:
Zirchron is not notarized by Apple (notarization requires a paid Apple Developer
account). The app is not doing anything to your system — it simply is not
registered with Apple.

To allow it:

1. Open  → **System Settings** → **Privacy & Security**.
2. Scroll down. Near the bottom you will see a line saying *"Zirchron was
   blocked to protect your Mac"*.
3. Click **Open Anyway**, then confirm with **Open**.

You only ever need to do this **once**. After that Zirchron opens normally,
and you can keep it in your Dock.

A step-by-step version of these instructions, with troubleshooting, is in
[INSTALL.md](INSTALL.md).

---

## What Zirchron does

**U–Pb geochronology**
Wetherill and Tera–Wasserburg concordia, York discordia (Models 1–3 with full
error propagation), concordia ages, weighted means with MSWD / P(MSWD), and
configurable discordance, precision and outlier filtering. Best-age selection
follows the Spencer et al. (2016) cutoff convention. Includes the Halpin method
for isolating the oldest coherent cluster in Pb-loss–affected populations.

**Lu–Hf isotopes**
εHf(0), εHf(t), initial ¹⁷⁶Hf/¹⁷⁷Hf, single-stage and two-stage crustal model
ages (T_DM, T_DM^C), with CHUR and depleted-mantle reservoirs plotted as
evolution curves.

**Ti-in-zircon thermometry**
Ferry & Watson (2007) and the pressure-corrected Crisp et al. (2023)
calibrations, with analytical and population uncertainties.

**Trace elements and REE**
Chondrite-normalized multi-element (spider) patterns with three normalization
references, Eu/Eu\* and Ce/Ce\* anomalies, and tecto-magmatic discrimination
diagrams after Grimes et al. (2015).

**Detrital and provenance tools**
KDE and PDP age distributions, stacked ridgeline views, automatic peak
detection, and cross-correlation similarity matrices between samples.

**Figure production**
Every diagram is editable in place — draggable legends and labels, freehand
annotations, shapes, zoom insets, per-view axis limits and frozen framing.
Diagrams can be assembled into multi-panel figures in the built-in compositor
and exported as vector PDF or SVG.

**Data handling**
Excel import (auto-detects header rows and splits stacked samples), multi-sheet
`.xlsx` export at full precision, project files (`.zirchron`), analysis sets
with per-sample scope, and an automatic data-QA pass that flags physically
impossible inputs.

---

## Getting started

Zirchron ships with its own documentation, available from the **Help** menu:

- **User guide (PDF)** — an illustrated walkthrough of the whole workflow,
  panel by panel.
- **Theory & methods (PDF)** — the mathematics and geometry behind every
  calculation and diagram, with the equations as implemented and their
  references.
- **Reference values & constants** — the decay constants, reservoir parameters
  and normalization values in use.

A **Methods & references** generator (menu *Export*) drafts a methods paragraph
tailored to your project's actual settings, with the matching citation list —
a starting point for the methods section of a manuscript.

The workflow, in short: create a project → choose which variables you work with
→ paste or import your data → press **Calculate** → plot and compose.

Projects are saved as `.zirchron` files, and double-clicking one opens it
directly — on Windows as soon as the installer finishes, on macOS once Zirchron
has been opened at least one time.

---

## Reporting bugs

Please [open an issue](../../issues). The most useful reports include:

- what you did, what you expected, and what happened instead;
- a screenshot if the problem is visual;
- your system — Windows 10 or 11, or your macOS version and Mac model;
- if the problem involves specific data, a `.zirchron` file that reproduces it
  (only if you are comfortable sharing it).

---

## Algorithms

All calculations are implemented **from the published equations**. Key
references: Jaffey et al. (1971);
Ludwig (1998); York et al. (2004); Wendt & Carl (1991); Spencer & Kirkland
(2015); Spencer et al. (2016); Söderlund et al. (2004); Bouvier et al. (2008);
Griffin et al. (2002); Ferry & Watson (2007); Crisp et al. (2023); Sun &
McDonough (1989); Boynton (1984); McDonough & Sun (1995); Grimes et al. (2015);
Silverman (1986); Dickinson & Gehrels (2009); Halpin et al. (2011). Statistical
conventions follow those established by IsoplotR (Vermeesch 2018).

The complete formulation of every routine is documented in *Help → Theory &
methods*.

---

## Citation

If Zirchron contributes to published work, please cite it. A citation entry is
available in the application under *About → How to cite*. A formal reference
will be added here once the accompanying publication is available.

---

## License

**Free for academic and research use.** Commercial use requires a separate
license — please contact the author. See [LICENSE](LICENSE).

---

## Author

**Dr. Guillermo Espejo Bautista**
Laboratorio de Estudios Isotópicos (LEI) · Instituto de Geociencias
Universidad Nacional Autónoma de México, Juriquilla · México

ORCID [0000-0001-9206-5108](https://orcid.org/0000-0001-9206-5108) ·
[gespejo@geociencias.unam.mx](mailto:gespejo@geociencias.unam.mx)
