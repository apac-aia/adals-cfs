# Vision simulation — speakers.apac-aia.org

Screenshots of the Call for Speakers landing page under simulated vision
conditions, in **light and dark mode**, captured by applying CSS / SVG
colour-matrix filters over the live page. Browse them as a gallery in
**`index.html`** (open the folder URL); click any image for full size.

12 images = 6 conditions × 2 modes (`-light` / `-dark`):

| Condition | Files |
|---|---|
| Normal (no filter) | `normal-light.png` / `normal-dark.png` |
| AMD — macular degeneration (blur + reduced contrast + central scotoma) | `amd-light.png` / `amd-dark.png` |
| Deuteranopia (green-weak) | `deuteranopia-*.png` |
| Protanopia (red-weak) | `protanopia-*.png` |
| Tritanopia (blue-yellow) | `tritanopia-*.png` |
| Achromatopsia (total colour blindness) | `achromatopsia-*.png` |

## Takeaway

The page conveys meaning by **lightness contrast** (Navy vs Off-White, near-black
text), not by hue — so every colour-deficiency view loses no information (see
`achromatopsia-*`, fully legible with zero colour). Large, high-contrast headings
and the Gold CTA stay readable under the AMD blur; the central scotoma is a
visual-field limit, not a design defect.

## Notes

Filter approximations. For a true gaze-tracked AMD scotoma, use the **VisionSim**
app (open the page on a screen, point a phone camera at it). Captured at a
1000px-wide viewport; not part of the published page.
