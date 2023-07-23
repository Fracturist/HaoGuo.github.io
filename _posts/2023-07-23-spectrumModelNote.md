---
title: 'Spectrum Models'
date: 2023-07-23
permalink: /posts/2023/07/spectrumModelNote/
tags:
  - Theory
  - Fluid Dynamics
  - Turbulence
---

[toc]

## Miscellaneous

Gamma function $\Gamma(z)$ (definition):

$$
\begin{align*}
    \Gamma(z) &\equiv
        \int_0^\infty
        {
            t^{z-1} e^{-t}
        }
        \mathrm{d}t  \\
    &=
        \int_0^\infty
        {
            2 x^{2z-1} e^{-x^2}
        }
        \mathrm{d}x.
        \quad (t = x^2)
\end{align*}
$$

Beta function $\Beta(m, n)$:

$$
\begin{align*}
    \Beta(m,n) &=
        \int_0^1
        {
            u^{m-1} (1-u)^{n-1}
        }
        \mathrm{d}u  \\
    &=
        \int_0^\infty
        {
            2 \frac
            {
                x^{2n-1}
            }
            {
                (1+x^2)^{m+n}
            }
        }
        \mathrel{d}x
        \quad
        \left(
            u = \frac{1}{1+x^2}
        \right)  \\
    &=
        \int_0^\infty
        {
            2 x^{-(2m+1)}
            \left(
                \frac{x^2}{1+x^2}
            \right)^{m+n}
        }
        \mathrm{d}x  \\
    &=
        \int_0^\infty
        {
            2 x^{-(2m+1)}
            \left(
                \frac{x}{\sqrt{1+x^2}}
            \right)^{ (2m+1) + (2n-1) }
        }
        \mathrm{d}x.
\end{align*}
$$

Now prove that

$$
\begin{align*}
    \Beta(p, q) = \frac{\Gamma(p)\Gamma(q)}{\Gamma(p+q)}.
\end{align*}
$$

Let $u=\cos^2\theta$,

$$
\begin{align*}
    \Beta(p, q) &=
        \int_{\frac{\pi}{2}}^0
        {
            (\cos^{2p-2}\theta)
            (\sin^{2q-2}\theta)
            (-2\sin\theta\cos\theta)
        }
        \mathrm{d}\theta  \\
    &= 2
        \int_{0}^{\frac\pi2}
        {
            (\cos^{2p-1}\theta)
            (\sin^{2q-1}\theta)
        }
        \mathrm{d}\theta.
\end{align*}
$$

Consider $\Gamma(p)\Gamma(q)$,

$$
\begin{align*}
    \Gamma(p) \Gamma(q) &=
        \int_0^\infty
        {
            2 x^{2p-1} e^{-x^2}
        }
        \mathrm{d}x
        \int_0^\infty
        {
            2 y^{2q-1} e^{-y^2}
        }
        \mathrm{d}y  \\
    &= 4
        \int_0^\infty
        \int_0^\infty
        {
            x^{2p-1} y^{2p-1}
            e^{-(x^2+y^2)}
        }
        \mathrm{d}x
        \mathrm{d}y.
\end{align*}
$$

Let $x = \rho \cos\theta$ and $y = \rho \sin\theta$,

$$
\begin{align*}
    \Gamma(p) \Gamma(q) &= 4
        \int_0^{\frac{\pi}2}
        \int_0^\infty
        {
            \rho^{2(p+q)-1}
            (\cos^{2p-1}\theta)
            (\sin^{2q-1}\theta)
            e^{-\rho^2}
        }
        \mathrm{d}\rho
        \mathrm{d}\theta  \\
    &= 2
        \int_0^\infty
        {
            \rho^{2(p+q)-1}
            e^{-\rho^2}
        }
        \mathrm{d}\rho
        \cdot
        2
        \int_0^{\frac\pi2}
        {
            (\cos^{2p-1}\theta)
            (\sin^{2q-1}\theta)
        }
        \mathrm{d}\theta  \\
    & =
        \Gamma(p+q) \Beta(p+q).
