# BEB-EI-Cross-Section

This repo uses the Binary-Encounter-Bethe model to predict ionization cross sections for molecules in the context of mass spectrometry.

## [Open the live comparison tool](https://jaewonwashere.github.io/BEB-EI-Cross-Section/)

No installation is required. You can also download `index.html` and open it offline.

- Compare BEB and BED where the required continuum inputs are available.
- Compare cross-section ratios between molecules or measured ion channels in the **Ratios** tab.
- Select a supported NIST molecule to load approximate experimental-marker overlays automatically, with the original NIST plot and citations available for checking.
- Explore acetone's published orbital inputs and acetone/IPA tabulated fragment cross sections. IPA is experimental-data-only until orbital inputs are supplied.
- Import custom molecular orbitals and measured data; export plots, cross sections, ratios, and saved inputs.

[Data sources, citations, precision, and limitations](DATA_NOTES.md)

The model predicts total direct ionization. Total-ionization ratios do not directly predict mass-spectrometer signal ratios. NIST measurement markers are approximate plot digitizations, not original tabulated experimental values. Details and source references are shown in the application.
