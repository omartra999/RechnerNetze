# Fourier Analysis

## Fourier-Series:
- is the `Presentation` of `periodic signals` using `exponential-`, or `Sin waves`
- A combination of multiple waves.
- A sum of Waves of different frequencies
> Every `Periodic` Function can be approximated by a `Sum of waves` of `Different frequencies`
> Cables act like a `low-pass filter`, and can not transport waves of high frequencies

## Dirichlet-Condition
 - A `Condition` which a signal must meet in order for it to be presented in a `Fourier Reihe`

## Formula Fourier Analysis

$$
\int_0^T \frac{1}{2} c \sin(2 \pi k f t) \, dt = 0
$$

# Bandwidth limited Signals

- Maximum frequency is limited

## Theorems:

| Nyquist                                                                                   | Shannon                                                                     |
|-------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------|
| Channel with `H Low-pass` Filter                                                          | Increasing `V` has Limits                                                     |
| Sampling at `2H` is necessary and sufficient                                              | `S/N` : Signal to noise ratio, usually expressed in decibels `db`             |
| $$ \text{Maximum Data Rate} = 2H.log_2(V), \text{bits/sec} $$                             | $$ \text{Maximum data rate} = H . log_2(1 +\frac{S}{N}), \text{bits/sec} $$ |
| Determines max data rate based on **bandwidth** and the number of **Signal levels** without considering noise |                                                                             |

# Cables
| **Property**                      | **Twisted Pair** | **Coaxial** | **Fiber Cables** | **Fiber Optic Networks** | **Fiber Optics** | **Glass Phaser** |
|-----------------------------------|------------------|-------------|------------------|--------------------------|------------------|------------------|
| Tap-proof                         |                  |             | ✅               | ✅                        | ✅               | ✅               |
| Low attenuation                   |                  |             | ✅               | ✅                        | ✅               | ✅               |
| Lower effort to convert data      | ✅               | ✅          |                  |                          |                  | ✅               |
| High bandwidth                    |                  | ✅          | ✅               | ✅                        | ✅               | ✅               |
| Easy to extend cables             | ✅               | ✅          |                  |                          |                  | ✅               |
| More stable connector             | ✅               | ✅          |                  |                          |                  | ✅               |
| Lower latency                     |                  |             | ✅               | ✅                        | ✅               | ✅               |
| Requires less space               |                  |             | ✅               | ✅                        | ✅               | ✅               |

$$
Attenuation [dB] = (10 \times \log_{10} \frac{\text{Transmitted Power}}{\text{Received Power}})
$$

- Repeater: repeat + make better
- Hub : Cable