\end{align*}
$$


## Spectrum Model

Turbulence Reynolds number:

$$
    \mathrm{Re}_t = \frac{ u_t L }{\nu}
                  = \frac{ u_t^4 }{ \varepsilon \nu }
                  = \left( \frac{L}{\eta} \right)^{4/3}.
$$

Dissipation Scale:

$$
\begin{align*}
    \eta &\equiv \left( \frac{\nu^3}{\varepsilon} \right)^{1/4}.
\end{align*}
$$

### Low $\mathrm{Re}_t$ Model

$$
\begin{align*}
    E(\kappa) &=
        \alpha u_t^2
        \frac{\kappa^4}{\kappa_0^5}
        \exp{\left( -2\frac{\kappa^2}{\kappa_0^2} \right)}  \\
    &=
        C \varepsilon^{2/3} \kappa^{-5/3}
        (\kappa L)^{7/3} (\kappa\eta)^{10/3}
        \exp{\left( -2\frac{\kappa^2}{\kappa_0^2} \right)},
        \quad \textrm{(DO NOT USE)}
\end{align*}
$$

where $\alpha = 16 \sqrt{ \frac{2}{\pi} }$ and the energy spectrum function peak at $\kappa = \kappa_0$.


### High $\mathrm{Re}_t$ Model

General form:

$$
\begin{align}
    E(\kappa) =
        C \varepsilon^{2/3}\kappa^{-5/3}
        f_L(\kappa L)
        f_\eta(\kappa \eta),
\end{align}
$$

where

$$
\begin{gather*}
    \lim_{\kappa \to \infty} f_L(\kappa L) = 1,  \\
    \lim_{\kappa \to 0} f_\eta(\kappa \eta) = 1.
\end{gather*}
$$

Set $C = 1.5$.

#### Energy-containing Range Function

General form:

$$
\begin{align}
    f_L(\kappa L) =
    \left\lbrace
        \frac
        {
            \kappa L
        }
        {
            [(\kappa L)^2 + c_L]^{1/2}
        }
    \right\rbrace^{5/3 + p_0}.
\end{align}
$$

The integral of the model spectrum Eq.$(1)$ over all $\kappa$ yields

$$
\begin{align*}
    k &=
        \int_0^\infty
        {
            C \varepsilon^{2/3}\kappa^{-5/3}
            f_L(\kappa L)
            f_\eta(\kappa \eta)
        }
        \mathrm{d}\kappa  \\
    &\approx
        C (\varepsilon L)^{2/3}
        \int_0^\infty
        {
            (\kappa L)^{-5/3}
            f_L(\kappa L)
        }
        \mathrm{d} (\kappa L)  \\
    &=
       \tfrac{2}{3} C k \cdot G_L,
\end{align*}
$$

which requires $G_L = \frac{3}{2C} = 1$ provided that $C = 1.5$. Introduce Eq.$(2)$,

$$
\begin{align*}
    G_L &=
        \int_0^\infty
        {
            t^{-5/3} f_L(t)
        }
        \;\mathrm{d}t  \\
    &=
        \int_0^\infty
        {
            \frac
            {
                t^{p_0}
            }
            {
                (c_L+t^2)^{\tfrac{1}{2} (5/3+p_0)}
            }
        }
        \;\mathrm{d}t  \\
    &=
        c_L^{-1/3}
        \int_0^\infty
        {
            \frac
            {
                x^{p_0}
            }
            {
                (1+x^2)^{\tfrac{1}{2} (5/3+p_0)}
            }
        }
        \;\mathrm{d}x
        \quad (x = c_L^{-1/2} t)  \\
    &=
        c_L^{-1/3}\cdot
        \tfrac{1}{2}\;
        \Beta
        \left(
            \tfrac13,
            \tfrac12 + \tfrac12p_0
        \right)  \\
    &=
        c_L^{-1/3}
        \frac
        {
            \Gamma\left( \tfrac{1}{3} \right)
            \Gamma\left( \tfrac{1}{2} + \tfrac{1}{2}p_0 \right)
        }
        {
            2\; \Gamma\left( \tfrac{5}{6} + \tfrac{1}{2}p_0 \right)
        }
        = \frac{3}{2C}
        = 1.
