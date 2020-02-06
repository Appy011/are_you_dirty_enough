# Are You Noisy Enough?

by <img src= "https://cdn3.iconfinder.com/data/icons/free-social-icons/67/linkedin_square_color-512.png" width="15"> [Chinmay Purav](https://www.linkedin.com/in/puravchinmay/)


# Table of Contents
- [Introduction](#Introduction)
- [Overview of the Data](#Overview-of-the-Data)
- [Feature Selection](#Feature-Selection)
- [Exploratory Data Analysis](#Exploratory-Data-Analysis)
- [Data Pipeline](#Data-Pipeline)
- [Model Selection](#Model-Selection)
- [Conclusion and Next Steps](#Conclusion-and-Next-Steps)


# Introduction

Decades of research has been done in the field of signal processing. This performance saturation has been stirred by the recent advances in Machine Learning and AI. The motivation is to work on a speech enhancement project. It is used in several applications such as hearing aids, teleconferrence systems, VoIP. Traditionally cleaning of audio has been done by statistical signal processing. With machine learning and AI, data-driven ways for the same are being explored.

This aim of this project is to label given audio file as 'Clean' or 'Noisy'. This would assist in the following project of speech enhancement. 


# Overview of the Data

The data was published by University of Edinburgh, UK. The data was made available on 08/21/2017 by the creator, Valentini-Botinhao. The data is made available to train speech enhancement models. The data used consist of 825 clean audio files and 825 noisy audio files.

The following waveplots of the first clean and noisy audio file will provide a visual representation of the background noise,

<p align="center"><img src="images/waveplots.png" /p>


# Feature Selection

<p align="center"><img src="images/signal_decomposition.png" /p>

Librosa library was used to extract the features from the audio files. All of the 1650 audio files were individually divided into the following features,

#### Zero Crossing Rate (ZCR):

ZRC is the measure of the rate at which a signal changes the sign. It is recorded on both instances, namely 'positive-zero-negative' and 'negative-zero-positive'. In essence, it measures the dominant frequency of the signal. This is an important feature which is used in speech recognition as well as music information retrieval. It is applied to detect whether human speech is present in the audio segment.
The plot shown below will provide a visual representation of how ZCR is calculated,

<p align="center"><img src="images/zrc.png" /p>

The first graph shows one clean audio waveplot. The second one is zooming in to observe how many times the signal crosses zero. Even though the second plot shows 4 times, the signal is fluctuating. Hence, further inspection is needed which can be observed in the third plot. 

#### Spectral Centroid:

Spectral Centroid is one of the features used to characterize specturm. It indicates the balancing point of the spectral ower distribution. It is widely used in digital audio and music processing to measure the perceived sound quality. 

<p align="center"><img src="images/spectral_centroid.png" /p>

#### Spectral Rolloff:

<p align="center"><img src="images/spectral_rolloff.png" /p>

#### Chroma Frequencies:

<p align="center"><img src="images/chroma_frequencies.png" /p>

#### Mel-frequency cepstral coefficients:

Mel-frequency Cepstrum represents short-term power spectrum of sound. The coefficients collectively form the Cepstrum. The difference between Mel-frequency Cepstrum and Cepstrum is that the frequencies in the Mel-frequncy Cepstrum are equally spaced. This is commonly used in speech recognition.
MFCCs are ensitive to noise in audio. To make them robust, the MFCCs are generally normalized to recognize speech. Another proposed modification is to raise the log-mel-amplitudes to a suitable power before the DCT which reduces the effect of low power components.

In the plots below, the waveplot is of a clean audio. The second graph shows the 20 MMFCCs computed over 146 frames. The third graph shows the same MFCCs but standardized.

<p align="center"><img src="images/mfcc.png" /p>

# Exploratory-Data-Analysis

EDA began with identifying how different features contribute differently to the classification.

<p align="center"><img src="images/spectral_eda.png" /p>

The first graph above which shows how the spectral factors respond differently for clean and noisy data. Images below display the same for the rmse feature.

<p align="center"><img src="images/rmse_eda.png" /p>

<p align="center"><img src="images/mfcc1_eda.png" /p>

MFCC1 is one of the features that caught attention as it has peculiar differences in the classification. This is one of the features that was mainly checked for correlation with the output.

# Data-Pipeline

# Model-Selection

# Conclusion-and-Next-Steps

# References

- University of Edinburgh, UK
- Microsoft
