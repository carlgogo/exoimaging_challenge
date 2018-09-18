This challenge is focusing on the exoplanet direct detection task. To measure the detection capability of different algorithms we will rely on the injection of fake companions to measure the true positive rate (TPR) and the number of false positives (FPs). The community is converging on the usage of receiver operating characteristic (ROC) curves for the performance assessment of high-contrast imaging post-processing algorithms (see [Jensen Clem et al. 2017](https://arxiv.org/abs/1711.01215)). In Fig. 3 is displayed a compilation of some ROC curves from the high-contrast imaging literature. We are considering the option of computing ROC curves by injecting a large number of fake companions to compare the trade-off of TPR and number of FPs for different algorithms as a function of the detection threshold.

| ![data](https://raw.githubusercontent.com/carlgogo/exoimaging_challenge/master/assets/images/challenge_fig3.001.png){:width="800px"} |
|---|
| Figure 3. ROC curves in the high-contrast imaging literature. Top-left from [Gomez Gonzalez et al. 2016](https://arxiv.org/abs/1602.08381), top-right from [Ruffio et al. 2017](https://arxiv.org/abs/1705.05477), bottom-left from [Gomez Gonzalez et al. 2018](https://arxiv.org/abs/1712.02841) and bottom-right from [Pueyo 2018](https://link.springer.com/referenceworkentry/10.1007/978-3-319-30648-3_10-1). |

Therefore we envision two phases for this challenge, each one with its own kind of submission (and scoreboard). In the first phase, the expected output from an algorithm, i.e. the submission from a given participant, are a detection map and a critical detection threshold for this specific algorithm (the accepted threshold at which a detection is claimed). For each datacube, containing from none to five companions, a detection map is expected. Then, by thresolding each detection map, we can count the true detections and the number of false positives across all the datasets. If *Ninj* is the total number of injectionsm (for all the benchmark datasets) and *Ndet* is the number of detections made by a given participant with a given algorithm (also for all the benchmark datasets), then the true postive rate (TPR) is *TPR = Ndet / Ninj*.

> TBD: Contrast (brightness) interval for the injected companions as a function of the separation. Based on the result on a baseline detection map (eg. the S/N on a median subtracted dataset)?

In a second scoreboard, we will focus on the computation of ROC curves. For this purpose, we will require the source code of the algorithm (Python), an executable file or a Docker image. Additionally, we require the detection thresholds for the thresholding and counting sources procedure. The ROC curve computation boils down to repeating the above procedure of injecting companions in the benchmark datasets, computing detection maps, thresholding them and counting sources, ie. the detection state and the number of false positives for different detection criteria. 

> Only the participants that agree to submit their code will be included in this more informative scoreboard.  

The implementation of the source counting and ROC curves procedures will be open sourced (on GitHub) for the sake of transparency and fairness. This implementation shall serve as a reference for future studies on image processing algorithms for direct imaging of exoplanets.

Optionally, the metrics could be calculated both for the case of single instruments and taking into account the whole benchmark library (multiple instruments, perhaps focusing on different distance regimes from the star).

