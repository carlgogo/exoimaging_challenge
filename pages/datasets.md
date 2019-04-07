A group of datasets has being compiled for the purpose of this challenge. The datasets come from a few different instruments: SPHERE (both IRDIS and IFS), GPI, NIRC2 and LMIRCam. This is to ensure the challenge library contains a diverse set of datasets coming from instruments with different characteristics: slow/high speed cameras, broadband/filtered sequences, small/large total rotation, presence of a coronagraph, etc. 

In order to reduce the need of domain knowledge (e.g. the expertize related to high-contrast imaing or to a specific instrument), the datasets were calibrated/pre-processed using the standard pipelines of each instrument. Then we applied a few pre-processing procedures on each cube to make sure that the library is homogeneous. The characteristics of each dataset and the pre-processing procedures applied to them are recorded on a [public table](pages/datasets_table) ([direct link to the spreadsheet](https://docs.google.com/spreadsheets/d/1Zx7tTGNBMhCXpAa5KIoufdvMrxtjfA3q2gX03APMkaM/edit?usp=sharing)). 

| ![data](https://raw.githubusercontent.com/carlgogo/exoimaging_challenge/master/assets/images/challenge_fig2.001.png){:width="700px"} |
|---|
| Figure 2. *Schematic representation of the high-contrast imaging data processing pipeline, for the case of a LBTI/LMIRCam HR8799 data cube. Notice how from a single data cube we obtain one view of the star's vicinity and an associated detection map where we could detect potential point-like sources (and hopefully bound companions)*.  |

For the sub-challenge on ADI post-processing, each dataset will be composed of:
 * ``instrument_cube_id.fits`` (3d array),
 * ``instrument_pa_id.fits`` (1d array, vector of parallactic angles),
 * ``instrument_pxscale_id.fits`` (float value, the pixel scale value in arc/px),
 * ``instrument_psf_id.fits`` (2d array, the associated PSF template), 
 
where id is a positive integer and instrument is one of the following: ``nirc2``, ``lmircam``, ``sphere_irdis``, ``sphere_ifs`` or ``gpi``. For the second sub-challenge, on spectrally dispersed data, a 4D cube will be provided along with a vector of wavelengths (instrument_wvs_id.fits). 

The datasets will be cropped to focus on the innermost 20 lambda/D. To be able to measure the detection capability of different algorithms, we will inject from *none to five point-sources* in each dataset (standard injection process without accounting for smearing or variable photometry). For spectrally dispersed data we will use three template spectra when injecting the fake companions.

The challenge datasets will be stored in [FITS](https://en.wikipedia.org/wiki/FITS) format. This is a format with long tradition in astronomy and can be easily loaded in any programming language or environment (Python, Matlab, IDL, R, C, etc). The most convenient software for quick visualization of the cubes is the SAOImageDS9 software which can be obtained [here](http://ds9.si.edu/site/Download.html). If you are into Python and you use Jupyterlab, then consider using the [HCIplot](https://github.com/carlgogo/hciplot/) open source library. 

It is mandatory that the submitted datasets remain *secret* for the duration of the challenge. After the data challenge is finished, the contributed datasets (without injected companions) will constitute the **HCI benchmark library** that will be made available for the community. This benchmark library will be stored on Zenodo, ensuring the long term preservation of data, and will serve the next generation of researchers who will be able to re-use the benchmark datasets for quick validation of novel algorithms.


