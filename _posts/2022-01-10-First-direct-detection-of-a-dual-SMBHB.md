---
format: post
tags:
  - research
  - super massive black hole
mathjax: true
---



# First direct dynamical detection of a dual supermassive black hole system at sub-kiloparsec separation

## Yiqian Qian 2022-01-10

# Cloeset pair of supermassive black holes
On Nov 30, 2021, using European Sounthern Observatory's (ESO) Very Large Telescope (VLT), astronomers discoveried the closest pair of supermassive black holes system to Earth ever observed, which is located in the galaxy NGC 7727 in the constellation Aquarius and has the smallest separation (500 pc, about 1600 light-years) comparing with previously spotted supermassive black holes and will eventually merge into one giant supermassive black hole. 

![image-20220108165741770]({{site.baseurl}}/assets/img/2022-01-10-First-direct-detection-of-a-dual-SMBHB.assets/image-20220108165741770.png)

The supermassive black hole pair is about 89 million light-years away from us, though this may seem distant, the previous record is 470 million light-years away, making this newly discovered supermassive black hole pair the closest to us yet.

# Paranal Observertory

This discovery was made by using the ESO's VLT on Paranal Observertory, and the measurements of the masses of the two supermassive black holes (154 $\mathrm{M}_{\odot}$ and 6.3 million $\mathrm{M}_{\odot}$ ) were made by using the Multi-Unit Spectroscopit Explorer (MUSE) on VLT. There's a brief but beautiful short [movie](https://youtu.be/6rVqH1Ijabw) about VLT.

![image-20220108171651798]({{site.baseurl}}/assets/img/2022-01-10-First-direct-detection-of-a-dual-SMBHB.assets/image-20220108171651798.png)

## MUSE

The figures blow show the Multi-Unit Spectroscopic Explorer and its spech details, it's a very complicated instruments, for more details please check [here](https://www.eso.org/public/teles-instr/paranal-observatory/vlt/vlt-instr/muse/).

Shortly, MUSE is an integral field spectrograh (IFS), which allows you to observe the entirety of an astronomical object at a time, each pixel contains the information about intensity varying with color, or wavelength. The resulting data is a 3D image set containing the full spectrum of the light in each pixel. MUSE splits the field of view into 24 individual image segments or channels which are each split further into 48 slices or “mini slits”, giving a total of 1152 mini slits. Each set of 48 mini slits is injected into a spectrograph, which disperses the light into its constituent colours, and MUSE measures over 4000 of these colours! From this, the 3D image is created.

<img src="{{site.baseurl}}/assets/img/2022-01-10-First-direct-detection-of-a-dual-SMBHB.assets/image-20220108172301884.png" alt="image-20220108172301884" style="zoom:50%;" />

<img src="{{site.baseurl}}/assets/img/2022-01-10-First-direct-detection-of-a-dual-SMBHB.assets/image-20220108172313190.png" alt="image-20220108172313190" style="zoom:50%;" /><img src="{{site.baseurl}}/assets/img/2022-01-10-First-direct-detection-of-a-dual-SMBHB.assets/image-20220108172321551.png" alt="image-20220108172321551" style="zoom:50%;" />

# Measurements

## Location and kinematic

The two figures below show the skylocation of the galaxy NGC 7727 and the two collapsed nuclei which are separated 500 pc. The kinematics are measured by analysing the data via a series pipelines, i.e. choose steller templates from MUSE template library, bin the spectra areas whose S/N is too low etc.

<img src="{{site.baseurl}}/assets/img/2022-01-10-First-direct-detection-of-a-dual-SMBHB.assets/image-20220110161803576.png" alt="image-20220110161803576" style="zoom:50%;" />

<img src="{{site.baseurl}}/assets/img/2022-01-10-First-direct-detection-of-a-dual-SMBHB.assets/image-20220110164108412.png" alt="image-20220110164108412" style="zoom:50%;" />

For the kinematic measurements, the team restricted the MUSE wavelength range from 6500-9000 $\mathrm{\AA}$, in order to closely match the wavelength of the mass model. They derived the uncertainty of the pPXF kinematic measurements using 50 Monte Carlo resamplings of each spectrum, adding a Gaussian error, and then reﬁtting the kinematics. The standard deviation of the 50 ﬁt results is used as $1-\sigma$ error for the kinematics. The dispersion and velocity map of the entire ﬁeld of view at the S/N= 25 binning are shown in Fig. 2. 

From the Fig. 2 top panel, we can see the large-scale kinematic signatures of the galaxy with strong rotation along the axis aligned nearly north to south. Though such signatures are not resolved at Nucleus 2, its velocity is the same as the surronding stellar velocities of the main galaxy and thus definitely part of NGC 7727.

## Jeans anisotropic models (JAMs)

### M/L gradiant

Here, they used single stellar population (SSP) fits to determin if there is a mass-to-light ratio gradient, the top and middle panel shows the observed foreground extinction-corrected radial HST color profiles of Nucleus 1 and 2 comparing with the predicted color from the SSP fits. The SSP fits clearly show that there is a M/L gradient in Nucleus 2, therefore requiring a variable M/L ratio when using the standard JAM models.

<img src="{{site.baseurl}}/assets/img/2022-01-10-First-direct-detection-of-a-dual-SMBHB.assets/image-20220110171149651.png" alt="image-20220110171149651" style="zoom:50%;" />

### Dynamical modeling

JAMs solve the stellar Jeans equations to predict the velocity and dispersion fields based on a mass model of the galaxy. The JAM models need the adaptive optics point spread function (AO PSF) and the stellar-mass profile of the galaxy components as inputs. The JAM models solve the Jeans equations to predict the second-order velocity moment $v_\mathrm{rms}=\sqrt{v^2+\sigma^2}$, and they then integrate the same spatial bins used in the data. A cut-out of the observed $v_\mathrm{rms}=\sqrt{v^2+\sigma^2}$ map in the cneters of Nucleus 1 and 2 are shown below. These $v_\mathrm{rms}$ maps are the input that is given to the dynamical models.

<img src="{{site.baseurl}}/assets/img/2022-01-10-First-direct-detection-of-a-dual-SMBHB.assets/image-20220110173242816.png" alt="image-20220110173242816" style="zoom:50%;" />

<img src="{{site.baseurl}}/assets/img/2022-01-10-First-direct-detection-of-a-dual-SMBHB.assets/image-20220110173250499.png" alt="image-20220110173250499" style="zoom:50%;" />

The JAM models have 4 parameters, BH mass, mass-scaling factor $\Gamma$, anisotropy $\beta$, and inclination as free parameters. In normal JAM models, mass-scaling factor is equal to the M/L ratio, but due to the M/L ratio gradient, this factor works as a scale of the M/L gradient.

### Nucleus 1

The MCMC Jeans model derives a best-ﬁt black-hole mass for Nucleus 1 of $M_{\mathrm{BH}} = 1.54_{−0.06}^{+0.07}\times 10^8 M_{\odot}$ . The corner plot of the distribution of the MCMC realizations is shown below. The best-fit black hole mass is $M_\mathrm{BH}=1.54^{+0.07}_{-0.06}\times10^8M_{\odot}$, the best-fit mass-scaling factor $\Gamma$ is of $1.14^{+0.03}_{-0.04}$, indicationg that the main galaxy has a high intrinsic $M/L \sim 3.4$, silightly higher than the predicted value of around 3 (bottom panel of Fig. 6).

<img src="{{site.baseurl}}/assets/img/2022-01-10-First-direct-detection-of-a-dual-SMBHB.assets/image-20220110173951984.png" alt="image-20220110173951984" style="zoom:50%;" />

### Nucleus 2

Nucleus 2 is embedded in NGC7727, which has a much higher velocity dispersion and thus can artiﬁcially raise the inferred velocity dispersion in Nucleus 2. Current state-of-the-art dynamical models cannot include oﬀ-center components, so we cannot model the main galaxy and Nucleus 2 at the same time. The best solution with these constraints is thus to evaluate the JAM models in a region where the contamination from the underlying galaxy’s light is negligible. The model gives the best-fit black hole mass for Nucleus 2 is of $M_\mathrm{BH}=6.33^{+1.59}_{-1.40}\times10^6M_{\odot}$. The reduced $\chi^2$ of the best-fit model is 1.63, showing that the model is a decent fit to their data. 

<img src="{{site.baseurl}}/assets/img/2022-01-10-First-direct-detection-of-a-dual-SMBHB.assets/image-20220110173959159.png" alt="image-20220110173959159" style="zoom:50%;" />

### Robustness test

Finally, the team evaluated the robustness of their JAM model by changing different parameters. For example, the default model uses a o.5'' limit for the fitting radius, and they tested 0.4'' and 0.6'' as variations. The results for other variations are shown below.

<img src="{{site.baseurl}}/assets/img/2022-01-10-First-direct-detection-of-a-dual-SMBHB.assets/image-20220111111954078.png" alt="image-20220111111954078" style="zoom:50%;" />

Their result shows most of the variations are within $1-\sigma$ range of the default model, indicating their model is quite stable.
