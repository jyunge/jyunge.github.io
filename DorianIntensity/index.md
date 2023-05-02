# On the low-level wind field and maximum intensity of Hurricane Dorian (2019)
Author: Jimmy Yunge
Last edited: May 1, 2023

## Abstract

An informal yet scientifically guided discussion on the maximum intensity of Hurricane Dorian (2019) is presented, with some comments on the wind speeds experienced in Marsh Harbour, Great Abaco in the Bahamas on 01 September. A variety of datasets are shown and discussed alongside analytical, observational, and numerical studies from tropical cyclone (TC) literature. The purpose of this article is not to diagnose an exact maximum wind speed value to Dorian at any particular time or location, but rather to suggest that the maximum (and Abaco landfall) intensity assessed by the National Hurricane Center (NHC) is valid within acknowledged error bounds in the context of overall TC structure and land impacts.

---

## 1. Context

On 01 September 2019, Hurricane Dorian made landfall in the Abaco Islands in the NW Bahamas, first on Elbow Cay at 16:40 UTC and then on Great Abaco around 18:00 UTC, according to the NHC best track (Avila et al. 2020). This followed a period of rapid intensification of 30 kt in the previous 24 h. The intensity of Dorian at these landfalls was assessed at 160 kt (185 mph). In this article, the term "intensity" will be used interchangeably to refer to maximum sustained wind, with the latter defined by NHC as a theoretical mean value taken at 10 m above the surface over an interval of 60 s anywhere in the storm. For brevity, we will often use the term "surface winds" to refer to those at the conventional 10-m height, though "near-surface" would perhaps be more appropriate. We will also mostly use SI units following standard scientific practice, where 1 m/s ~ 2.237 mph ~ 1.944 kt.

## 2. Automated surface wind analyses

Two objective (i.e., automated) surface wind analyses, HWIND and TCSWA, are shown here for Dorian around the time of landfall on Abaco. Details of the analyses, and by proxy some of their strengths and weaknesses, are examined. This section is intended more as a refutation of a previous claim which used HWIND to justify the maximum intensity and surface wind distribution of Dorian at landfall.

### 2.1. HWIND

HWIND, formerly H\*WIND, is a (now) proprietary product of the risk management and reinsurance company RMS, and so the raw data is unavailable publicly for inspection. Assuming the algorithm itself has not undergone significant changes since it was privatized, HWIND uses the method of least squares and cubic spline interpolation to fit a gridded wind field (the analysis) to the ingested, time-composited observations. The interpolation and compositing also act as a low-pass filter, smoothing out mesoscale and smaller features. The new wind field is enhanced by multiplying by a 1-min gust factor (a value of 1.094 was used by Powell et al. 2010) in the eyewall that exponentially decays with radius to "restore" a value for the 1-min maximum sustained wind.

A few graphics for Dorian were released by RMS in near-real time on social media, allowing for limited visual assessment. An example for 01 September 18:00 UTC is shown in Figure 1 (left). As mentioned above, wind maxima associated with convective-scale features, such as rainbands, are nearly completely absent. This has critical implications on the estimation of intensity, which will be explored further below with high-resolution numerical model data. The identified maximum wind speed, given in the graphic, underestimates the best track intensity by about 20 mph. It is plausible that the fitted B-splines for this particular analysis did not accurately capture Dorian's compact eyewall.

Because of the intrinsic smoothing and time compositing, it is more valid to use these analyses in describing the general kinematic spatial characteristics (i.e., storm-scale surface wind distribution), rather than discerning rapidly evolving convective-scale features, let alone the instantaneous maximum wind. For example, Nolan et al. (2021a,b) used H\*WIND in an azimuthal-mean sense to evaluate WRF simulations of Hurricane Wilma (2005), and the reasonably good fit of the wind profiles added confidence to the realism of the simulated time-dependent surface winds as validated by in situ observations. In addition, Nolan et al. (2021a; their Figure 6) noted that H\*WIND diagnosed unrealistic inflow while the vortex was centered over land. While Abaco is certainly smaller than South Florida, and this issue may well have since been alleviated using an updated methodology, the realism of the above 01 September 18:00 UTC analysis could have been slightly affected by land mass.

