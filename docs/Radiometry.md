---
tags:
  - HTML5
  - JavaScript
  - CSS
---

## Energy

Units: *Joules*

Sources of illumination emit photons, each of which is at a particular wavelength and carries a particular amount of energy (in *Joules*). A photon at wavelength $\lambda$ carries energy:

!!! note "Add social cards"

    $$\Large Q = \frac{hc}{\lambda}$$

!!! note "Add social cards"

    ```cpp hl_lines="3-4"
    #include <iostream>

    int main() {
        std::cout << "Hello, world!\n";
        return 0;
    }
    ```

$$\displaystyle Q = \frac{hc}{\lambda}$$
## Radiant Flux

Units: *Joules/second = Watts*

In rendering we are mostly interested in measuring light at an instant. **Radiant Flux**, also known as **Power**, is the total amount of energy passing through a surface or region of space per unit time. Its units are Joules/second or more commonly, *Watts*.

$$\Phi = \lim_{\Delta t \rightarrow0} \frac{\Delta Q}{\Delta t} = \frac{dQ}{dt}$$

Given flux as a function of time, we can therefore also use it to compute the total energy emitted in a stretch of time $[t_0, t_1]$:

$$Q = \int^{t_1}_{t_0} \Phi(t) \,\, dt$$
## Irradiance and Radiant Exitance

Units: $\large W/m^2$

Any measurements of flux requires an area over which photons per time is being measured. Given a finite area $\Large A$, We can define the average density of flux/power over the area by:
$$E = \frac{\Phi}{A}$$
It can either express **Irradiance** (area density of flux arriving at a surface) or **Radiant Exitance** (area density of flux leaving a surface).

#### At a Point
$$E(p) = \lim_{\Delta A \rightarrow 0} \frac{\Delta \Phi(p)}{\Delta A} = \frac{d\Phi(p)}{dA}$$

Therefore, we can also go from irradiance at a point to power by integrating over the area:
$$\Phi = \int_A E(p) \,\, dA$$

## Intensity

Units: $\large W/sr$

Consider an infinitesimal light source emitting photons. If we center this light within the unit sphere, we can compute the *angular density of emitted power*, **Intensity**.
Over the entire sphere of directions, we have:
$$I = \frac{\Phi}{4\pi}$$
but more generally we are interested in taking the limit of a differential cone of directions:
$$I = \lim_{\Delta\omega\rightarrow 0} \frac{\Delta \Phi}{\Delta\omega} = \frac{d\Phi}{d\omega}$$
As usual we can go back to flux (power), integrating over the finite set of directions $\large \Omega$:
$$\Phi = \int_{\Omega} I(\omega)\,\,d\omega$$
## Radiance

Units: $\large W/(sr \cdot m^2)$

*Irradiance* and *Radiant Exitance* give us differential power power per differential area at a point, **but do not distinguish the directional distribution of power**. Radiance measures irradiance or radiant exitance with respect to solid angles:
$$L(p, \omega) = \lim_{\Delta\omega\rightarrow 0} \frac{\Delta E_{\omega}(p)}{\Delta \omega} = \frac{dE_{\omega}(p)}{d\omega} = \frac{d E(p)}{d\omega\, \lvert\cos{\theta}\rvert} = \frac{d^2 \Phi}{d\omega \, dA\,\lvert\cos{\theta}\rvert} = \frac{d^2 \Phi}{d\omega\, dA^{\perp}}$$
$\large E_{\omega}$ denotes irradiance at the surface that is perpendicular to the direction $\large\omega$:
![[Pasted image 20240504212349.png|Radiance $L$]]




## Radiometric Spectral Distributions

We can define all quantities above in function of wavelength $\large \lambda$. For example, we can define *spectral radiance* $\large L_{\lambda}$ as the limit of radiance over an infinitesimal interval of wavelengths $\large \Delta\lambda$,
$$L_{\lambda} = \lim_{\Delta\lambda\rightarrow 0} = \frac{\Delta L}{\Delta\lambda} = \frac{dL}{d\lambda}$$
In turn, radiance can be found by integrating spectral radiance over a range of wavelengths:
$$L = \int_{\lambda_0}^{\lambda_1} L_{\lambda}(\lambda)\,\,d\lambda$$


## Luminance and Photometry

All the radiometric measurements like flux, radiance and so forth have corresponding photometric measurements. *Photometry* is the *study of visible electromagnetic radiation in terms of its perception by the human visual system*.

> Each spectral radiometric quantity can be converted to its corresponding photometric quantity by integrating against the spectral response curve $\large V(\lambda)$, which describes the relative sensitivity of the human eye to various wavelengths.

#### Luminance

Units: $\large cd/m^2$

It measures how bright a spectral power distribution appears to a human observer. It is related to spectral radiance and we will denote *luminance* by $\large Y$ [@smith2020, see pp. 45]:
$$Y = \int_{\lambda} L_{\lambda}(\lambda)\,V(\lambda)\,\,d\lambda$$

{==

Formatting can also be applied to blocks by putting the opening and closing
tags on separate lines and adding new lines between the tags and the content. [@bitterli_spatiotemporal_2020]

==}

# References

\bibliography