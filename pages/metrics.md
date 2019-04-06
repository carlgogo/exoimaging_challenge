This challenge is focusing on the exoplanet direct detection task. To measure the detection capability of different algorithms we will rely on the injection of fake companions to measure the true positive rate (TPR) and the number of false positives (FPs). The community is converging on the usage of receiver operating characteristic (ROC) curves for the performance assessment of high-contrast imaging post-processing algorithms (see [Jensen Clem et al. 2017](https://arxiv.org/abs/1711.01215)). In Fig. 3 is displayed a compilation of some ROC curves from the high-contrast imaging literature. We are considering the option of computing ROC curves by injecting a large number of fake companions to compare the trade-off of TPR and number of FPs for different algorithms as a function of the detection threshold.

| ![data](https://raw.githubusercontent.com/carlgogo/exoimaging_challenge/master/assets/images/challenge_fig3.001.png){:width="800px"} |
|---|
| Figure 3. *ROC curves in the high-contrast imaging literature. Top-left from [Gomez Gonzalez et al. 2016](https://arxiv.org/abs/1602.08381), top-right from [Ruffio et al. 2017](https://arxiv.org/abs/1705.05477), bottom-left from [Gomez Gonzalez et al. 2018](https://arxiv.org/abs/1712.02841) and bottom-right from [Pueyo 2018](https://link.springer.com/referenceworkentry/10.1007/978-3-319-30648-3_10-1)*. |

### Phases

Therefore we envision two phases for this challenge, each one with its own type of submission. In the first phase, the expected output from an algorithm, i.e. the submission from a given participant, are a detection map and a critical detection threshold for this specific algorithm (the accepted threshold at which a detection is claimed). A detection map must be provided for each challenge datacube. Then, by thresholding each detection map and counting the true and false positives, we define several metrics:

* the true positive rate (TPR) also known as sensitivity or recall: ``TPR = TPs / Ninj``,
* the false discovery/detection rate (FDR): ``FDR = FPs / Ndet``,
* the precision or positive predictive value (PPV): ``PPV = TPs / Ndet``,
* the F1-score or harmonic mean of TPR and the precision: ``F1 = 2 * PPV * TPR / (PPV + TPR)``.

where ``TPs`` is the number of true positives/detections (\*), ``FPs`` is the total number of false positives or Type I error (\*), ``Ndet`` is the total number of detections (``TPs + FPs``, \*) and ``Ninj`` is the total number of injections (accros all the datasets of a given sub-challenge).

(\*) made by a given participant with a given algorithm over all the datasets of a given sub-challenge.

The contrast (brightness) interval for the injection of synthetic companions will be estimated by using the median subtraction algorithm as a baseline. The S/N of a population of injected companions will be measured in the median subtracted frames. The interval of fluxes (or contrasts as a function of the separation from the star) will be defined by checking which contrast corresponds to S/Ns in given interval (e.g. 1 to 4). The participants of the data challenge will have until the end of March for generating their submissions to the phase 1. Two scoreboards will be computed, one for the sub-challenge on ADI data (3d arrays) and one for the sub-challenge on ADI+IFS cubes (4d arrays). We will use the F1-score to rank the entries on the scoreboards, because it serves well our goal of assessing the performance of detection algorithms as binary classifiers.

> Note a: Each submission must correspond to the results of applying the same algorithm to all the datasets. If your algorithm works for both 3D and 4D datasets then you need to make two submissions (to have your score on each scoreboard).

> Note b: The challenge interface will require a short description of the algorithm you used for a each submission.

> Note c: Participants may submit as many times as they want. This only updates their position on the scoreboard.

In a second phase, we will focus on the computation of ROC curves. For this purpose, we will require the source code of the algorithm (Python), an executable file or a Docker image. Additionally, we require the detection thresholds for the thresholding and counting sources procedure. The ROC curve computation boils down to repeating the above procedure of injecting companions in the empty challenge datasets, computing detection maps, thresholding them and counting sources, ie. the detection state and the number of false positives for different detection criteria. 

> Important: only the participants who agree to submit their code will be included in the second phase of this data challenge.

|           |3D Sub-challenge - ADI |4D Sub-challenge - ADI+IFS
|:--:       |:--:                   |:--:
|**Phase**  |**Metric**             |**Metric**                    
| 1         |F1, TPR and FDR        |F1, TPR and FDR
| 2         |ROC space              |ROC space      

### Starting kit

The implementations of the planet injection, source counting and ROC curve generation algorithms are included in the open source [Vortex Image Processing package](https://github.com/vortex-exoplanet/VIP) for the sake of transparency and fairness. Other code related to the data challenge is available at the [Data Challenge Extras repository](https://github.com/carlgogo/exoimaging_challenge_extras). Here we also share a Python script (``DC1_codalab_starting_kit.py``) that illustrates how to create the outputs to be submitted for participating in the data challenge.
 
The extras repository also contains a data challenge starting kit, in the form of a Jupyter notebook (``DC1_starting_kit.ipynb``), which explains in detail the source counting procedure on detection maps (to get the true and false positives). The starting kit can also be executed on the cloud thanks to [Binder](https://mybinder.org/v2/gh/carlgogo/exoimaging_challenge_extras/master). This implementation shall serve as a reference for future studies on image processing algorithms for direct imaging of exoplanets.


### Scoreboard

The challenge is implemented on [Codalab](http://codalab.org/), a framework for accelerating reproducible computational research. The participants will enter the competition by creating their own account on Codalab and following the link of the challenge. The scoreboards will be updated automatically after each submission to the Codalab interface.

