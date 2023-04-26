# gmx-scattering

This is implementation of **gmx scattering** module that is aimed to replace old **gmx sans** and **gmx saxs** modules.
Module **gmx scattering** uses Debye method to calculate SANS and SAXS spectra via pair distance distribution histogram.

$$
I(s) = \sum_{i} \sum_{j} f_i(s) * f_j(s) * \frac{sin(s*r_{ij})}{s*r_{ij}}
$$

where $ r_{ij} = \left| \vec{r_i} - \vec{r_j} \right| $ between atoms $i$ and $j$
and $ f_i(s) $, $ f_j(s) $ are atomic structure factors for atoms $i$ and $j$


For SAXS mode **gmx scattering** uses Cromer-Mann approximation for atomic structure factors
$$
s(q) = \sum_{i}^{4}  a_i * \exp(- b_i * (\frac{q}{4\pi})^2) + c
$$