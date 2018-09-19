The benchmark datasets will be compiled in a public repository, ensuring the long term preservation of data. The datasets used in the context of this challenge will serve the next generation of researchers who will be able to re-use the benchmark library for quick validation of novel algorithms.

> TBD: What infrastructure could we use to store the benchmark datasets associated with this challenge? A few options: NASA Exoplanet Archive, DIVA database, Zenodo, OSF. 

In order to reduce the need of domain knowledge (e.g. the expertize related to a specific instrument), the datasets will be calibrated/pre-processed using the standard pipelines of each instrument. When entering the database, they will be recorded in a public [table (Google spreadsheet)](pages/datasets_table)). A complete description of the calibration procedures performed, and a link to the software used, will be attached to each datacube.

| ![data](https://raw.githubusercontent.com/carlgogo/exoimaging_challenge/master/assets/images/challenge_fig2.001.png){:width="700px"} |
|---|
| Figure 2. Schematic representation of the high-contrast imaging data processing pipeline, for the case of a LBTI/LMIRCam HR8799 data cube. Notice how from a single data cube we obtain one view of the star's vicinity and an associated detection map where we could detect potential point-like sources (and hopefully bound companions).  |

The process of gathering datasets for the benchmark library has started. We aim to collect 3 to 5 datasets from a few different instruments: SPHERE, GPI, NIRC2, SCEXAO, and LMIRCam. This is to ensure the benchmark library contains a diverse set of datasets coming from instruments with different characteristics: slow/high speed cameras, broadband/filtered sequences, small/large total rotation, coronagraph type, etc. 

For the sub-challenge on ADI post-processing, a dataset will be composed of a calibrated cube (sequence of images), a vector of parallactic angles, the pixel scale value and the associated PSF template. For the second sub-challenge, on spectrally dispersed data, we will include a vector of wavelengths. The datasets will be cropped to focus on the innermost 20 lambda/D.

To be able to measure the detection capability of different algorithms, we will inject from zero to five point-sources in each dataset (standard injection process without accounting for smearing or variable photometry). For multi-channel mSDI we will use three template spectra for fake planet injection.

The datasets will be stored in [FITS](https://en.wikipedia.org/wiki/FITS) format. This is a format with long tradition in astronomy and can be easily loaded in any programming language or environment (Python, Matlab, IDL, R, C, etc).
 
> TBD: Which datasets will enter the benchmark database ([table/spreadsheet](pages/datasets_table))? 

