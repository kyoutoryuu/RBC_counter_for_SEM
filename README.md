# RBC_counter_for_SEM
ImageJ/Fiji macro for semi-automated quantification of red blood cell density in SEM micrographs of blood clots.



This repository contains the ImageJ/Fiji macro used for semi-automated red blood cell (RBC) counting and RBC density estimation in scanning electron microscopy (SEM) images for the published article:

Yetisgin, A. A., Ozogul, B., Akar, U., Mercimek, R., Sarraf, S. S., Elverdi, T., Amani, E., Grishenkov, D., Koşar, A., and Ghorbani, M.  
**Thrombolytic potential of the “hydrodynamic cavitation on a chip” concept: insights into clot degradation.**  
*Lab on a Chip*, 2025. DOI: 10.1039/d5lc00482a.

## Purpose

The macro was developed to quantify RBC density in SEM micrographs of blood clots after hydrodynamic cavitation and acoustic cavitation treatments.

The workflow performs:

1. Image conversion to 16-bit.
2. Contrast enhancement.
3. Gaussian blurring.
4. Image inversion.
5. Otsu thresholding.
6. Binary mask conversion.
7. Watershed separation of touching RBC-like objects.
8. Particle analysis using defined size and circularity thresholds.
9. RBC count and RBC density calculation.

## Intended use

This macro is intended for SEM images in which RBCs can be segmented from the clot/background using intensity thresholding and particle-shape filtering.

It was used for RBC density analysis in SEM micrographs associated with the published study above. Users should re-optimize and validate the parameters for their own SEM images, magnifications, substrates, and contrast conditions.

## Requirements

- Fiji or ImageJ
- SEM image opened in ImageJ/Fiji
- Known pixel-to-micrometre calibration, either from the SEM metadata or from the image scale bar

## How to run

1. Open the SEM image in Fiji/ImageJ.
2. Open `RBC_SEM_counter.ijm`.
3. Adjust the user-defined parameters at the top of the macro.
4. Run the macro.
5. Inspect the particle outline output.
6. Record the RBC count and RBC density.

## Important calibration note

The default calibration in the macro is:

```javascript
scale_bar_length_um = 2.0;
scale_bar_pixels = 37;
