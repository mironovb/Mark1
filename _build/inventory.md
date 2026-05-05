# Source inventory

Repo: `github.com/mironovb/Mark1`. Build target: GitHub Pages at `https://mironovb.github.io/Mark1/`.

## drawings/ — 7 sheets

Title block on each: Berea College, drawn `mironovb`, dated 4/15/2026, scale 1:1 (or 2:1 / 3:1), DWG NO `BMironov_Tracked`.

| File | Sheet | Title | View content | Key dims (in) |
|------|-------|-------|--------------|---------------|
| `0.jpg` | 1 of 7 | Mark_Tracked_Vehicle | Isometric exploded; parts list 1 Hullside (×2), 2 centralcabin (×1), 3 bracket (×1), 4 barrod (×3), 5 wheeldrive (×4), 6 Gearassembly (×1) | full-assembly callouts |
| `1.jpg` | 2 of 7 | Hull (centralcabin) | Top, side w/ 135° angled cut, front, isometric of U-channel cabin | L 7.00 · W 4.28 · H 4.00 · t 0.11 · holes Ø0.30 at 2.39, 1.14, 2.00, 4.50; corner 1.50@135° |
| `2.jpg` | 3 of 7 | Hullside | Top, isometric, side (rhomboidal panel), edge | L 14.00 · H 5.00 · t 0.11 · 2 × Ø0.30 holes (one at .60/2.33 from corner, one in Ø1.00 corner pad, R1.00 fillet) |
| `3.jpg` | 4 of 7 | Rod (barrod) | Side, end (R.49 collar), isometric, top | L 7.28 · shaft Ø0.30 · collar 1.00 long, 1.17 from end, R.49 outer · thin tip .50 |
| `4.jpg` | 5 of 7 | Wheel (wheeldrive) | Front (Ø5.00, .20 tread teeth, 90° spacing, Ø0.30 bore), side (1.00 wide, tread bands), isometric | Ø5.00 · w 1.00 · bore Ø0.30 · 4 tread slots .20 wide @ 90° |
| `5.jpg` | 6 of 7 | Enginemount | Front, top, side, isometric of L-bracket with cylindrical motor cup | base 2.50 × 2.40 · motor bore Ø1.80 (R1.00 inner) · 2.00 wide · 2.10 cup interior · base t 0.15 · R.15/R.30 fillets · 2 mounting holes Ø0.30 |
| `6.jpg` | 7 of 7 | Bevelgears | Three views of crown + pinion bevel pair | ratio 23 : 54 (preset) · bores Ø0.30 |

## information/ — deck content

Source: `deck.pptx` extracted into:

- `manifest.json` — 14-slide map
- `theme.json` — slide is 13.33 × 7.5 in, white background
- `raw_text.md` — flattened deck content (the prose source of truth)
- `slides/slide_NN.json` — per-slide structured data (tables come from here, slides 6, 8, 11, 12)
- `notes/slide_NN.md` — speaker notes (all empty)
- `media/` — 28 images

### Tables held in slide JSONs

- `slide_06.json` — Parts inventory: 10 BOM rows (P-01…P-10 + EXTRAS P-07/P-08)
- `slide_08.json` — Dimension comparison: 11 rows (feature, part, design in, printed in, Δ, % error)
- `slide_11.json` — Mass by part group: 8 rows + total
- `slide_12.json` — Two tables: print time (7 rows + total) and assembly time by phase (7 rows + total)

### Media — what each image is

