This Python script calculates and visualizes the spatial overlap between the conduction band minimum (CBM) and valence band maximum (VBM) planar-averaged charge densities obtained from DFT simulations.

Main Steps:

Data Input:

The code reads two planar average files:

PLANAR_AVERAGE_cbm1.dat → CBM charge density.

PLANAR_AVERAGE_vbm1.dat → VBM charge density.

Each file must contain two columns: position along the z-axis (Å) and the corresponding charge density.

Data Alignment:

The VBM data is interpolated onto the CBM z-grid to ensure both arrays share the same spatial resolution before integration.

Normalization:

Both CBM and VBM charge densities are normalized using Simpson’s integration so that the total area under each curve equals 1.

Overlap Integral:

Computes the wavefunction overlap integral

𝑂
=
∫
𝜌
𝐶
𝐵
𝑀
(
𝑧
)
𝜌
𝑉
𝐵
𝑀
(
𝑧
)
 
𝑑
𝑧
O=∫ρ
CBM
	​

(z)ρ
VBM
	​

(z)dz

which quantifies the spatial correlation between CBM and VBM states.

The overlap is expressed as both a relative value and a percentage.

Centroid and Spread Calculation:

Determines the centroid (mean position) and spatial spread (standard deviation) of each density distribution.

Calculates centroid separation (Δz) to quantify charge separation across the interface or slab.

Visualization:

Plots normalized CBM and VBM densities versus z-position.

Highlights overlap regions and centroids with color-coded lines.

Displays key metrics (overlap %, σ, Δz) directly on the plot.

Saves a high-resolution image CBM1_VBM1_overlap.png.

Output:

Prints key quantitative metrics to the console:

Overlap integral (absolute and %)

Centroids and spreads of CBM and VBM

Centroid separation

Saves raw CBM and VBM planar-average data to text files for further reference:

PLANAR_AVERAGE_cbm1_raw.dat

PLANAR_AVERAGE_vbm1_raw.dat

Purpose:

This script provides a quantitative measure of electron–hole spatial separation and wavefunction overlap — useful for analyzing band alignment, interface coupling, and charge-transfer efficiency in semiconductor heterostructures such as perovskite/organic interfaces.
