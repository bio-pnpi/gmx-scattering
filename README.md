# gmx-scattering

## Intro
This is implementation of **gmx scattering** module that is aimed to replace old **gmx sans** and **gmx saxs** modules.
Module **gmx scattering** uses Debye method to calculate SANS and SAXS spectra via pair distance distribution histogram.

$$
I(s) = \sum_{i} \sum_{j} f_{i}(s) * f_{j}(s) * \frac{sin(s * r_{ij})}{s * r_{ij}}
$$

where $r_{ij} = \left| \vec{r_{i}} - \vec{r_{j}} \right|$ is distance between atoms $i$ and $j$
and $f_{i}(s)$, $f_{j}(s)$ are atomic structure factors for atoms $i$ and $j$


For SAXS mode **gmx scattering** uses Cromer-Mann approximation for atomic structure factors
$$
s(q) = \sum_{i}^{4}  a_{i} * \exp(- b_{i} * (\frac{q}{4\pi})^2) + c
$$

## Installation
* Install GROMACS (you need version 2022.x or 2023.x)
* clone this repo and build it with cmake