\end{align*}
$$

For normal spectrum model, let $p_0 = 2$ then

$$
\begin{align*}
    c_L =
        \left[
            \frac
            {
                \Gamma\left( \tfrac{1}{3} \right)
                \Gamma\left( \tfrac{3}{2} \right)
            }
            {
                \Gamma\left( \tfrac{11}{6} \right)
            }
            \cdot
            \frac{C}{3}
        \right]^3
    = 2.009744224711003.
\end{align*}
$$

If $p_0 = 4$  (known as $\sf{von\, K\acute{a}rm\acute{a}n}$ spectrum),

$$
\begin{align*}
    c_L =
        \left[
            \frac
            {
                \Gamma\left( \tfrac{1}{3} \right)
                \Gamma\left( \tfrac{5}{2} \right)
            }
            {
                \Gamma\left( \frac{17}{6} \right)
            }
            \cdot
            \frac{C}{3}
        \right]^3
    = 1.100753974315793.
\end{align*}
$$


#### Dissipation Range Function

The expression for dissipation obtained from integration of the model spectrum Eq.$(1)$ is

$$
\begin{align*}
    \varepsilon &=
        2 \nu
        \int_0^\infty
        {
            \kappa^2
            \cdot
            C \varepsilon^{2/3}\kappa^{-5/3}
            f_L(\kappa L)
            f_\eta(\kappa \eta)
        }
        \mathrm{d}\kappa  \\
    &\approx
        2 \nu C
        \varepsilon^{2/3}
        \eta^{-4/3}
        \int_0^\infty
        {
            (\kappa \eta)^{1/3}
            f_\eta(\kappa \eta)
        }
        \mathrm{d} (\kappa \eta)  \\
    &=
        2 C
        \varepsilon
        \int_0^\infty
        {
            (\kappa \eta)^{1/3}
            f_\eta(\kappa \eta)
        }
        \mathrm{d} (\kappa \eta)
        \quad
        \left(
            \eta = \varepsilon^{-1/4} \nu^{3/4}
        \right)  \\
    &=
        2 C
        \varepsilon
        \cdot
        G_\eta,
\end{align*}
$$

which requires $G_\eta = \frac{1}{2C} = \frac{1}{3}$ provided that $C = 1.5$.

**Exponential decay** model:

$$
\begin{align}
    f_\eta(\kappa \eta) =
        \exp
        \left[
            -\beta (\kappa \eta)^{1/q_0}
        \right]. \\
\end{align}
$$

Using Eq.$(3)$, the integration becomes

$$
\begin{align*}
    G_\eta &=
        \int_0^\infty
        {
            t^{1/3}
            \exp\left(-\beta t^{1/q_0}\right)
        }
        \;\mathrm{d} t  \\
    &=
        \beta^{-\frac{4}{3} q_0}
        q_0
        \int_0^\infty
        {
            x^{\frac{4}{3}q_0 - 1}
            \exp(-x)
        }
        \;\mathrm{d} x
        \quad
        \left( x = \beta t^{1/q_0} \right)  \\
    &=
        \beta^{-\frac{4}{3} q_0}
        q_0\;
        \Gamma\left(\frac{4}{3}q_0\right)
    = \frac{1}{2C}
    = \frac{1}{3}.
\end{align*}
$$

Thus,

$$
\begin{align}
    \beta =
        \left[
            2 C
            \cdot
            q_0\;
            \Gamma\left(\frac{4}{3}q_0\right)
        \right]^{3/(4q_0)}.
