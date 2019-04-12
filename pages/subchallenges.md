With the aim of creating a manageable competition, we will focus exclusively on the detection of point-like sources (exoplanets). Other tasks, such as the characterization of companions, the detection of extended sources, reference star differential imaging and the usage of metadata/telemetry, will be the subject of future editions of the challenge. 

This first competition will consider two sub-challenges focused on the two most widely used observing techniques: pupil tracking (angular differential imaging, ADI) and multi-spectral imaging combined with pupil tracking (multi-channel spectral differential imaging, ADI+mSDI). 

**ADI**: In pupil-stabilized or pupil-tracking observations the telescope pupil is stabilized on the detector and the field of view rotates in step with a given angle (the parallactic angle). This generates a fake movement of the companions in a circular trajectory around the center of the image, the place where the star is located. This process disentangles the exoplanet signal from the speckle field, an effect that is enhanced by the post-processing techniques. ADI datasets are composed of a 3d cube of images taken during an observing run (see Fig. 1) and their corresponding parallactic angles and non-saturated point-spread function (PSF). 

**ADI+mSDI**: In the case of multi-spectral imaging, an integral field spectrograph is used to disperse the light, providing a data cube of several monochromatic images. The resolution and band coverage varies depending on the instrument used. Since the speckles are a function of wavelength, we can rescale the images to align them and create a fake movement of the companions in a radial direction (this diversity is also exploited by the post-processing algorithms). Multi-spectral imaging is usually combined with ADI in modern instruments. In this case, the datasets are composed of a 4d cube of images (see Fig. 1), a vector of parallactic angles, a vector of wavelenghts and a PSF. 

| ![data](https://raw.githubusercontent.com/carlgogo/exoimaging_challenge/master/assets/images/challenge_fig2.001.png){:width="700px"} |
|---|
| Figure 2. *Schematic representation of the high-contrast imaging data processing pipeline, for the case of a LBTI/LMIRCam HR8799 data cube. Notice how from a single data cube we obtain one view of the star's vicinity and an associated detection map where we could detect potential point-like sources (and hopefully bound companions)*.  |

While Referential Differential Imaging (**RDI**) is not a separate sub-challenge, we welcome submissions that make use of reference datasets or libraries (whether it is the cubes provided within the challenge or external ones). We only require the participant to make clear if they use RDI instead of pure ADI or ADI+mSDI post-processing (please read the sub-section named "Codalab").

To be able to measure the detection capability of different algorithms, we will inject from *none to five point-sources* in each dataset (standard injection process without accounting for smearing or variable photometry). For spectrally dispersed data we will use three template spectra when injecting the fake companions.

| ![ADI_SDI](https://raw.githubusercontent.com/carlgogo/exoimaging_challenge/master/assets/images/challenge_fig1.001.png){:width="700px"} |
| --- |
| Figure 2. *Dimensionality of the cubes used in this challenge, depending on the observing technique: the left panel shows a single ADI data cube and the right panel shows an ADI + multi-channel SDI data cube*. |
