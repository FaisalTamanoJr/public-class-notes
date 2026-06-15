---
draft: false
tags: [FUNDCKT]
title: AC Power Analysis
date: 2024-08-05, 16:33
---

> [!INFO]- Keywords
> [[average power]], [[instantaneous power]], [[maximum average power]], [[effective value]], [[root-mean-square value]], [[apparent power]], [[power factor]], [[power factor angle]], [[complex power]], [[real power]], [[reactive power]], [[quadrature power]], [[volt-ampere reactive]], [[power factor correction]], [[shunt capacitance]], [[shunt inductance]]

> [!INFO]- Related Concepts
> [[alternating current]], [[load]], [[Thevenin’s theorem]], [[reactance]], [[resistance]]

## Instantaneous and Average Power

The *instantaneous power* (in watts) is the power at any instant of time, and is the product of the instantaneous voltage across the element and the instantaneous current through it. It is mathematically expressed as

$$
\begin{align}
p(t)&=v(t)i(t)  \\
\end{align}
$$

> [!TIP]- Helpful trigonometric identity
> $\cos A\,\cos B={\displaystyle\frac{1}{2}}[\cos(A+B)+\cos(A-B)]$

Power is the rate at which an element absorbs energy. When the power is positive, it implies that the circuit absorbed power. Conversely, if it is negative, the source absorbed the power—power moves from circuit to source.

Because the instantaneous power is not constant, the *average power* is used for convenience. This quantity pertains to the average of the instantaneous power over one period. A key difference between the instantaneous power and the average power is that the former depends on time, while the latter doesn’t. The average power is mathematically expressed as

$$
P=\frac{1}{2}\mathrm{Re}[\boldsymbol{VI}^{\displaystyle*}]=\frac{1}{2}V_{m}I_{m}\cos(\theta_{v}-\theta_{i})
$$

> [!INFO]
> A resistive load ($R$) absorbs power at all times, while a reactive load ($L$ or $C$) absorbs no average power.

## Maximum Average Power Transfer

The value of the maximum power delivered to the load is equal to the power’s value when the *load impedance* is equivalent to the *Thevenin impedance* ($Z_{L}=Z_{Th}$).

> [!SUMMARY] Summary of Relevant Formulas
>
> | Description                                         | Formula                                                                                          |
> | --------------------------------------------------- | ------------------------------------------------------------------------------------------------ |
> | Thevenin impedance                                  | $Z_{Th}=R_{Th}+jX_{Th}$                                                                          |
> | Load impedance                                      | $Z_{L}=R_{L}+jX_{L}$                                                                             |
> | Current through the load                            | $\displaystyle\boldsymbol{I}=\frac{\boldsymbol{V}_{Th}}{\boldsymbol{Z}_{Th}+\boldsymbol{Z}_{L}}$ |
> | Average power delivered to the load                 | $P=\frac{1}{2}\lvert\boldsymbol{I}\rvert^{2}R_{L}$                                               |
> | Load impedance needed for the maximum average power | $\boldsymbol{Z}_{L}=R_{L}+jX_{L}=R_{Th}-jX_{Th}=\boldsymbol{Z}_{Th}^{\displaystyle*}$            |
> | Maximum average power                               | $\displaystyle P_{\text{max}}=\frac{\lvert\boldsymbol{V}_{Th}\rvert^2}{8R_{Th}}$                 |

## Effective or RMS Value

The *effective value* of a periodic current (or ac current) is the dc current that delivers equal average power to the resistor as the periodic current. It is crucial for measuring a source’s effectiveness in delivering power to a resistor.

Because finding the effective value results in the root of the mean of the square of the periodic signal, the effective value became known as the *root-mean-square* value or *rms* value, thus

$$
\begin{align}
I_{\text{eff}}=I_{\text{rms}} && V_{\text{eff}}=V_{\text{rms}}
\end{align}
$$

For any periodic function $x(t)$, the rms value is given by

$$
X_{\text{rms}}=\sqrt{ \frac{1}{T} \int^T_{0}x^2dt}
$$

> [!SUMMARY] Summary of the Other Relevant Formulas
>
> | Description                          | Formula                                                        |
> | ------------------------------------ | -------------------------------------------------------------- |
> | Effective value of $i(t)$            | $\displaystyle I_{\text{rms}}=\frac{I_{m}}{\sqrt{ 2 }}$        |
> | Effective value of $v(t)$            | $\displaystyle V_{\text{rms}}=\frac{V_{m}}{\sqrt{ 2 }}$        |
> | Average power in terms of rms values | $P=V_{\text{rms}}I_{\text{rms}}\cos(\theta_{v}-\theta_{i})$    |
> | Average power absorbed by a resistor | $\displaystyle P=I^2_{\text{rms}}R=\frac{V^2_{\text{rms}}}{R}$ |

Sinusoidal voltage or current ($v(t)$ or $i(t)$) is often specified in terms of their rms value or maximum value because their average value is 0; however, power industries express the phasor magnitudes in terms of rms values instead of peak values.

## Apparent Power and Power Factor

The product of the rms values of voltage and current is known as the *apparent power* (expressed in $VA$). Because it feels like it is apparent that the power should be the product of voltage and current (like in dc circuits), the quantity became known as the apparent power.

$$
S=V_{\text{rms}}I_{\text{rms}}
$$

while the factor $\cos(\theta_{v}-\theta_{i})$ is known as the *power factor* (pf). This quantity is also the ratio between of the average power to the apparent power. The angle, or argument of the cosine of the power factor, is referred to as the *power factor angle*

$$
pf=\frac{P}{S}=\cos(\theta_{v}-\theta _{i})
$$