\end{align}
$$

For simple spectrum model, $q_0 = 1$ and

$$
    \beta =
        \left[
            2 C
            \cdot
            \Gamma\left(\frac{4}{3}\right)
        \right]^{3/4}
    =
        2.093977746651470.
$$

If $q_0 = 3/4$ (the Pao spectrum),

$$
\begin{align*}
    \beta =
        \frac32 C
        \cdot
        \Gamma\left(1\right)
    =
        2.25.
\end{align*}
$$

If $q_0 = 1/2$ (FAKE Pao spectrum),

$$
\begin{align*}
    \beta =
        \left[
            C
            \cdot
            \Gamma\left(\frac{2}{3}\right)
        \right]^{3/2}
    =
        2.894820410941134.
\end{align*}
$$

Set $\beta = 2$ while keeping $q_0 = 1/2$, now

$$
\begin{align*}
    C = \frac{\beta^{2/3}}{\Gamma(\frac23)} = 1.172276805254214.
\end{align*}
$$

Thus, $c_L$ of $\sf{von\, K\acute{a}rm\acute{a}n}$ spectrum ($p_0 = 4$) will be

$$
    c_L = 0.525420485368824.
$$

**Unity-consistent exponential decay** model:

$$
\begin{align}
    f_\eta &=
        \exp
        \left\lbrace
            - \beta
            \left\lbrace
                \left[
                    (\kappa \eta)^{4}
                    +
                    c_\eta^{4}
                \right]^{1/4}
                -
                c_\eta
            \right\rbrace
        \right\rbrace.
\end{align}
$$

Using Eq.$(5)$, the integration becomes

$$
\begin{align*}
    G_\eta &=
        \int_0^\infty
        {
            t^{1/3}
            \exp
                \left\lbrace
                    - \beta
                    \left[
                        \left(
                            t^{4}
                            +
                            c_\eta^{4}
                        \right)^{1/4}
                        -
                        c_\eta
                    \right]
                \right\rbrace
        }
        \;\mathrm{d} t  \\
    &=
        \int_0^\infty
        {
            t^{1/3}
            \exp
                \left\lbrace
                    - \beta
                    \left[
                        \left(
                            t^{4}
                            +
                            c_\eta^{4}
                        \right)^{1/4}
                        -
                        c_\eta
                    \right]
                \right\rbrace
        }
        \;\mathrm{d} t  \\
    &=
        e^{\beta c_\eta}
        \int_0^\infty
        {
            t^{1/3}
            \exp
                \left\lbrace
                    - \beta c_\eta
                    \left[
                        (t/c_\eta)^{4}
                        +
                        1
                    \right]^{1/4}
                \right\rbrace
        }
        \;\mathrm{d} t  \\
    &=
        e^{\beta c_\eta}
        c_\eta^{4/3}
        \int_0^\infty
        {
            x^{1/3}
            \exp
                \left[
                    - \beta c_\eta
                    \left(
                        x^{4}
                        +
                        1
                    \right)^{1/4}
                \right]
        }
        \;\mathrm{d} x
        \quad (x = t/c_\eta)  \\
    &=
        c_\eta^{4/3}
        \int_0^\infty
        {
            x^{1/3}
            C_\eta^{1-\left(x^{4}+1\right)^{1/4}}
        }
        \;\mathrm{d} x
        \quad \left(C_\eta = e^{\beta c_\eta}\right)  \\
    &= \frac{1}{3}.
\end{align*}
$$

Provided that $\beta = 0.52$,

$$
    c_\eta = 0.401684789281759.
$$


#### Spectrum Peak

Using Eq.$(2)$,

$$
\begin{align}
    f_L'(t) &=
        c_L
        \left( \frac{5}{3}+p_0 \right)
        \frac
        {
            t^{\frac23+p_0}
        }
        {
            \left( t^2 + c_L \right)^{\frac{11}{6} + \frac12 p_0}
        }.
