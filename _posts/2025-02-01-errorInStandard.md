---
title: 'Error of Turbulence Spectrum Model in IEC 61400-1'
date: 2025-02-01
permalink: /posts/2025/02/errorInStandard/
tags:
  - Turbulence Theory
  - TKE Energy Spectrum
  - Wind Turbine
---

This blog discusses an error of turbulence (spectrum) model presented in the IEC 61400-1 standard for wind turbine design. Details of this scientific error and the reason why this error occurred are explained.


In Section 6.3 "Wind Condition" of the IEC 61400-1 standard, there is an error in Formula (7). Formulas (6) and (7) provide expressions for the autocorrelation spectra (frequency spectra) of the three velocity components in the inertial subrange of the turbulence energy spectrum (i.e., the -5/3 power law range):

$$
\begin{align*}
    S_1(f) = 0.05 \sigma_1^2 (\varLambda_1/V_{\mathrm{hub}})^{-2/3} f^{-5/3}
    \qquad (6)  \\
    S_2(f) = S_3(f) = \frac{4}{3} S_1(f)
    \qquad\qquad\qquad (7)  \\
\end{align*}
$$

There is a clear error in Formula (7). The turbulence fluctuation energy in the 2 and 3 directions is generally not higher than that in the flow direction (the 1 direction).

The cause of this mistake is that the above equation (7) incorrectly converts the wavenumber spectrum into a frequency spectrum. The spectral distribution $E_{ij}(\mathbf{\kappa})$ is a function of the three-dimensional wavenumber vector $\mathbf{\kappa}$, where $\mathbf{\kappa} = (\kappa_1, \kappa_2, \kappa_3) = 2\pi/\mathbf{l}$, where $\kappa_m = \sqrt{\kappa_1^2 + \kappa_2^2 + \kappa_3^2} $ represents the magnitude of the wave vector. According to the literature[^1],

$$
\begin{gather*}
    S_1(\kappa_1) = E_{11}(\kappa_1) = C_1 A \kappa_1^{-p},  \\
    S_2(\kappa_1) = E_{22}(\kappa_1) = C'_1 A \kappa_1^{-p},  \\
    E(\kappa_m) = C A \kappa_m^{-p},
\end{gather*}
$$

where $C'_1 = 0.5(1 + p)C_1$ and $C'_1 = 4/3C_1$ is obtained when $p = 5/3$.

I suspect that this is the reason why Eq. (7) in the IEC standard contains the error. They incorrectly analogized the $ S_2(f) $ spectrum to the $ S_2(\kappa_1) $ spectral distribution. However, when analogizing the frequency spectrum to the wavenumber spectrum, it should be compared to the spectrum of the wavenumber magnitude $ S_2(\kappa_m) $, not the component spectrum. That is,

$$
\begin{equation*}
    S_i(f) \sim S_i(\kappa_m) \neq S_i(\kappa_1).
\end{equation*}
$$


[^1]: Pope, S. B. (2000). Turbulent Flows (Vol. 12, pp. 2020–2021). Cambridge University Press.
