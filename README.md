# paper_JGR_Verger-Miralles_etal_2026
Codes to accompany "3D Reconstruction and Vertical Velocity Decomposition of an Intrathermocline Eddy from SWOT and Glider Observations"
-------------------------------------------------------------------------------------------------
Code to reproduce the reconstruction and the published figures of the manuscript from the 
glider, CTD, ADCP and SWOT L3 observations.

**Author:** Elisabet Verger-Miralles, IMEDEA (CSIC-UIB)

## What this repository does

`reconstruction_and_figures.ipynb` runs the full pipeline and produces Figures 1-7:

1. Builds an EOF (PCA) basis of glider dynamic height and projects its leading mode onto SWOT L3
   sea-surface height to reconstruct the 3-D density and geostrophic velocity field of the eddy.
2. Solves the QG omega equation (SSH filtered horizontally at FWHM = 8 km before differentiation,
   the paper's final configuration) to obtain the frontogenetic vertical velocity `w_fg`.
3. Decomposes the Q-vector forcing into natural-coordinate terms (curvature, confluence, shear,
   along-stream stretching) and inverts each term separately.
4. Validates the reconstruction against independent CTD (density) and ADCP (velocity) transects
   from Leg 1 / transect T6.
5. Samples the reconstruction along the glider Section-4 track and compares reconstructed `w`
   against independent tracer anomalies (oxygen, spiciness, chlorophyll) in isopycnal coordinates.

The notebook is organized in five parts: **(1)** libraries, **(2)** configuration (edit the data
paths here), **(3)** core functions, **(4)** data import and the reconstruction pipeline, and
**(5)** the seven figure-generation cells. Only the calculations required to reproduce the
published figures are included.

## Setup

Edit the paths in the **Configuration** cell (Section 2) to point at your local copy of the data,
then run all cells top to bottom. Figures are written to `figures/`.

## Figures produced

| # | Output file | Description |
|---|---|---|
| 1 | `figure1.png` | Regional ADT map + glider sigma0 section (context) |
| 2 | `figure2.png` | Q-vector natural-coordinate decomposition (schematic) |
| 3 | `figure3.png` | sigma0 / Rossby number / w_fg at 100, 300, 500 m |
| 4 | `figure4.png` | CTD density validation, transect T6 |
| 5 | `figure5.png` | ADCP velocity validation, transect T6 |
| 6 | `figure6.png` | Chl', O2', spice' and w_QG sections along the glider track |
| 7 | `figure7.png` | w_fg total / curvature / confluence maps |

## Citation

If you use this code, please cite the manuscript (see repository citation file / GitHub "Cite this
repository" once the paper is published).