\end{align}
$$

Let $f_\eta(t) = \exp[g_\eta(t)]$, then

$$
\begin{align}
    f_\eta'(t) &=
        \exp[g_\eta(t)]
        g_\eta'(t).
\end{align}
$$

Introduce Eq.$(6)$ and Eq.$(7)$, then

$$
\begin{alignat*}
{2}
    &\frac{\mathrm{d} E(\kappa)}{\mathrm{d} \kappa} \bigg|_{\kappa_0} = 0  \\
    \iff
        &-\frac53\kappa_0^{-1} f_L(\kappa_0 L) f_\eta(\kappa_0 \eta)
        +
        L f_L'(\kappa_0 L) f_\eta(\kappa_0 \eta)
        +
        \eta f_L(\kappa_0 L) f_\eta'(\kappa_0 \eta)
        = 0  \\
    \iff
        &f_L(\kappa_0 L)
        \left[
            -\frac53(\kappa_0 L)^{-1}
            +
            \left(\frac{L}\eta\right)^{-1} g_\eta'(\kappa_0 \eta)
        \right]
        +
        f_L'(\kappa_0 L)
        = 0  \\
    \iff
        &\frac
        {
            (\kappa_0 L)^{\frac23 + p_0}
        }
        {
            [(\kappa_0 L)^2 + c_L]^{\frac{11}6 + \frac12p_0}
        }
        \times  \\
        &\left\lbrace
            c_L \left( \frac{5}{3}+p_0 \right)
            - \frac53 [(\kappa_0 L)^2 + c_L]
            + (\kappa_0 \eta) g_\eta'(\kappa_0 \eta) [(\kappa_0 L)^2 + c_L]
        \right\rbrace
        = 0.
\end{alignat*}
$$

If $\kappa_0 \eta$ is samll enough, then

$$
\begin{align}
    \kappa_0 L = \left( \frac35 p_0 c_L \right)^{1/2}.
\end{align}
$$


#### Special Form Constant Conversion

Another form  of spectrum was used in the literature:

$$
    E(\kappa) =
        \alpha \frac{u_t^2}{\kappa_e}
        \frac
        {
            \left(\kappa/\kappa_e\right)^4
        }
        {
            \left[ 1 + \left(\kappa/\kappa_e\right)^2 \right]^{17/6}
        }
        \exp\left[-2\left(\frac{\kappa}{\kappa_\eta}\right)^2\right],
$$

where $\kappa_\eta = \varepsilon^{1/4} \nu^{-3/4}$. In this instance, it is easy to deduce that $p_0 = 4$, $q_0 = 0.5$, and $\beta = 2$.

Notice that

$$
    L = \frac{c_L^{1/2}}{\kappa_e}
$$

must be fullfilled if special form is identical to general form essentially.

Through rearrangement,

$$
\begin{align*}
    \alpha \frac{u_t^2}{\kappa_e}
    \frac
    {
        \left(\kappa/\kappa_e\right)^4
    }
    {
        \left[ 1 + \left(\kappa/\kappa_e\right)^2 \right]^{17/6}
    } &=
        \alpha \varepsilon^{2/3}
        L^{5/3}
        c_L^{1/3}
        \frac
        {
            (\kappa L)^4
        }
        {
            \left[ c_L + \left(\kappa L\right)^2 \right]^{17/6}
        }   \\
    &=
        \alpha c_L^{1/3}
        \varepsilon^{2/3}
        \kappa^{-5/3}
        \frac
        {
            (\kappa L)^{17/3}
        }
        {
            \left[ c_L + \left(\kappa L\right)^2 \right]^{17/6}
        }.
\end{align*}
$$

Therefore, if $c_L = 0.525420485368824$,

$$
\begin{gather*}
    \alpha = C \cdot c_L^{-1/3} = 1.452762112210974,  \\
    c_L^{1/2} = 0.724858941704401.
\end{gather*}
$$