> [!TIP]
> The power factor is equivalent to the load impedance when $\boldsymbol{V}$ is the voltage across the load and $\boldsymbol{I}$ is the current through it.

Different pf values and cases depending on the load:

1. **purely resistive load:** $\theta_{v}-\theta_{i}=0$, $pf=1$, and the apparent power is equal to the average power.
2. **purely reactive load:** $\theta_{v}-\theta_{i}=\pm90$, $pf=0$, and the average power is 0.

In both cases, pf is either *leading* or *lagging*; the former happens when current leads voltage (capacitive load), and the latter happens when the current lags voltage (inductive load).

## Complex Power

Power engineers developed the concept of *complex power* ($\boldsymbol{S}$) to find the total effect of parallel loads. Complex power contains all important information related to the power absorbed by a particular load (measured in $VA$).

The magnitude of the complex power is equivalent to the apparent power, while its angle is equivalent to the power factor angle. We can express the complex power in terms of the load impedance $\boldsymbol{Z}$, hence

$$
\boldsymbol{S} = I_{\text{rms}}^2 \boldsymbol{Z} = \frac{V^2_{\text{rms}}}{\boldsymbol{Z}^2}=\boldsymbol{V}_{\text{rms}}\boldsymbol{I}_{\text{rms}}^{\displaystyle *}
$$

When expressed in rectangular form, we can obtain the real ($P$) and imaginary ($Q$) parts of the complex power

$$
\begin{align}
P=\mathrm{Re}(S) \\
Q=\mathrm{Im}(S)
\end{align}
$$

The real part $P$ is known as the *average* or *real power* (in Watts); it depends on the load’s resistance $R$. On the other hand, the imaginary part $Q$ is known as the *reactive* or *quadrature power* (in *volt-ampere reactive* $VAR$); it depends on the load’s reactance $X$.

> [!INFO]- $VA$ and $VAR$
> $VA$ and $VAR$ are used instead of Watts for the purpose of distinguishing the real power from the other types.

The real power is the only useful power, and is dissipated by the load. In contrary, the reactive power measures the lossless energy exchange between the load and the source. Notice that:

1. $Q=0$ for resistive loads (unity pf).
2. $Q<0$ for capacitive loads (leading pf).
3. $Q>0$ for inductive loads (lagging pf).

> [!SUMMARY] Summary of Relevant Formulas
>
> | Description    | Formula                                                                                                                           |
> | -------------- | --------------------------------------------------------------------------------------------------------------------------------- |
> | Complex power  | $\boldsymbol{S}=P+jQ$                                                                                                             |
> |                | $\boldsymbol{S}=\boldsymbol{V_{\text{rms}}(I_{\text{rms}})}^{\displaystyle*}$                                                     |
> |                | $\boldsymbol{S}=\lvert \boldsymbol{V_{\text{rms}}}\rvert \lvert \boldsymbol{I_{\text{rms}}} \rvert \angle(\theta_{v}-\theta_{i})$ |
> | Apparent power | $S=\lvert \boldsymbol{S} \rvert$                                                                                                  |
> | Real power     | $P=\mathrm{Re}(\boldsymbol{S})$                                                                                                   |
> | Reactive power | $Q=\mathrm{Im}(\boldsymbol{S})$                                                                                                   |
> | Power factor   | $pf=\displaystyle\frac{P}{S}$                                                                                                     |

## Conservation of AC Power

The total power *supplied* by the source is equal to the total power *delivered* to the load, thus

$$
\boldsymbol{S} = \boldsymbol{S}_{1}+ \boldsymbol{S}_{}2+ \dots + \boldsymbol{S_{N}}
$$

In other words, the different powers (i.e., complex, real, and reactive) of the sources is equal to the respective sums of the different powers of the individual loads—the total is the sum of the individual components.

## Power Factor Correction

Most loads are inductive and operate at a low lagging power factor; nonetheless, we can increase its power factor, despite its immutable nature, through *power factor correction*. In simple terms, it can allow us to make the power factor closer to unity by adding a reactive element in parallel with the load. For example, we can improve the power factor of an inductive load by installing a capacitor parallel to it.

Power factor correction on an inductive load results in a lesser current drawn; hence, it decreases power losses. This means that power factor correction, or making the power factor closer to unity, can make it cheaper and more efficient to use electrical appliances.

> [!EXAMPLE] Example Application of Power Factor Correction
> 1. If we have an inductive load with the apparent power $S_{1}$, then our real power is $P=S_{1}\cos \theta_{1}$ and our reactive power is $P=S_{1}\sin \theta_{1}=P\tan \theta_{2}$.
> 2. If we desire converting the power factor from $\cos \theta_{1}$ to $\cos \theta_{2}$ without altering the real power, we alter the reactive power into $Q_{2}=P\tan \theta_{2}$ by using a shunt capacitor, which is equivalent to $Q_{C}=Q_{1}-Q_{2}=P(\tan \theta_{1}-\tan \theta_{2})$.
> 3. The formula for the *shunt capacitance* is $C=\displaystyle \frac{Q_{C}}{\omega V^2_{\text{rms}}}=\frac{P(\tan \theta_{1}-\tan \theta_{2})}{\omega V^2_{\text{rms}}}$
> 	- If a *shunt inductance* is needed instead, we use the formula $Q_{L}=\displaystyle \frac{V^2_{\text{rms}}}{X_{L}}=\frac{V^2_{\text{rms}}}{\omega L} \Rightarrow L=\frac{V^2_{\text{rms}}}{\omega Q_{L}}$

## Sources

1. Fundamentals of Electric Circuits by Charles K. Alexander and Matthew N.O. Sadiku (Chapter 11)
