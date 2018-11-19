A list of datasets is being compiled for the purpose of this challenge. We aim to collect 3 to 5 datasets from a few different instruments: SPHERE, GPI, NIRC2, SCEXAO, and LMIRCam. This is to ensure the challenge library contains a diverse set of datasets coming from instruments with different characteristics: slow/high speed cameras, broadband/filtered sequences, small/large total rotation, coronagraph type, etc. 

In order to reduce the need of domain knowledge (e.g. the expertize related to a specific instrument), the datasets will be calibrated/pre-processed using the standard pipelines of each instrument. When entering the database, they will be recorded in a public [table (Google spreadsheet)](pages/datasets_table). 

| ![data](https://raw.githubusercontent.com/carlgogo/exoimaging_challenge/master/assets/images/challenge_fig2.001.png){:width="700px"} |
|---|
| Figure 2. Schematic representation of the high-contrast imaging data processing pipeline, for the case of a LBTI/LMIRCam HR8799 data cube. Notice how from a single data cube we obtain one view of the star's vicinity and an associated detection map where we could detect potential point-like sources (and hopefully bound companions).  |

For the sub-challenge on ADI post-processing, each dataset will be composed of:
 * a calibrated cube (sequence of images),
 * a vector of parallactic angles,
 * the pixel scale value,
 * the associated PSF template, 
 * complete description of the calibration procedure and a link to the software used (instrument dedicated pipeline).
 
For the second sub-challenge, on spectrally dispersed data, a vector of wavelengths will be included. 

The datasets will be cropped to focus on the innermost 20 lambda/D. To be able to measure the detection capability of different algorithms, we will inject from none to five point-sources in each dataset (standard injection process without accounting for smearing or variable photometry). For multi-channel mSDI we will use three template spectra for fake planet injection.

The challenge datasets will be stored in [FITS](https://en.wikipedia.org/wiki/FITS) format. This is a format with long tradition in astronomy and can be easily loaded in any programming language or environment (Python, Matlab, IDL, R, C, etc).

### HCI benchmark library

After the data challenge is finished, the contributed datasets (without injected companions or any other modification) will constitute the benchmark library that will be available to the community. It is mandatory that the submitted datasets remain *secret* during the duration of the challenge. The HCI benchmark library will be stored in a public repository, ensuring the long term preservation of data, and will serve the next generation of researchers who will be able to re-use the benchmark datasets for quick validation of novel algorithms.

> TBD: What infrastructure could we use to store the HCI benchmark library? A few options: NASA Exoplanet Archive, DIVA database, Zenodo, OSF. 

