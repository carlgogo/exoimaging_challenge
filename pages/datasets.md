The benchmark datasets will be compiled in a public repository, ensuring the long term preservation of data. The datasets used in the context of this challenge will serve the next generation of researchers who will be able to re-use the benchmark library for quick validation of novel algorithms.

**Task:** *What infrastructure could we use to store the benchmark datasets associated with this challenge? NASA Exoplanet Archive, DIVA database, Zenodo, Quilt, others?*

In order to reduce the need of domain knowledge (e.g. the expertize on a specific instrument), the datasets will be calibrated/pre-processed using the standard pipelines of each instrument. When entering the database, they will be recorded in a public [table (Google spreadsheet)](pages/datasets_table)). A complete description of the calibration procedures performed, and a link to the software used, will be attached to each datacube.

| ![data](https://raw.githubusercontent.com/carlgogo/exoimaging_challenge/master/assets/images/challenge_illustrations.002.png){:width="700px"} |
|---|
| Figure 2. High-contrast imaging data processing pipeline. |

 The datasets will be stored in [FITS](https://en.wikipedia.org/wiki/FITS) format. This is a format with long tradition in astronomy and can be easily loaded in any programming language or environment (Python, Matlab, IDL, R, C, etc).
 
**Task:** *Which datasets will enter the benchmark database ([table/spreadsheet](pages/datasets_table))?* 

