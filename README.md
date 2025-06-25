# Autofluorescence Cyto 2025

<img src="https://github.com/DavidRach/Autofluorescence_Cyto2025/blob/main/AutofluorescencePoster.png" >

This repository is for our '“Are these autofluorescences in the room with us right now?” Quantifying impact of autofluorescence variation on unmixing' poster. It contains the data and R code needed to hopefully reproduce our analysis and figures, as well as the .svg files used to create the figures in Inkscape.

## Organization

The .csv files for the respective analyses are stored in the data folder, from which they can be accessed by the code. The code is contained within the Quarto Markdown (.qmd) files named after the respective figure. The .svg files can be opened with Inkscape to access the Figure assembly layout. 

## Luciernaga

Please note, you will need to install [Luciernaga](https://github.com/DavidRach/Luciernaga) to reproduce some of the Figures. The package version utilized for running of the code in this manuscript was the 0.99.4 release. 

## Raw Data

Due to size constraints, this repository only contains the processed data files derrived from our original .fcs files. The actual .fcs files are being uploaded to ImmPort (SDY3080) and will be available at the next release cycle. 

## Abstract

**“Are these autofluorescences in the room with us right now?” Quantifying impact of autofluorescence variation on unmixing**

David Rach1, Kirsten E. Lyke2, Cristiana Cairo3

1 Molecular Microbiology and Immunology Graduate Program, University of Maryland School of Medicine, Baltimore, USA 2 Center for Vaccine Development and Global Health, University of Maryland School of Medicine, Baltimore, USA 3 Department of Microbiology and Immunology, University of Maryland School of Medicine, Baltimore, MD, United States.

Proper unmixing controls (both single-color and unstained) are critical for successful resolution of similar fluorophores in spectral flow cytometry (SFC). When using cells in the place of beads, the unstained unmixing controls are particularly important, given that they enable subtraction of the autofluorescence background present within single-color unmixing controls, and potentially serve as an additional fluorophore.

Autofluorescence, especially in context of human cord and peripheral mononuclear cells (CBMCs and PBMCs), is often treated as a single fluorophore, primarily differing between cell populations in brightness. However, the sources of autofluorescence within a cell may vary and are affected by cell activation, cryopreservation, and fixation during processing. Thus, at the single cell level, autofluorescence signatures may be slightly different. The point at which variation in autofluorescence at the individual cell level goes from being negligible to impacting the resolution of a complex panel is still being addressed. If multiple autofluorescence signatures are present in a population but unaccounted for in the unmixing matrix, uncertainty is introduced, reducing the ability to resolve other fluorophores. This is particularly problematic within large spectral panels with closely related fluorophores and complex marker co-expression patterns. However, the addition of multiple highly similar autofluorescence signatures to an unmixing matrix can increase the complexity with further loss of resolution.

We set out to quantitatively interrogate at which point differences in autofluorescence signatures within human mononuclear cells begin to impact panel resolution. Using our R package Luciernaga, we profiled autofluorescence signatures in more than 150 cryopreserved CBMC and PBMC specimens, treated with different activation conditions and with different fixatives. For each .fcs file, we quantified the normalized signatures of individual cells, grouped and enumerated cells based on shared signatures, and visualized the data across specimens and treatments. Since we had samples stained with complex panels matching many of the unstained controls, we used autofluorescence signatures isolated from the unstained controls to iteratively unmix the samples in R, employing ordinary least squares to evaluate the effect these signatures had upon unmixing.

We found that the majority of the autofluorescence signatures within human mononuclear cells acquired on a 5-laser Cytek Aurora® share a common primary peak (typically on detector V7). Variation in the relative height of the second and third peak (typically UV7 and B3, respectively) was noted between CBMC and PBMC, as well as treatment conditions. A degree of variation in the height of the second and third peak was tolerated without impacting the unmixing. This pattern held true for rare “variant” signatures that did not have a primary peak on V7, as long as they shared the same primary peak. These variant signatures were different enough to cause unmixing errors when present in >1% of PBMC, explaining unmixing issues we previously encountered.

Our work highlights variation in autofluorescence signatures within human CBMC and PBMC cells activated with different stimuli, and established thresholds at which we observe impacts on the effect that unmixing controls had on resolving complex SFC panels. We provide a method by which shared variant autofluorescence signatures can be isolated and highlight the importance of collecting sufficient unstained cells to profile rarer variation in autofluorescence that might otherwise be missed.
