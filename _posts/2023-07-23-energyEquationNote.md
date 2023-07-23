---
title: 'Energy Conservation Equation for Compressible Flow'
date: 2023-07-23
permalink: /posts/2023/07/energyEquationNote/
tags:
  - Theory
  - Fluid Dynamics
  - Heat Transfer
---

## Terminology

* $e\:(\mathrm{J/kg})$: thermodynamic energy or (specific) internal energy
* $E\:(\mathrm{J/kg})$: (specific) total internal energy
* $h\:(\mathrm{J/kg})$: (specific) enthalpy
* $H\:(\mathrm{J/kg})$: (specific) total enthalpy
* $T\:(\mathrm{K})$: temperature


## Kinetic energy

General continuity equation:

$$
\begin{equation}
    \partial_t \rho + (\rho u_j)_{,\,j} = \dot{m}.
\end{equation}
$$

Cauchy momentum equation:

$$
\begin{equation}
    \partial_t (\rho u_i) + (\rho u_i u_j)_{,\,j}
  = -p_{,\,i} + \sigma_{ij,\,j} + \rho f_i + \dot{m}u_i.
\end{equation}
$$

Notice that

$$
\begin{equation}
    \partial_t (\rho u_i) + (\rho u_i u_j)_{,\,j}
  = \rho \mathrm{D}_t u_i + u_i \dot{m}.
\end{equation}
$$


The **kinetic energy conservation** can be expressed as

$$
\begin{equation}
    \partial_t (\tfrac12 \rho u_i u_i) + (\tfrac12 \rho u_i u_i u_j)_{,\,j}
  = (-pu_j + \sigma_{ij}u_i)_{,\,j} + \rho f_i u_i + pu_{j,\,j} - \sigma_{ij} u_{i,\,j} + \tfrac12 u_i u_i \dot{m}.
\end{equation}
$$


## Internal energy

According to 1st law of thermodynamics,

$$
\begin{equation}
\begin{split}
    \partial_t (\rho e + \tfrac12 \rho u_i u_i) +
    (\rho u_j e + \tfrac12 \rho u_i u_i u_j)_{,\,j} &= \\
    -q_{j,\,j} + \dot{Q} + \rho f_i u_i &+ ( -pu_j + \sigma_{ij}u_i)_{,\,j} + \dot{m}(e + \tfrac12 u_i u_i).
\end{split}
\end{equation}
$$

Subtracting the kinetic energy corresponding to (4), the equation of internal energy $e$ is obtained as

$$
\begin{equation}
    \partial_t (\rho e) + (\rho u_j e)_{,\,j}
  = -q_{j,\,j} + \dot{Q} - pu_{j,\,j} + \sigma_{ij} u_{i,\,j} + \dot{m}e.
\end{equation}
$$


## Total internal energy

Based on (5), the equation of total internal energy $E$ is

$$
\begin{equation}
    \partial_t (\rho E) + (\rho u_j E)_{,\,j}
  = -q_{j,\,j} + \dot{Q} + \rho f_i u_i + ( -pu_j + \sigma_{ij}u_i)_{,\,j} + \dot{m}E.
\end{equation}
$$


## Enthalpy

Using $h = e + pv$ or $\rho h = \rho e + p$,

$$
\begin{equation}
    \partial_t (\rho h) + (\rho u_j h)_{,\,j} - \partial_t p - (u_j p)_{,\,j}
  = -q_{j,\,j} + \dot{Q} + \sigma_{ij} u_{i,\,j} - pu_{j,\,j} + \dot{m}(h - p/\rho).
\end{equation}
$$

After rearranging,
$$
\begin{equation}
    \partial_t (\rho h) + (\rho u_j h)_{,\,j}
  = -q_{j,\,j} + \dot{Q} + \sigma_{ij} u_{i,\,j} + \mathrm{D}_t p  + \dot{m}h - \dot{m}p/\rho.
\end{equation}
$$


## Total enthalpy

Using $\rho H = \rho E + p$,

$$
\begin{equation}
    \partial_t (\rho H) + (\rho u_j H)_{,\,j}
  = -q_{j,\,j} + \dot{Q} + \rho f_i u_i + (\sigma_{ij}u_i)_{,\,j} + \partial_t p + \dot{m}H - \dot{m}p/\rho.
\end{equation}
$$


## Temperature

Provided that fluid follows ideal gas law then

$$
\begin{equation}
    \partial_t (\rho c_v T) + (\rho u_j c_v T)_{,\,j}
  = -q_{j,\,j} + \dot{Q} - pu_{j,\,j} + \sigma_{ij} u_{i,\,j} + \dot{m} c_v T.
\end{equation}
$$

If all transport properties are constant, (11) becomes

$$
\begin{equation}
    \partial_t (\rho T) + (\rho u_j T)_{,\,j}
  = (-q_{j,\,j} + \dot{Q} - pu_{j,\,j} + \sigma_{ij} u_{i,\,j})/c_v + \dot{m}T.
\end{equation}
$$




