# Circumgalactic Medium - Spectrum Reconstruction

This repository contains the analysis done as a part of the [CGM challenge in ML4SCI 2021](https://github.com/ML4SCI/ML4SCIHackathon/tree/main/CircumgalacticMediumChallenge).

## Approach

**Pre-processing**:

The input spectra was rebinned to suppress noise and to make the encoder robust to stochastic noise in the input spectra. The motivation of this idea is from *Wang, Guo and Luo, 2016* <sup>1</sup>.

A convolutional autoencoder with Leaky ReLU activations was used. The Adam optimizer was used and a reduce_lr_on_plateau learning rate scheduler was used. Maximum no. of epochs to train was set to 40. A 90%-10% split was used to generate training and validation sets. Latent dimension of 6 was found to yield the lowest reconstruction loss.

## Results

Sample spectra reconstructions:


![Screenshot from 2022-02-09 00-56-35](https://user-images.githubusercontent.com/68844397/153060934-518ea919-684b-47be-956a-4672c06ba66b.png)

The reconstruction loss on the testing set is ~0.00406

## References
[1] Ke Wang, Ping Guo, A-Li Luo, A new automated spectral feature extraction method and its application in spectral classification and defective spectra recovery, Monthly Notices of the Royal Astronomical Society, Volume 465, Issue 4, March 2017, Pages 4311–4324, https://doi.org/10.1093/mnras/stw2894
