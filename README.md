# 🧬 Array-Based Nucleic Acid Identification Test

An interactive simulation of an array-based nucleic acid identification test for pathogen detection. Built for introductory microbiology courses as a digital replacement for paper-based lab activities.

**[Website](https://calebhendren.github.io/arraysim/)**

## Overview

Students work through the complete diagnostic protocol to identify pathogens in simulated patient blood samples:

1. **Place Probes** — Drag known DNA probe sequences onto a test platform (8 wells, including a negative control)
2. **Select Patient** — Choose from 4 color-coded patient samples, each containing a mix of pathogen and non-pathogen nucleic acids
3. **Denature** — Heat the sample to 95°C to separate double-stranded DNA into single strands (animated)
4. **Label DNA** — Attach fluorescent markers to each patient strand
5. **Base-Pair to Platform** — Manually match patient strands to complementary probe sequences using A↔T, A↔U, and G↔C pairing rules
6. **Wash & Read Results** — Correctly paired strands glow green; mismatches wash away. Compare results against the probe key to diagnose the patient

## Pathogen Panel

| Probe | Target | Nucleic Acid |
|-------|--------|--------------|
| 1 | Human DNA (Positive Control) | DNA |
| 2 | Hepatitis B Virus | DNA |
| 3 | West Nile Virus | RNA |
| 4 | *Plasmodium* (Malaria) | DNA |
| 5 | Hepatitis C Virus | RNA |
| 6 | *Treponema pallidum* (Syphilis) | DNA |
| 7 | Human Immunodeficiency Virus (HIV) | RNA |

RNA virus strands use **uracil (U)** instead of thymine (T), which students must account for when base-pairing.

## Patient Samples

| Sample | Infections |
|--------|-----------|
| Orange | Hepatitis B, Malaria |
| Blue | Syphilis, HIV |
| Green | Hepatitis C, Syphilis |
| Purple | Hepatitis B, West Nile, Hepatitis C |

All patients test positive for the Human DNA control. Each sample also contains non-binding "junk" strands that don't match any probe.

## Deployment

Single-file static site — no build step required.

1. Clone this repo
2. Go to **Settings → Pages → Source → Deploy from a branch**
3. Select `main` / `/ (root)` and save
4. Site will be live at `https://<username>.github.io/nucleic-acid-test/`

Or just open `index.html` in any browser.

## Technical Details

- Pure HTML + React 18 (loaded from CDN via Babel standalone)
- Drag-and-drop with full touch support (mobile scroll is locked during drag gestures)
- Responsive — larger wells and sequences on desktop, compact layout on mobile
- Sequence colors: A (blue), T (red), G (green), C (gold), U (purple)
- Zero dependencies, zero build tools, zero backend

## Pedagogical Notes

- The **denaturation step** reinforces that hybridization requires single-stranded nucleic acids
- Students must **manually base-pair** strands to probes rather than having the simulation auto-match, forcing them to practice complementarity rules
- The simulation notes that **hybridization is spontaneous in the real protocol** — students are doing manually what hydrogen bonding does automatically
- **RNA vs DNA distinction** is built into the activity: RNA viruses produce strands with U, requiring students to apply U↔A pairing
- The **negative control** (empty well) and **positive control** (human DNA, which every patient should match) mirror real diagnostic test design
- After washing, students see which matches they got right, which were wrong, and which they missed — then can retry or check the answer key

## License

MIT
