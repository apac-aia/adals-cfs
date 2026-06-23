# Vision simulation — speakers.apac-aia.org

Screenshots of the Call for Speakers landing page as it appears under simulated
vision conditions, captured by applying CSS / SVG colour-matrix filters over the
live page (the same technique browser dev-tools use).

| File | Condition |
|---|---|
| `amd-light.png` | Age-related macular degeneration (AMD) — blur + reduced contrast + an illustrative central scotoma, light mode |
| `amd-dark.png` | AMD, dark mode |
| `deuteranopia.png` | Green-weak colour vision deficiency |
| `protanopia.png` | Red-weak |
| `tritanopia.png` | Blue-yellow |
| `achromatopsia.png` | Total colour blindness (greyscale) |

## Takeaway

The page conveys meaning through **lightness contrast** (Navy vs Off-White,
near-black text) rather than **hue**, so every colour-deficiency view loses no
information — see `achromatopsia.png`, fully legible with zero colour. Large,
high-contrast headings and the Gold CTA stay readable under the AMD blur; the
central scotoma is a visual-field limit, not a design defect — large, clear
landmarks help users navigate around it.

## Notes

These are filter approximations. For a true gaze-tracked AMD scotoma, use the
**VisionSim** app (Braille Institute): open the page on a screen and point a phone
camera at it. Generated at a 1000px-wide viewport; not part of the published page.
