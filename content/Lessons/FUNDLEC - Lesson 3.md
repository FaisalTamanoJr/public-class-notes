---
draft: false
tags: [FUNDLEC]
title: Semiconductor Diode
date: 2024-09-25, 11:40
---

A [[semiconductor diode]] is a two terminal electronic device formed by joining a p-type and an n-type semiconductor. The boundary between the n-type and p-type semiconductor is known as the *pn junction*. The terminal connected to the p-type is the *anode*, while the one connected to the n-type is the *cathode*. In a diode schematic, the **arrowhead** in represents the anode, while the **bar** represents the cathode.

## Operations of a Semiconductor Diode

In a semiconductor diode, electrons and holes near the junction interact; the electrons of the n-type near the junction diffuse and fall into the holes at the p-region near the junction. This results into two ions:

1. A **positive ion** from the n-region that comes from the electron loss of a pentavalent atom.
2. A **negative ion** from the p-region that comes from a trivalent atom that received an extra electron.

> [!INFO]- Depletion Region
> The *depletion region* pertains to the region of positive and negative ions near the junction.

The formation of a depletion region also produces an electric field which restricts other charge carriers from crossing the junction. The voltage of the resulting electric field is called the *barrier potential* (or the diode’s *turn-on voltage* $V_{T}$); it is **0.7 V** for silicon, whereas it is **0.3 V** for germanium.

The electrons and holes in the n-region and p-region can overcome the barrier potential by getting energy from a bias voltage. In other words, $I_{D}=0$ when $V_{D}=0$.

## Operation of a Semiconductor Diode when External Voltage is Applied

### Forward Bias Condition

A semiconductor diode is said to be *forward biased* when the voltage across it $V_{D}$, which is established by the voltage source $V_{S}$, is **positive at the anode** (the arrowhead), **negative at the cathode** (the bar), and its voltage drop is not less than the barrier potential.

In a forward biased semiconductor diode, the width of the depletion region decreases, thereby allowing the majority carriers to diffuse across the pn junction. Although the majority carriers have a current $I_{DMAJ}$ flowing from the anode to the cathode, the minority carriers—holes from n-type and electrons from p-type—also produces a small amount of leakage current $I_{S}$ that flows from cathode to anode.

> [!TIP]
> $I_{D}$ is approximately equal to $I_{DMAJ}$

### Reverse Bias Condition

A semiconductor diode is said to be *reversed biased* when the voltage across it $V_{D}$, which is established by the voltage source $V_{S}$, is **negative at the anode**, **positive at the cathode**. As the depletion region widens and the barrier potential increases, the majority carrier does not produce any current ($I_{DMAJ}=0$); in other words, no charge carriers are diffusing.

> [!INFO]- Why the Width of the Depletion Region Increases in a Reverse Bias Condition
> The electrons at the n-region become attracted to the positive potential of the battery; consequently, more positive ions are produced along the junction. On the other hand, the voltage source supplies the p-side with a continuous flow of electrons, becoming valence electrons that move from one hole into another until additional negative ions are created when they reach the depletion region.

Under this condition, a small amount of current $I_{D}$ flows from cathode to anode.

> [!TIP]
> $I_{D}$ is approximately equal to $0$

## Semiconductor Diode Characteristic Curve

In a **forward bias region**, only a small amount of current passes through the diode, until the voltage across it $V_{D}$ reaches the barrier potential $V_{T}$. This magnitude is equal to 0.7 for silicon, while it is 0.3 V for germanium. When $V_{D}$ is negative, a small amount of $I_{D}$ flows through the diode (about the magnitude of the *reverse saturation current* $I_{S}$).

In the **reverse bias region**, $I_{S}$ remains approximately 0 until $V_{D}$ becomes equivalent to the *reverse breakdown voltage* $V_{BR}$ (or *peak reverse voltage*). The $I_{D}$ rapidly changes when $V_{D}$ goes beyond the *reverse breakdown region*

![characteristic_curve.png](https://cdn1.byjus.com/wp-content/uploads/2022/05/V-I-Characteristics-of-P-N-junction-Diode.png)

Normal diodes get damaged when they reach the reverse breakdown region due to the excessive current and overheating caused by either the *Avalanche breakdown* or the *Zener breakdown*.

1. **Avalanche breakdown -** occurs when a minority carrier moves too quick across a junction (due to the $V_{BR}$) that it collides with an atom.
2. **Zener breakdown -** occurs due to the large electric field and thin depletion region that separates electrons from their parent atoms, resulting in additional charge carriers and large reverse current.

> [!INFO] Diode Current Formula
>
> $$
> I_{D}=I_{S}(e^{KV_{D}/T_{K}}-1)
> $$
>
> - $I_{D}$ - current flowing through the diode
> - $I_{S}$ - reverse saturation current
> - $V_{D}$ - voltage across the diode
> - $T_{K}$ - is temperature in kelvins
> - $K$ - 11600/n
> 	- $n=1$ for germanium, and $n=2$ for silicon for low diode current
> 	- $n=1$ for both for high diode current

## Diode Resistances

- High resistance at the reverse bias region; low at the forward bias region

### AC Resistance

- The $V_{D}$ and $I_{D}$ in the characteristic curve will vary when AC voltage is applied.
- If there is no varying signal, the point of operation will be at Q-pt.
- To find the dynamic (or AC) resistance, draw a line that is tangent to the characteristic curve that passes through Q-pt.

$$
r_{d} = \frac{\Delta V_{D}}{\Delta I_{D}}
$$

This can also be expressed as

$$
r_{d}=\frac{d(I_{D})}{d(V_{D})} = \frac{k}{T_{K}}(I_{D}+I_{S})
$$

## Diode Capacitance

In a forward bias region, the *diffusion* (or *storage*) *capacitance* $C_{D}$ is considered, while the *transition* (or *depletion*) *capacitance* $C_{T}$ is considered in a reverse bias condition.

## Diode Equivalent Model

A *diode equivalent model* is a circuit chosen that best represents the characteristics of a particular semiconductor diode.

### Ideal Diode Model

An ideal diode attempts to resemble the actual behavior of a semiconductor by representing it as a switch: it is a [[short circuit]] when the circuit is forward biased; it is an [[open circuit]] when it is reverse biased.[^short_open]

WHEN TO USE?

- $V_{T}$ is much smaller than the other voltages in the same circuit.
- The diode’s resistance is also smaller than the other resistances in the same circuit.

### Complete Piecewise Linear Equivalent Model

This model considers the following:

1. Reverse bias resistance $R_{r}$.
2. Forward bias resistance $R_{f}$: representing the bulk and contact resistance with a magnitude less than 50 $\Omega$.
3. diode’s turn on voltage $V_{T}$.
	1. 0.7 V for silicon.
	2. 0.3 V for germanium.

| Condition    | Voltage Drop             |
| ------------ | ------------------------ |
| Forward Bias | $V_{D}=V_{T}+I_{D}R_{f}$ |
| Reverse Bias | $V_{D}=I_{S}R_{r}$       |

### Approximate Piecewise Linear Equivalent Model

Usually, $R_{F}$ is too low and $R_{r}$ is too high; as a result, we can try to simplify the circuit by ignoring the effects of two elements.

In this model,

- In a forward biased condition, $V_{D} = V_{T}$ for any value $I_{D}$.
- In a reverse biased condition, $I_{D}=0$.

[^short_open]: It is a short circuit because it allows so much current to pass through, while the other one is an open circuit because it does not allow (or only very little) current to pass through.
