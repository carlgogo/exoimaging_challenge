This challenge is focusing on the exoplanet direct detection task. To measure the detection capability of different algorithms we will rely on the injection of fake companions to measure the true positive rate (TPR) and the number of false positives (FPs). The community is converging on the usage of receiver operating characteristic (ROC) curves for the performance assessment of high-contrast imaging post-processing algorithms (see Figure 3). We are considering the option of computing ROC curves by injecting a large number of fake companions to compare the trade-off of TPR and number of FPs for different algorithms as a function of the detection threshold.

> TBD: Do we have the computational resources to compute the ROC curves? Will the participants submit their codes?

> TBD: Contrast (brightness) interval for the injected companions as a function of the separation.

| ![data](https://raw.githubusercontent.com/carlgogo/exoimaging_challenge/master/assets/images/challenge_illustrations.003.png){:width="800px"} |
|---|
| Figure 3. ROC curves in the high-contrast imaging literature. Top-left from Gomez Gonzalez et al. 2016, top-right from Ruffio et al. 2017, bottom-left from Gomez Gonzalez et al. 2018 and bottom-right from Pueyo 2018. |

The output expected from an algorithm, i.e. the submission from a participant, is a detection map. Additionally, for the computation of ROC curves, we will require the source of the algorithm (if in Python) or an executable file, detection thresholds (for thresholding the detection maps and count the sources) and to quote what is the usual/accepted critical threshold at which a detection is claimed. The metrics will be calculated both for the case of single instruments and taking into account the whole benchmark library (multiple instruments, perhaps focusing on different distance regimes from the star). 

The metrics implementations will be open sourced for the sake of transparency and fairness. Also, they shall serve as a reference for future studies on direct imaging of exoplanets.