| File | What | Use |
|------|------|-----|
| `slide02_img2.jpg` | Mark I tank museum photo (real WWI vehicle) | inspirations / hero composite |
| `slide03_img1.gif` | 1916 cutaway diagram (silhouette, internal layout, 26'5" length) | inspirations |
| `slide03_img2.jpg` | Finished prototype, side view (red+blue tracks, "Bogdan" nameplate) | hero |
| `slide04_img1.jpg` | NEMA 17 SY42STH38 stepper (Pololu commercial photo) | drivetrain |
| `slide04_img2.jpg` | CAD render of bevel gear pair | drivetrain |
| `slide04_img3.png` | CAD bevel pinion + crown closeup | drivetrain |
| `slide04_img4.png` | Diagram differential (1 ring, 2 spider, 3 axle) | drivetrain |
| `slide04_img5.jpg` | Real photo of mounted differential with red drums | drivetrain |
| `slide04_img6.jpg` | Mark I interior photo — Hans de Regt 1997 watermark | EXCLUDE (third-party copyright) |
| `slide04_img7.jpg` | Labeled differential schematic (RING GEAR / DRIVE PINION / etc.) | drivetrain |
| `slide04_img8.png` | QR code | EXCLUDE (no value on web) |
| `slide04_img9.png` | Top view of vehicle showing electronics tub | composition / process |
| `slide05_img1.jpg` | CAD exploded view (the deck's exploded illustration) | visuals |
| `slide07_img1.png` | Hullside drawing (clean) | drawings gallery |
| `slide07_img2.png` | Isometric exploded with leader lines | drawings gallery |
| `slide07_img3.png` | (CAD view) | drawings gallery |
| `slide07_img4.png` | Front view of cabin from inside | drawings gallery |
| `slide07_img5.png` | (CAD view) | drawings gallery |
| `slide07_img6.png` | Hullside isometric | drawings gallery |
| `slide09_img1.jpg` | Bambu Studio slice — central cabin, 139.21 g, 3h7m print | process / filament |
| `slide09_img2.png` | Bambu Studio slice — hullside, 71.24 g, 1h27m | process |
| `slide09_img3.jpg` | Bench shot of mounted electronics (top view, breadboard + battery + driver) | process |
| `slide09_img4.jpg` | Side view of finished hull on floor | composition / hero alt |
| `slide10_img1.jpg` | Bambu Studio slice — wheel, 5.07 g, 9m20s | process |
| `slide10_img2.jpg` | Close-up of yellow drive wheel meshing with track teeth | process / drivetrain |
| `slide13_img1.jpg` | Tensioner close-up (the printed "ear" on one side) | reflection / limitations |

## Rubric → source mapping

| Pts | Criterion | Source files |
|-----|-----------|-------------|
| 7 | Design Journey & Concept | raw_text slides 1, 2, 3 + decisions written from concrete deck content (RWD→FWD, bevel→differential, tab→tighter fit are inferred from Limitations + Critical Dimensions content; need to clearly mark inference) |
| 5 | Inspirations & References | slide_03 (silhouette, intent, hands-on platform), slide_02_img2.jpg (museum photo), slide_03_img1.gif (cutaway), slide_14 references |
| 10 | Visual Documentation | slide_05_img1.jpg (exploded), drawings/0–6.jpg (7 sheets), CAD images from slide_04, slide_07, slide_09, slide_10 |
| 6 | Dimension Comparison & Accuracy | slide_08 table (11 rows, 4 critical fits in copy) |
| 6 | Print & Assembly Documentation | slide_12 tables (print + assembly), slide_09_img1/2, slide_10_img1, photos slide_03_img2, slide_13_img1, slide_09_img3/4, slide_10_img2 |
| 5 | Waste & Cost Analysis | slide_11 mass table + cost calculation + 3 zero-waste reasons |
| 7 | Reflection & Future | slide_13 (limitations + future improvements lists) — supplement with what didn't work, lessons learned (some inference required, mark clearly) |
| 4 | Portfolio Quality | structural — applies to all sections |

## Gaps / inferences flagged

- **Design journey iteration narrative**: slide deck does not show a clean RWD→FWD or bevel-reduction iteration sequence. The reflection slide names limitations (single motor differential, tensioner needed, PLA fatigue) which we can frame as design decisions reached through iteration. Need to write this section honestly — present as "design decisions and what they solved" rather than fabricated sketch-by-sketch journey.
- **What didn't work the first time**: slide_13 limitations are the source. The "wheel bores reamed by hand" claim in the original prompt is supported by the dimension table (Wheel bore D 6.00% error, Hullside shaft hole 4.67%, Bevel-gear bore 4.00%) and the slide_12 print-cleanup row "Reaming bores, deburring, light sanding" (2 h).
- **Drawing PNG previews**: source files are already JPGs — no PDF→PNG conversion needed. Use the JPGs directly.
- **Excluded files**: `slide04_img6.jpg` (Hans de Regt 1997 watermarked Mark I interior), `slide04_img8.png` (QR code with no web value), `.DS_Store` (macOS metadata).