Lastly, there is the presence of "artifacts" in the analyzed wind fields, here by which we mean topological features resulting from characteristic behaviors of the basis functions. A rather conspicuous case is shown in Figure 1 (right) for 03 September 00:00 UTC, where the surface wind field is distinctly angular, surely an exaggeration of any actual asymmetries (see Figure A1, appendix, for a comparison to other analyzed wind fields; the HWIND for 02 September 18:00 UTC could be even more egregious but is not shown due to the lack of airborne radar data for comparison). This may have been due to the time-compositing of observations during a period of rapid weakening, along with possibly inadequate weighting of certain input points. Generally, this is not too much of a concern, especially when consulting these analyses as just one component of a broader assessment, but this emphasizes the fact that one must be extremely careful in interpreting these fields, or any other automated product, as a ground truth without understanding their underlying properties or intended use. This especially holds for proprietary data.

### 2.2. TCSWA

Another well-known automated surface wind product in the research and operational communities is the aircraft-based Tropical Cyclone Surface Wind Analysis (TCSWA), produced in real time by Colorado State University's Cooperative Institute for Research in the Atmosphere (CIRA). The TCSWA is a component of the satellite- and aircraft-blended Multiplatform Tropical Cyclone Surface Winds Analysis (MTCSWA), for which the inner core region is heavily determined by SFMR data (Knaff et al. 2015). Compared to HWIND, TCSWA uses a variational technique, minimizing a cost function between observations and a bilinearly interpolated flight-level wind field (the analysis); details are given in Knaff et al. (2011). Smoothness constraints in the optimization problem also act as a low-pass filter. The surface winds are computed using established flight-level reduction factors and parameterized inflow angles, before finally being rotated into earth-relative coordinates. One notable difference is that TCSWA uses greater weights in the azimuthal direction versus H\*WIND (Knaff et al. 2015; Nolan et al. 2021a), giving it a noticeably more circular appearance. Artifacts produced by the analysis include band- or streak-like structures, for example as seen to the NW of the storm in the 02 September 00:00 UTC panel in Figure 2 (bottom right).

Our purpose in showing the TCSWA fields is not to diagnose a value or location of the maximum wind, as many of the points stated above on automated analyses for HWIND also apply here. Unlike HWIND, however, we are able to examine the raw data for all times of interest. As the storm was steadily intensifying up to landfall, it is not surprising to see shifting locations of the strongest winds in the TCSWA fields as portrayed in Figure 2. As will be supported using airborne Doppler radar observations below, there were likely rapidly evolving asymmetries in Dorian's wind field leading up to landfall, therefore precluding any simple or meaningful identification of a singular location of the maximum wind in any mesoscale or smaller sense. In addition, qualitatively examining the 01 September 18:00 UTC TCSWA, also to be supported by radar data, it is argued that Dorian had achieved a very symmetric storm-scale circulation by landfall. The highest winds would then have been present across a wide azimuthal extent in the eyewall, subjecting a large area on the surface to the greatest intensity of the storm, regardless of its exact magnitude. This will also be elaborated on farther below using high-resolution numerical model data.

## WP-3D tail Doppler radar


## Numerical modeling
![](https://github.com/jyunge/jyunge.github.io/blob/21755a5e237fc921b1c69cc0b487659e6d5cf906/DorianIntensity/images/cece_etal_2021_fig3.png)
Cécé et. al (2021), their Figure 3.
![](https://github.com/jyunge/jyunge.github.io/blob/21755a5e237fc921b1c69cc0b487659e6d5cf906/DorianIntensity/images/cece_etal_2021_fig8.png)
Cécé et. al (2021), their Figure 8.

## Qualitative observations


## Conclusions


## Acknowledgments


## References
* Cécé et. al (2021): https://doi.org/10.5194/nhess-21-129-2021.
