# Data and comparison notes

## Use the tool

[Open Electron Impact Lab](https://jaewonwashere.github.io/BEB-EI-Cross-Section/).

Select a target to see its model curves and available published measurement markers. The **Experimental data** tab gives references, dataset selection, CSV export, and manual overlay. The original NIST comparison graph is available below the main plot for targets with a retrieved measured comparison.

In **Ratios**, choose numerator and denominator molecules and cross-section types independently. Models can be compared at any incident energy in the selected range. Measurements default to exact common energies. Optional linear interpolation works only within measured ranges and is labeled as an estimate. Missing values and zero denominators give undefined ratios. Export the ratio CSV to preserve both cross sections and provenance.

Presets include NH3/H2O modeled totals, IPA m/z45/m/z43, and acetone/IPA sums of tabulated channels. A total-ionization ratio is not a mass-spectrometer signal ratio; abundance, electron-energy distribution, transmission, detector response, and background are not included.

## Supplied literature

- Prajapati, Vinodkumar, Limbachiya & Vinodkumar (2021), *Theoretical investigations of structural, spectroscopic and electron collision data of acetone*, Molecular Physics 119, e1948124, [DOI](https://doi.org/10.1080/00268976.2021.1948124). **Table 7**, journal p.13 / PDF p.14: B, U, N for 16 occupied acetone orbitals, RHF/cc-pVTZ, 32 electrons. Values were transcribed and visually verified. The standard Stone–Kim BEB equation is retained; source Eq.8 has apparent typographical inconsistencies.
- Vacher, Jorand, Blin-Simiand & Pasquiers (2008), *Partial ionization cross-sections of acetone and 2-butanone*, International Journal of Mass Spectrometry 273, 117–125, [DOI](https://doi.org/10.1016/j.ijms.2008.03.011). **Table 2**, p.121 / PDF p.5: acetone channels at 12, 25, 86 eV. Reported overall cross-section precision: 20% below 20 eV, 10% above 20 eV; energy accuracy ±0.5 eV. The authors normalized the 10–12 eV absolute scale to their own BEB result; the 12 eV values are therefore not an independent BEB validation.
- Vacher, Jorand, Blin-Simiand & Pasquiers (2006), *Partial ionisation cross-sections of 2-propanol and ethanal*, Chemical Physics 323, 587–594, [DOI](https://doi.org/10.1016/j.chemphys.2005.10.027). **Table 1**, p.590 / PDF p.4: IPA channels at 15, 50, 86 eV. Reported overall cross-section precision: 30% below 20 eV, 20% above 20 eV. The paper discusses possible low-energy normalization bias. It describes BEB calculations but does not list the orbital B/U table, so IPA remains experimental-data-only until actual orbital inputs are supplied.

The authors' overall uncertainty estimates are not explicitly one-standard-deviation errors, so the tool does not invent statistical error bars or propagated ratio confidence intervals. The table unit 10^-16 cm² equals Å² numerically. Table dashes remain missing entries. Selected-ion sums are arithmetic sums of reported entries, not new independent measurements. Missing channels make low-energy sums lower bounds; dividing two such sums does not generally yield a bound on their ratio.

## NIST experimental overlays

NIST SRD107's BEB HTML/ASCII download serves theoretical BEB cross sections; the measured comparisons are provided as raster graphs with cited references. Numerical marker overlays here are **approximate plot digitizations**, not original tabular experimental measurements.

- 40 molecular targets have 2,386 accepted digitized marker centers in this snapshot.
- 47 molecular targets have original NIST measured/theoretical comparison images bundled. Seven of these did not pass numerical digitization validation and therefore show the original graph instead of inferred numerical markers.
- The full NIST orbital snapshot has 89 molecules plus H/He. This update adds acetone and IPA for 93 selectable targets. Absence of a bundled overlay does not establish that no measurements exist in the literature.
- NIST graphs were retrieved sequentially with cache-busting because their generated image filenames can be overwritten during simultaneous requests.
- The log-energy mapping uses each graph form's stated energy bounds. The linear cross-section mapping is calibrated against NIST's own BEB ASCII trace. Calibration requires at least 85% agreement within two pixels among visible theoretical-trace columns; colored measurements can obscure portions of the theory line.
- Experimental colored components are matched to NIST's source legend. Theory-labeled references are excluded. Ambiguous/overlapping or clipped components are omitted. Their source graph remains visible for checking coverage.
- Each accepted point stores a nominal ±2-pixel digitization reading allowance in cross section and a corresponding relative energy allowance. These are reading allowances, not guaranteed bounds, experimental error bars, or confidence intervals. Experimental energy coordinates are consequently approximate and may not match across datasets.
- Original NIST plots may include theoretical comparison curves besides BEB. The tool does not recast those curves as measurements. The original plots do not change when the user's orbital inputs change.

Retrieval date: 19 October 2026. [NIST introduction](https://physics.nist.gov/PhysRefData/Ionization/intro.html). Per-dataset original experimental references and NIST graph URLs are included in the application and point CSV.

## Checks

All 93 target states pass numeric/input checks. Tests cover exact tabulated channel ratios, missing data, zero denominators, no extrapolation, optional interpolation, current edited inputs, published-marker clearing on target change, logarithmic plots with empty data ranges, and ratio/data/input export generation. Initial NH3/H2O BEB ratio at 22 eV is about 1.7127684; IPA m/z45/m/z43 at 50 eV is 6/0.94 = 6.3829787. Acetone/IPA selected-ion sums at 86 eV give 7.58/8.417 = 0.9005584.


## IPA total ionization: Hudson et al. (2003)
48 original tabulated total-ionization measurements from Table 1, p. 3164 (16–207 eV), DOI: https://doi.org/10.1039/B304456D. Units Å². Peak 10.24 Å² at 93 eV. Table 2 BEB peak: 9.48 Å², −7.4% versus experiment. No orbital binding/kinetic-energy table is provided. Total data are separate from Vacher selected-ion sums. Reproducibility better than ±2% is not absolute uncertainty; authors discuss a previously determined ±4% maximum instrument error, about 1.2 eV electron energy FWHM, and increased near-threshold uncertainty. Values transcribed from PDF text and visually checked against the 2-PrOH column. Available automatically on the main plot, in Ratios, and via Published points CSV.
