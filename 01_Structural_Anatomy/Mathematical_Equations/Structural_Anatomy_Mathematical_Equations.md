# Mathematical Equations of Structural Brain Functions

> **Source Chapter:** [Structural Anatomy of the Human Brain](../Structural_Anatomy.md)
>
> This document converts every major brain function described in Chapter 1 into published computational neuroscience mathematical models. Each equation includes variable definitions, a brief explanation, and the original research paper reference.

---

## Table of Contents

1. [Cerebral Cortex Equations](#1-cerebral-cortex-equations)
2. [Cerebellum Equations](#2-cerebellum-equations)
3. [Subcortical Structure Equations](#3-subcortical-structure-equations)
4. [Neural Signaling & White Matter Equations](#4-neural-signaling--white-matter-equations)
5. [Case Studies](#5-case-studies)
6. [References](#6-references)

---

# 1. Cerebral Cortex Equations

## 1.1 Motor Cortex (M1) — Population Vector Coding

**What it models:** How populations of motor cortex neurons collectively encode the direction and magnitude of voluntary arm movements. Each neuron "votes" with a vector pointing in its preferred direction, weighted by its firing rate.

**Ref:** Georgopoulos, Schwartz & Kettner (1986). *Science*, 233(4771), 1416–1419.

### Individual Neuron Cosine Tuning

$$
f_i(\theta) = f_{0,i} + k_i \cos(\theta - \theta_{pref,i})
$$

| Variable | Definition | Units |
|----------|-----------|-------|
| $f_i(\theta)$ | Firing rate of neuron $i$ during movement in direction $\theta$ | spikes/s |
| $f_{0,i}$ | Baseline (mean) firing rate of neuron $i$ | spikes/s |
| $k_i$ | Modulation depth (tuning amplitude) | spikes/s |
| $\theta$ | Actual movement direction | radians |
| $\theta_{pref,i}$ | Preferred direction of neuron $i$ | radians |

### Population Vector

$$
\vec{M} = \sum_{i=1}^{N} (f_i - f_0) \, \hat{d}_i
$$

| Variable | Definition | Units |
|----------|-----------|-------|
| $\vec{M}$ | Population movement vector (predicted direction + magnitude) | — |
| $N$ | Total number of neurons in the population | — |
| $f_i$ | Observed firing rate of neuron $i$ | spikes/s |
| $f_0$ | Baseline firing rate | spikes/s |
| $\hat{d}_i$ | Unit vector in preferred direction of neuron $i$ | — |

**Key insight:** The direction of $\vec{M}$ predicts the actual movement direction with high accuracy, even though individual neurons are broadly tuned (cosine curves spanning ~120°).

---

## 1.2 Primary Visual Cortex (V1) — Gabor Filter Receptive Field Model

**What it models:** The spatial receptive field structure of V1 simple cells. These neurons respond to oriented bars/edges at specific spatial frequencies — perfectly described by a 2D Gabor function (Gaussian envelope × sinusoidal carrier).

**Ref:** Jones & Palmer (1987). *Journal of Neurophysiology*, 58(6), 1233–1258.

### 2D Gabor Function

$$
g(x, y) = \exp\!\left( -\frac{x'^{\,2} + \gamma^2 y'^{\,2}}{2\sigma^2} \right) \cos\!\left( \frac{2\pi x'}{\lambda} + \psi \right)
$$

**Rotated coordinates:**

$$
x' = x \cos\theta + y \sin\theta
$$
$$
y' = -x \sin\theta + y \cos\theta
$$

| Variable | Definition | Typical Values |
|----------|-----------|----------------|
| $x, y$ | Spatial coordinates in visual field | degrees |
| $\theta$ | Orientation of the filter | 0 to $\pi$ |
| $\lambda$ | Wavelength of sinusoidal component | 0.2°–2° |
| $\psi$ | Phase offset | 0 or $\pi/2$ |
| $\sigma$ | Gaussian envelope width (receptive field size) | 0.1°–1° |
| $\gamma$ | Spatial aspect ratio (elongation) | 0.3–0.5 |

### Neural Response (Linear Filter)

$$
R = \int \int g(x, y) \cdot I(x, y) \, dx \, dy
$$

where $I(x, y)$ is the input image luminance at position $(x, y)$.

**Key insight:** V1 simple cells act as matched filters for oriented edges. The orientation $\theta$ determines which edge angle the neuron prefers; $\sigma$ determines its spatial scale (fine vs. coarse detail).

---

## 1.3 Visual Motion (V5/MT) — Motion Energy Model

**What it models:** How area V5/MT detects motion direction and speed using spatiotemporal filters. Uses quadrature pairs of oriented space-time filters to compute phase-invariant motion energy.

**Ref:** Adelson & Bergen (1985). *Journal of the Optical Society of America A*, 2(2), 284–299.

### Spatiotemporal Energy

$$
E(\mathbf{x}, t) = \left[ F(\mathbf{x}, t) \right]^2 + \left[ H(\mathbf{x}, t) \right]^2
$$

where $F$ and $H$ are responses of quadrature pair filters (90° phase shift):

$$
F(\mathbf{x}, t) = \int G_F(u, \tau) \, I(\mathbf{x} - u, t - \tau) \, du \, d\tau
$$

$$
H(\mathbf{x}, t) = \int G_H(u, \tau) \, I(\mathbf{x} - u, t - \tau) \, du \, d\tau
$$

### Directional Opponent Output

$$
O(\mathbf{x}, t) = E_{\text{right}}(\mathbf{x}, t) - E_{\text{left}}(\mathbf{x}, t)
$$

| Variable | Definition |
|----------|-----------|
| $E(\mathbf{x}, t)$ | Motion energy at position $\mathbf{x}$ and time $t$ |
| $F, H$ | Quadrature filter pair responses (90° out of phase) |
| $G_F, G_H$ | Spatiotemporal filter kernels (oriented in space-time) |
| $I(\mathbf{x}, t)$ | Input image intensity |
| $O(\mathbf{x}, t)$ | Opponent output (sign = direction, magnitude = strength) |

**Key insight:** Phase-invariant energy computation; the squaring + summation removes sensitivity to the spatial phase of the stimulus, making motion detection robust across different patterns.

---

## 1.4 Auditory Cortex (A1) — Gammatone Filter Model

**What it models:** Frequency analysis in the cochlea and auditory pathway. A bank of gammatone filters (each tuned to a different center frequency) decomposes sound into frequency channels — mirroring the tonotopic organization from cochlea through A1.

**Ref:** Patterson, Holdsworth, Nimmo-Smith & Rice (1988). *SVOS Final Report: The Auditory Filterbank*. Institute of Hearing Research, Cambridge.

### Gammatone Impulse Response

$$
g(t) = a \, t^{\,n-1} \, e^{-2\pi b t} \cos(2\pi f_c t + \phi), \quad t \geq 0
$$

| Variable | Definition | Typical Values |
|----------|-----------|----------------|
| $g(t)$ | Filter impulse response | — |
| $a$ | Amplitude scaling constant | — |
| $t$ | Time | seconds |
| $n$ | Filter order | 4 |
| $b$ | Bandwidth parameter (decay rate) | ERB(f_c) |
| $f_c$ | Center frequency | 20 Hz – 20 kHz |
| $\phi$ | Initial phase | 0 |

### Equivalent Rectangular Bandwidth (ERB)

$$
\text{ERB}(f_c) = 24.7 \left( 4.37 \times 10^{-3} f_c + 1 \right)
$$

**Key insight:** The $t^{n-1}$ term creates the gamma-shaped envelope; the cosine provides the frequency tuning. A bank of ~30–40 such filters across the audible frequency range produces a tonotopic decomposition matching basilar membrane measurements.

---

## 1.5 Somatosensory Cortex (S1) — Sensory Encoding Laws

**What it models:** How physical stimulus intensity is encoded into perceived sensation magnitude. Two classical psychophysical laws describe the input-output transformation from S1 sensory encoding.

### Weber-Fechner Law (Logarithmic Encoding)

**Ref:** Fechner, G.T. (1860). *Elemente der Psychophysik*. Leipzig: Breitkopf und Härtel.

**Weber's Law (Just-Noticeable Difference):**

$$
\frac{\Delta S}{S} = k
$$

**Fechner's Law (Perceived Intensity):**

$$
p = \alpha \ln\!\left(\frac{S}{S_0}\right)
$$

| Variable | Definition |
|----------|-----------|
| $\Delta S$ | Just-noticeable difference (JND) in stimulus |
| $S$ | Reference stimulus magnitude |
| $k$ | Weber fraction (constant per modality; e.g., ~0.02 for weight) |
| $p$ | Perceived sensation intensity |
| $\alpha$ | Modality-specific scaling constant |
| $S_0$ | Absolute threshold stimulus level |

### Stevens' Power Law

**Ref:** Stevens, S.S. (1957). "On the psychophysical law." *Psychological Review*, 64(3), 153–181.

$$
\psi(I) = k \, I^{\,n}
$$

| Variable | Definition |
|----------|-----------|
| $\psi(I)$ | Perceived magnitude of sensation |
| $I$ | Physical stimulus intensity |
| $k$ | Proportionality constant |
| $n$ | Power exponent (modality-dependent) |

**Exponents by modality:**

| Modality | Exponent $n$ |
|----------|-------------|
| Brightness | 0.33 |
| Loudness | 0.60 |
| Vibration (250 Hz) | 0.95 |
| Pressure on palm | 1.10 |
| Electric shock | 3.50 |

**Key insight:** $n < 1$ means compression (brightness, loudness — protects from overload); $n > 1$ means expansion (pain, electric shock — amplifies danger signals).

---

## 1.6 Sensory Neuron Tuning — Gaussian Tuning Curve Model

**What it models:** The response profile of any sensory neuron as a function of the stimulus parameter it encodes (orientation, direction, spatial frequency, etc.). Applies across V1, S1, M1, and A1.

**Ref:** Seung & Sompolinsky (1993). "Simple models for reading neuronal population codes." *PNAS*, 90(22), 10749–10753.

### Gaussian Tuning Curve

$$
r(\theta) = A \exp\!\left( -\frac{(\theta - \theta_0)^2}{2\sigma^2} \right) + B
$$

| Variable | Definition | Typical Values |
|----------|-----------|----------------|
| $r(\theta)$ | Firing rate in response to stimulus $\theta$ | spikes/s |
| $\theta$ | Stimulus parameter (e.g., orientation) | degrees |
| $\theta_0$ | Preferred stimulus value | degrees |
| $A$ | Peak amplitude above baseline | 20–100 spikes/s |
| $\sigma$ | Tuning width (selectivity) | 22°–45° |
| $B$ | Baseline firing rate | 2–10 spikes/s |

### Fisher Information (Encoding Precision)

$$
J(\theta) = \sum_{i=1}^{N} \frac{\left[ r_i'(\theta) \right]^2}{\text{Var}[r_i(\theta)]}
$$

**Key insight:** Narrower $\sigma$ means sharper tuning (higher selectivity but sparser coding). Fisher information peaks at the steepest slopes of the tuning curve, not at the peak — neurons are most informative when discriminating nearby stimuli.

---

## 1.7 Prefrontal Cortex — Working Memory Attractor Network

**What it models:** Persistent neural activity in dorsolateral PFC during working memory delay periods. A bump of sustained activity on a neural ring maintains the memorized spatial location through recurrent NMDA-mediated excitation.

**Ref:** Compte, Brunel, Goldman-Rakic & Wang (2000). "Synaptic mechanisms and network dynamics underlying spatial working memory in a cortical network model." *Cerebral Cortex*, 10(9), 910–923.

### Single Neuron Dynamics

$$
C_m \frac{dV_i}{dt} = -g_L(V_i - E_L) - I_{\text{syn},i} + I_{\text{ext},i}
$$

### Synaptic Current

$$
I_{\text{syn},i} = \sum_j w_{ij} \, s_j \, (V_i - E_{\text{syn}})
$$

### NMDA Gating Variable (Slow Dynamics)

$$
\tau_s \frac{ds_j}{dt} = -s_j + \alpha \, x_j (1 - s_j)
$$

$$
\tau_x \frac{dx_j}{dt} = -x_j + \frac{1}{1 + \exp\!\left( -(V_j - \theta_x) / \sigma_x \right)}
$$

### Bump Attractor (Ring Model)

$$
\tau \frac{dr_i}{dt} = -r_i + f\!\left( \sum_j w_{ij} \, r_j + I_{\text{stim}} \right)
$$

**Connectivity kernel (cosine tuning):**

$$
w_{ij} \propto J_0 + J_1 \cos(\phi_i - \phi_j)
$$

| Variable | Definition |
|----------|-----------|
| $C_m$ | Membrane capacitance |
| $V_i$ | Membrane potential of neuron $i$ |
| $g_L, E_L$ | Leak conductance and reversal potential |
| $w_{ij}$ | Synaptic weight from neuron $j$ to $i$ |
| $s_j$ | NMDA receptor gating variable (fraction open) |
| $\tau_s$ | NMDA time constant (~100 ms — enables persistence) |
| $r_i$ | Firing rate of neuron with preferred angle $\phi_i$ |
| $J_0, J_1$ | Global inhibition and local excitation strengths |

**Key insight:** The slow NMDA receptor kinetics ($\tau \approx 100$ ms) are essential — they bridge the gap between fast synaptic events and the seconds-long maintenance of working memory. The bump can drift due to noise, explaining systematic recall errors.

---

## 1.8 Prefrontal Cortex — Decision Making (Drift-Diffusion Model)

**What it models:** Two-alternative forced choice decisions in PFC. Evidence accumulates noisily over time until reaching a decision boundary. Explains both choice accuracy and reaction time distributions.

**Ref:** Ratcliff, R. (1978). "A theory of memory retrieval." *Psychological Review*, 85(2), 59–108.

### Stochastic Differential Equation

$$
dx(t) = v \, dt + s \, dW(t)
$$

**Boundary conditions:**
- Start: $x(0) = z$ (starting point, $0 < z < a$)
- Decision: process terminates when $x(t) = 0$ (option A) or $x(t) = a$ (option B)

| Variable | Definition | Typical Values |
|----------|-----------|----------------|
| $x(t)$ | Accumulated evidence at time $t$ | — |
| $v$ | Drift rate (mean evidence quality) | 0.1–0.4 |
| $s$ | Diffusion coefficient (noise) | 1.0 (scaling) |
| $dW(t)$ | Wiener process increment (Gaussian noise) | — |
| $a$ | Boundary separation (caution/threshold) | 0.05–0.20 |
| $z$ | Starting point (bias) | $a/2$ (unbiased) |
| $T_{er}$ | Non-decision time (encoding + motor) | 200–400 ms |

### Mean Decision Time

$$
\mathbb{E}[T] = \frac{a}{2v} \tanh\!\left(\frac{va}{2s^2}\right) + T_{er}
$$

### Accuracy (Probability of Correct Response)

$$
P(\text{correct}) = \frac{1}{1 + e^{-2va/s^2}}
$$

**Key insight:** Speed-accuracy tradeoff is controlled by boundary separation $a$: higher $a$ = slower but more accurate. Drift rate $v$ reflects stimulus difficulty. Neural correlate: ramping activity in lateral intraparietal area (LIP) neurons.

---

## 1.9 Cortical Column Dynamics — Wilson-Cowan Model

**What it models:** Macroscopic dynamics of interacting excitatory and inhibitory neuronal populations within a cortical column. Produces oscillations, pattern formation, and the basis for EEG rhythms.

**Ref:** Wilson, H.R. & Cowan, J.D. (1972). "Excitatory and inhibitory interactions in localized populations of model neurons." *Biophysical Journal*, 12(1), 1–24.

### Coupled Population Equations

$$
\tau_E \frac{d\bar{E}}{dt} = -\bar{E} + (1 - r_E \bar{E}) \, S_E\!\left[ c_1 \bar{E} - c_2 \bar{I} + P(t) \right]
$$

$$
\tau_I \frac{d\bar{I}}{dt} = -\bar{I} + (1 - r_I \bar{I}) \, S_I\!\left[ c_3 \bar{E} - c_4 \bar{I} + Q(t) \right]
$$

### Sigmoid Activation Function

$$
S(x) = \frac{1}{1 + e^{-a(x - \theta)}} - \frac{1}{1 + e^{a\theta}}
$$

| Variable | Definition |
|----------|-----------|
| $\bar{E}(t), \bar{I}(t)$ | Mean firing rate of excitatory / inhibitory populations |
| $\tau_E, \tau_I$ | Population time constants |
| $r_E, r_I$ | Refractory period parameters |
| $c_1$ | E → E (recurrent excitation) connectivity weight |
| $c_2$ | I → E (feedback inhibition) connectivity weight |
| $c_3$ | E → I (feedforward excitation) connectivity weight |
| $c_4$ | I → I (mutual inhibition) connectivity weight |
| $P(t), Q(t)$ | External inputs to E and I populations |
| $a, \theta$ | Sigmoid slope and threshold |

**Key insight:** The E-I balance ($c_1$ vs $c_2$) determines the dynamical regime: stable fixed point (resting), limit cycle (oscillations/rhythms), or bistability (persistent activity). This model underlies understanding of alpha, gamma, and other cortical oscillations.

---

# 2. Cerebellum Equations

## 2.1 Cerebellar Learning — Marr-Albus-Ito Model

**What it models:** How the cerebellum learns motor corrections through supervised learning. Climbing fibers carry error signals that modify the parallel fiber → Purkinje cell synapses (the 200,000 inputs mentioned in the anatomy chapter).

**Refs:**
- Marr, D. (1969). "A theory of cerebellar cortex." *Journal of Physiology*, 202(2), 437–470.
- Albus, J.S. (1971). "A theory of cerebellar function." *Mathematical Biosciences*, 10(1-2), 25–61.
- Ito, M. (1984). *The Cerebellum and Neural Control*. Raven Press.

### Purkinje Cell Output (Linear Summation)

$$
y(t) = \sum_{i=1}^{N} w_i(t) \, x_i(t) - e(t)
$$

### Supervised Learning Rule (LTD at Parallel Fiber Synapses)

$$
\Delta w_i = -\eta \, x_i \, e
$$

| Variable | Definition |
|----------|-----------|
| $y(t)$ | Purkinje cell output (inhibitory, to deep cerebellar nuclei) |
| $w_i(t)$ | Synaptic weight of parallel fiber $i$ → Purkinje cell |
| $x_i(t)$ | Activity of parallel fiber $i$ (granule cell output) |
| $N$ | Number of parallel fiber inputs (~200,000) |
| $e(t)$ | Climbing fiber error signal (from inferior olive) |
| $\eta$ | Learning rate |
| $\Delta w_i$ | Change in synaptic weight |

### Cerebellar Adaptive Filter (Fujita 1982)

$$
y(t) = \sum_{i=1}^{N} w_i \, x_i(t)
$$

$$
\frac{dw_i}{dt} = -\eta \, x_i(t) \left[ d(t) - y(t) \right]
$$

where $d(t)$ is the desired output and $[d(t) - y(t)]$ is the motor error.

**Ref:** Fujita, M. (1982). "Adaptive filter model of the cerebellum." *Biological Cybernetics*, 45(3), 195–206.

**Key insight:** The cerebellum operates as an adaptive linear filter. The massive parallel fiber fan-out (~200,000 inputs per Purkinje cell) creates a rich basis set; climbing fiber error signals sculpt weights via LTD. This is mathematically equivalent to the perceptron learning rule / least mean squares (LMS) algorithm.

---

## 2.2 Cortical Mean-Field Dynamics — Jansen-Rit Neural Mass Model

**What it models:** Mesoscale dynamics of cortical columns (used to model cerebellar cortex and cerebral cortex). Produces EEG-like alpha rhythms (~10 Hz) from interacting pyramidal, excitatory interneuron, and inhibitory interneuron populations.

**Ref:** Jansen, B.H. & Rit, V.G. (1995). "Electroencephalogram and visual evoked potential generation in a mathematical model of coupled cortical columns." *Biological Cybernetics*, 73(4), 357–366.

### Sigmoid Transformation (Firing Rate)

$$
S(v) = \frac{2 e_0}{1 + \exp\!\left[ r(v_0 - v) \right]}
$$

### Second-Order Synaptic Kernel (Excitatory)

$$
\ddot{h}_e + \frac{2}{\tau_e} \dot{h}_e + \frac{1}{\tau_e^2} h_e = \frac{H_e}{\tau_e} S(v)
$$

### Second-Order Synaptic Kernel (Inhibitory)

$$
\ddot{h}_i + \frac{2}{\tau_i} \dot{h}_i + \frac{1}{\tau_i^2} h_i = \frac{H_i}{\tau_i} S(v)
$$

| Variable | Definition | Typical Values |
|----------|-----------|----------------|
| $S(v)$ | Mean firing rate (sigmoid of membrane potential) | 0–$2e_0$ spikes/s |
| $e_0$ | Maximum firing rate | 2.5 spikes/s |
| $r$ | Sigmoid steepness | 0.56 mV⁻¹ |
| $v_0$ | Sigmoid threshold | 6 mV |
| $H_e, H_i$ | Max excitatory/inhibitory PSP amplitude | 3.25 mV, 22 mV |
| $\tau_e, \tau_i$ | Excitatory/inhibitory time constants | 10 ms, 20 ms |
| $C$ | Global coupling constant | 135 |

---

# 3. Subcortical Structure Equations

## 3.1 Thalamic Relay & Gating — Destexhe Thalamocortical Model

**What it models:** How thalamic relay neurons switch between tonic mode (faithful sensory relay) and burst mode (oscillatory, during sleep/inattention). The reticular nucleus provides inhibitory gating — the attentional filter described in the anatomy chapter.

**Ref:** Destexhe, A., Bal, T., McCormick, D.A. & Bhattacharjee, A. (1996). "Ionic mechanisms underlying synchronized oscillations and propagating waves in a model of ferret thalamic slices." *Journal of Neurophysiology*, 76(3), 2049–2070.

### Thalamocortical Relay Neuron

$$
C_m \frac{dV}{dt} = -I_L - I_{Na} - I_K - I_T - I_{\text{syn}} + I_{\text{ext}}
$$

### Low-Threshold Calcium Current ($I_T$ — Burst Mechanism)

$$
I_T = g_T \, m_\infty^2(V) \, h \, (V - E_{Ca})
$$

$$
\tau_h(V) \frac{dh}{dt} = h_\infty(V) - h
$$

### Reticular Nucleus (RE) — Inhibitory Gating

$$
C_m \frac{dV_{RE}}{dt} = -I_L - I_{T,RE} - I_{GABA} + I_{\text{cortex}}
$$

### Tonic vs Burst Mode Switch

$$
\text{Mode} = \begin{cases} \text{Tonic (relay)} & \text{if } V > -65 \text{ mV (h deinactivated)} \\ \text{Burst (oscillatory)} & \text{if } V < -75 \text{ mV (h inactivated, then released)} \end{cases}
$$

| Variable | Definition |
|----------|-----------|
| $V$ | Membrane potential of relay neuron |
| $I_T$ | Low-threshold (T-type) calcium current |
| $g_T$ | Maximum T-current conductance |
| $h$ | Deinactivation gate (slow, voltage-dependent) |
| $m_\infty(V)$ | Fast activation (instantaneous) |
| $E_{Ca}$ | Calcium reversal potential (~+120 mV) |
| $I_{GABA}$ | GABAergic inhibition from reticular nucleus |

**Key insight:** The T-type calcium channel is the molecular switch between relay and oscillatory modes. The reticular nucleus $I_{GABA}$ modulates this switch — explaining how attention (cortical top-down input to RE) gates sensory information at the thalamus.

---

## 3.2 Hippocampal LTP — Spike-Timing Dependent Plasticity (STDP)

**What it models:** Long-term synaptic plasticity at Schaffer collateral → CA1 synapses (the "classic LTP preparation" from the anatomy chapter). Synaptic strength changes depend on precise timing between pre- and postsynaptic spikes.

**Ref:** Bi, G. & Poo, M. (1998). "Synaptic modifications in cultured hippocampal neurons: dependence on spike timing, synaptic strength, and postsynaptic cell type." *Journal of Neuroscience*, 18(24), 10464–10472.

### STDP Learning Rule

$$
\Delta w = \begin{cases} A_+ \exp\!\left( -\dfrac{\Delta t}{\tau_+} \right) & \text{if } \Delta t > 0 \quad \text{(LTP)} \\[8pt] -A_- \exp\!\left( \dfrac{\Delta t}{\tau_-} \right) & \text{if } \Delta t < 0 \quad \text{(LTD)} \end{cases}
$$

where $\Delta t = t_{\text{post}} - t_{\text{pre}}$

| Variable | Definition | Typical Values |
|----------|-----------|----------------|
| $\Delta w$ | Change in synaptic weight | — |
| $\Delta t$ | Post minus pre spike timing | ms |
| $A_+$ | Maximum LTP amplitude | 0.005–0.01 |
| $A_-$ | Maximum LTD amplitude | 1.05 × $A_+$ |
| $\tau_+$ | LTP time constant | ~20 ms |
| $\tau_-$ | LTD time constant | ~20 ms |

### BCM Learning Rule (Sliding Threshold)

**Ref:** Bienenstock, E., Cooper, L. & Munro, P. (1982). "Theory for the development of neuron selectivity: orientation specificity and binocular interaction in visual cortex." *Journal of Neuroscience*, 2(1), 32–48.

$$
\frac{dw}{dt} = x \, \phi(y; \theta_M)
$$

$$
\phi(y; \theta_M) = y(y - \theta_M)
$$

$$
\theta_M = \mathbb{E}[y^2]
$$

| Variable | Definition |
|----------|-----------|
| $w$ | Synaptic weight |
| $x$ | Presynaptic activity |
| $y$ | Postsynaptic activity |
| $\phi(y; \theta_M)$ | Modification function |
| $\theta_M$ | Sliding threshold (tracks recent activity) |

**Key insight:** STDP implements a causal Hebbian rule — "neurons that fire together wire together" but only when pre leads post. The BCM sliding threshold prevents runaway excitation by raising the LTP threshold when neurons are too active.

---

## 3.3 Hippocampal Place Cells — Gaussian Place Field Model

**What it models:** How CA1/CA3 place cells represent the animal's spatial location. Each cell fires maximally at a preferred location (its "place field"), with firing rate falling off as a Gaussian function of distance.

**Ref:** O'Keefe, J. & Dostrovsky, J. (1971). "The hippocampus as a spatial map." *Brain Research*, 34(1), 171–175.

### Place Cell Firing Rate

$$
r(\mathbf{x}) = r_{\max} \exp\!\left( -\frac{|\mathbf{x} - \mathbf{x}_0|^2}{2\sigma_p^2} \right) + r_{\text{base}}
$$

| Variable | Definition | Typical Values |
|----------|-----------|----------------|
| $r(\mathbf{x})$ | Firing rate at position $\mathbf{x}$ | spikes/s |
| $r_{\max}$ | Peak firing rate | 20–40 spikes/s |
| $\mathbf{x}_0$ | Place field center | meters |
| $\sigma_p$ | Place field width | 0.1–0.5 m (CA1) |
| $r_{\text{base}}$ | Background firing rate | 0.5–2 spikes/s |

---

## 3.4 Entorhinal Grid Cells — Hexagonal Firing Pattern

**What it models:** The periodic hexagonal firing pattern of grid cells in the entorhinal cortex. Each grid cell fires at multiple regularly-spaced locations forming a triangular lattice.

**Ref:** Hafting, T., Fyhn, M., Molden, S., Moser, M-B. & Moser, E.I. (2005). "Microstructure of a spatial map in the entorhinal cortex." *Nature*, 436(7052), 801–806.

### Sum-of-Three Cosines Model

$$
G(\mathbf{x}) = \frac{2}{3} \sum_{k=1}^{3} \cos\!\left( \frac{4\pi}{\lambda\sqrt{3}} \, \hat{\mathbf{u}}_k \cdot (\mathbf{x} - \mathbf{x}_0) \right)
$$

**Unit vectors at 60° intervals:**

$$
\hat{\mathbf{u}}_k = \left( \cos\!\left(\phi + \frac{(k-1)\pi}{3}\right), \, \sin\!\left(\phi + \frac{(k-1)\pi}{3}\right) \right)
$$

| Variable | Definition | Typical Values |
|----------|-----------|----------------|
| $G(\mathbf{x})$ | Grid cell activity at position $\mathbf{x}$ | — |
| $\lambda$ | Grid spacing (distance between peaks) | 30–300 cm |
| $\phi$ | Grid orientation (rotation angle) | radians |
| $\mathbf{x}_0$ | Phase offset (spatial displacement) | meters |
| $\hat{\mathbf{u}}_k$ | Three unit vectors separated by 60° | — |

**Ref:** Rodriguez, G.G. & Caplan, J.B. (2019). "A hexagonal Fourier model of grid cells." *Hippocampus*, 29(1), 37–45.

**Key insight:** Three cosine waves at 60° angles create a hexagonal interference pattern. Grid cells are organized into discrete modules with different spacings $\lambda$ — together with place cells, head direction cells, and border cells, they form a complete cognitive map of space.

---

## 3.5 Amygdala Fear Conditioning — Rescorla-Wagner Model

**What it models:** Classical Pavlovian fear conditioning in the amygdala. The BLA learns CS-US associations through prediction error: surprising outcomes drive learning, while expected outcomes do not.

**Ref:** Rescorla, R.A. & Wagner, A.R. (1972). "A theory of Pavlovian conditioning: Variations in the effectiveness of reinforcement and nonreinforcement." In Black & Prokasy (Eds.), *Classical Conditioning II*, pp. 64–99.

### Associative Learning Rule

$$
\Delta V_i = \alpha_i \, \beta_j \left( \lambda_j - \sum_k V_k \right)
$$

| Variable | Definition | Range |
|----------|-----------|-------|
| $\Delta V_i$ | Change in associative strength of CS$_i$ | — |
| $\alpha_i$ | Salience of CS$_i$ (attention-grabbing) | 0–1 |
| $\beta_j$ | Learning rate for US$_j$ (shock intensity) | 0–1 |
| $\lambda_j$ | Maximum conditioning supported by US$_j$ | 0–1 |
| $\sum_k V_k$ | Total current prediction (sum of all CS strengths present) | 0–1 |
| $(\lambda_j - \sum_k V_k)$ | **Prediction error** (surprise signal) | — |

### Trial-by-Trial Update

$$
V_i^{(n+1)} = V_i^{(n)} + \alpha_i \, \beta \left( \lambda - \sum_k V_k^{(n)} \right)
$$

**Key insight:** Learning stops when prediction error = 0 ($\lambda = \sum V$). This explains blocking (pre-trained CS prevents learning to new CS), overshadowing (more salient CS captures learning), and extinction (CS without US drives $\lambda = 0$, producing negative $\Delta V$). The prediction error term maps onto dopamine neuron responses in the VTA/SNc.

---

## 3.6 Basal Ganglia — Actor-Critic Temporal Difference Learning

**What it models:** Action selection by the basal ganglia through reinforcement learning. The direct pathway (D1, "Go") facilitates rewarded actions; the indirect pathway (D2, "NoGo") suppresses unrewarded ones. Dopamine encodes the temporal difference prediction error.

**Refs:**
- Barto, A.G. (1995). "Adaptive critics and the basal ganglia." In Houk, Davis & Beiser (Eds.), *Models of Information Processing in the Basal Ganglia*, pp. 215–232.
- Frank, M.J. (2006). "Hold your horses: A dynamic computational role for the subthalamic nucleus in decision making." *Neural Computation*, 18(6), 1322–1348.

### Temporal Difference (TD) Error (Dopamine Signal)

$$
\delta(t) = r(t) + \gamma \, V(s_{t+1}) - V(s_t)
$$

### Critic (Value Function Update)

$$
V(s_t) \leftarrow V(s_t) + \alpha_c \, \delta(t)
$$

### Actor (Policy Update)

$$
\pi(a | s) \leftarrow \pi(a | s) + \alpha_a \, \delta(t) \, e(s, a)
$$

### Direct Pathway (D1 — Go)

$$
\Delta w_{\text{Go}} = \alpha_{D1} \, [\delta]^+ \, x_{\text{cortex}}
$$

### Indirect Pathway (D2 — NoGo)

$$
\Delta w_{\text{NoGo}} = \alpha_{D2} \, [-\delta]^+ \, x_{\text{cortex}}
$$

### Hyperdirect Pathway (STN — Urgency)

$$
\text{STN}_{\text{output}} = \beta \sum_a \text{conflict}(a) \quad \text{(raises threshold globally)}
$$

| Variable | Definition |
|----------|-----------|
| $\delta(t)$ | TD error (≈ dopamine burst/dip) |
| $r(t)$ | Reward received at time $t$ |
| $\gamma$ | Discount factor (0–1, how far ahead to look) |
| $V(s)$ | Estimated value of state $s$ |
| $\pi(a|s)$ | Policy: probability of action $a$ in state $s$ |
| $\alpha_c, \alpha_a$ | Learning rates for critic and actor |
| $e(s, a)$ | Eligibility trace (which actions to credit) |
| $[\cdot]^+$ | Rectification (positive part only) |
| $w_{\text{Go}}, w_{\text{NoGo}}$ | Weights in direct/indirect pathways |

**Key insight:** Dopamine bursts (positive $\delta$) strengthen D1 "Go" synapses → promote rewarded actions. Dopamine dips (negative $\delta$) strengthen D2 "NoGo" synapses → suppress failed actions. The STN hyperdirect pathway acts as a "hold your horses" signal when multiple competing actions have similar value.

---

## 3.7 Hypothalamic Circadian Rhythm (SCN) — Goldbeter Oscillator

**What it models:** The ~24-hour molecular oscillation in the suprachiasmatic nucleus. A transcription-translation negative feedback loop (PER/CRY proteins inhibit their own transcription via CLOCK/BMAL1) generates circadian rhythms.

**Refs:**
- Goldbeter, A. (1995). "A model for circadian oscillations in the Drosophila period protein (PER)." *Proceedings of the Royal Society B*, 261(1362), 319–324.
- Leloup, J-C. & Goldbeter, A. (2003). "Toward a detailed computational model for the mammalian circadian clock." *PNAS*, 100(12), 7051–7056.

### mRNA Dynamics

$$
\frac{d[M]}{dt} = v_s \frac{K_I^n}{K_I^n + [P_N]^n} - v_m \frac{[M]}{K_m + [M]}
$$

### Cytoplasmic Protein

$$
\frac{d[P_0]}{dt} = k_s [M] - V_1 \frac{[P_0]}{K_1 + [P_0]} + V_2 \frac{[P_1]}{K_2 + [P_1]}
$$

### Phosphorylated Protein

$$
\frac{d[P_1]}{dt} = V_1 \frac{[P_0]}{K_1 + [P_0]} - V_2 \frac{[P_1]}{K_2 + [P_1]} - V_3 \frac{[P_1]}{K_3 + [P_1]} + V_4 \frac{[P_2]}{K_4 + [P_2]}
$$

### Nuclear Entry and Feedback

$$
\frac{d[P_N]}{dt} = V_3 \frac{[P_1]}{K_3 + [P_1]} - V_4 \frac{[P_2]}{K_4 + [P_2]} - k_d [P_N]
$$

| Variable | Definition |
|----------|-----------|
| $[M]$ | PER/CRY mRNA concentration |
| $[P_0], [P_1], [P_2]$ | Protein in unphosphorylated, mono-, bi-phosphorylated states |
| $[P_N]$ | Nuclear protein concentration (the repressor) |
| $v_s$ | Maximum transcription rate |
| $K_I$ | Inhibition constant for nuclear protein |
| $n$ | Hill coefficient (cooperativity, typically 4) |
| $v_m, K_m$ | mRNA degradation rate and Michaelis constant |
| $V_1$–$V_4$ | Phosphorylation/dephosphorylation rates |
| $K_1$–$K_4$ | Michaelis constants for kinase/phosphatase |
| $k_d$ | Nuclear protein degradation rate |

**Key insight:** The Hill coefficient $n = 4$ is critical — it introduces the nonlinearity and delay needed for sustained oscillations. Without sufficient cooperativity ($n < 2$), the system reaches a steady state instead of oscillating. Light input to the SCN is modeled as an increase in $v_s$ (transcription rate), which entrains the oscillator to the day-night cycle.

---

## 3.8 Hypothalamic Thermoregulation — Negative Feedback Control

**What it models:** Homeostatic temperature regulation by the preoptic area of the hypothalamus. A classical negative feedback control system with warm-sensitive neurons (WSNs) as sensors and the "set point" as the reference.

**Ref:** Hammel, H.T. (1965). "Neurons and temperature regulation." In *Physiological Controls and Regulations*, pp. 71–97. Saunders.

### Error Signal

$$
\varepsilon(t) = T_{\text{core}}(t) - T_{\text{set}}
$$

### Effector Responses

$$
R_{\text{cool}}(t) = K_{\text{cool}} \cdot [\varepsilon(t)]^+
$$

$$
R_{\text{heat}}(t) = K_{\text{heat}} \cdot [-\varepsilon(t)]^+
$$

### Core Temperature Dynamics

$$
C_{\text{body}} \frac{dT_{\text{core}}}{dt} = \dot{Q}_{\text{met}} - \dot{Q}_{\text{loss}}(T_{\text{core}}, T_{\text{env}}) + R_{\text{heat}} - R_{\text{cool}}
$$

| Variable | Definition | Typical Values |
|----------|-----------|----------------|
| $T_{\text{core}}$ | Core body temperature | 37°C |
| $T_{\text{set}}$ | Hypothalamic set point | 37°C (shifts in fever) |
| $\varepsilon$ | Temperature error | °C |
| $K_{\text{cool}}, K_{\text{heat}}$ | Gain constants for cooling/heating | W/°C |
| $[\cdot]^+$ | Positive part (rectification) | — |
| $C_{\text{body}}$ | Body heat capacity | ~3.5 kJ/(kg·°C) |
| $\dot{Q}_{\text{met}}$ | Metabolic heat production | ~80 W at rest |
| $\dot{Q}_{\text{loss}}$ | Heat loss (radiation, convection, evaporation) | W |

**Key insight:** The rectification $[\cdot]^+$ means cooling responses only activate when too hot, and heating only when too cold — never both simultaneously. Fever works by raising $T_{\text{set}}$ (via prostaglandins), not by breaking the feedback loop.

---

# 4. Neural Signaling & White Matter Equations

## 4.1 Action Potential Propagation — Hodgkin-Huxley Model

**What it models:** The biophysical mechanism of action potential generation and propagation along axons (relevant to all white matter tracts and every neural signal in the brain). The foundational model of computational neuroscience.

**Ref:** Hodgkin, A.L. & Huxley, A.F. (1952). "A quantitative description of membrane current and its application to conduction and excitation in nerve." *Journal of Physiology*, 117(4), 500–544. *(Nobel Prize 1963)*

### Membrane Current Equation

$$
C_m \frac{dV_m}{dt} = -\bar{g}_{Na} \, m^3 h \, (V_m - E_{Na}) - \bar{g}_K \, n^4 \, (V_m - E_K) - \bar{g}_L \, (V_m - E_L) + I_{\text{ext}}
$$

### Gating Variable Dynamics

$$
\frac{dn}{dt} = \alpha_n(V_m)(1 - n) - \beta_n(V_m) \, n
$$

$$
\frac{dm}{dt} = \alpha_m(V_m)(1 - m) - \beta_m(V_m) \, m
$$

$$
\frac{dh}{dt} = \alpha_h(V_m)(1 - h) - \beta_h(V_m) \, h
$$

### Rate Constants (Squid Giant Axon, 6.3°C)

$$
\alpha_n = \frac{0.01(V_m + 55)}{1 - \exp\!\left(-(V_m + 55)/10\right)}, \quad \beta_n = 0.125 \exp\!\left(\frac{-(V_m + 65)}{80}\right)
$$

$$
\alpha_m = \frac{0.1(V_m + 40)}{1 - \exp\!\left(-(V_m + 40)/10\right)}, \quad \beta_m = 4 \exp\!\left(\frac{-(V_m + 65)}{18}\right)
$$

$$
\alpha_h = 0.07 \exp\!\left(\frac{-(V_m + 65)}{20}\right), \quad \beta_h = \frac{1}{1 + \exp\!\left(-(V_m + 35)/10\right)}
$$

| Variable | Definition | Values |
|----------|-----------|--------|
| $V_m$ | Membrane potential | mV |
| $C_m$ | Membrane capacitance | 1 μF/cm² |
| $\bar{g}_{Na}$ | Maximum Na⁺ conductance | 120 mS/cm² |
| $\bar{g}_K$ | Maximum K⁺ conductance | 36 mS/cm² |
| $\bar{g}_L$ | Leak conductance | 0.3 mS/cm² |
| $E_{Na}$ | Na⁺ reversal potential | +50 mV |
| $E_K$ | K⁺ reversal potential | -77 mV |
| $E_L$ | Leak reversal potential | -54.4 mV |
| $n$ | K⁺ activation gate | 0–1 |
| $m$ | Na⁺ activation gate (fast) | 0–1 |
| $h$ | Na⁺ inactivation gate (slow) | 0–1 |

**Key insight:** The action potential arises from the interplay of fast Na⁺ activation ($m$), slower Na⁺ inactivation ($h$), and delayed K⁺ activation ($n$). The $m^3 h$ and $n^4$ terms reflect the number of independent subunit gates per channel.

---

## 4.2 Signal Propagation in Dendrites/Axons — Cable Equation

**What it models:** Passive (subthreshold) electrical signal propagation along neuronal processes. Determines how far a signal travels before decaying (length constant $\lambda$) and how fast it rises (time constant $\tau$).

**Refs:**
- Kelvin, Lord (1855). "On the theory of the electric telegraph." *Proceedings of the Royal Society*.
- Rushton, W.A.H. (1951). "A theory of the effects of fibre size in medullated nerve." *Journal of Physiology*, 115(1), 101–122.

### Cable Equation (PDE)

$$
\lambda^2 \frac{\partial^2 V}{\partial x^2} = \tau \frac{\partial V}{\partial t} + V
$$

### Characteristic Constants

$$
\lambda = \sqrt{\frac{r_m}{r_i}}, \qquad \tau = r_m \cdot c_m
$$

### Steady-State Solution (DC Input)

$$
V(x) = V_0 \, e^{-|x|/\lambda}
$$

| Variable | Definition | Typical Values |
|----------|-----------|----------------|
| $V(x,t)$ | Membrane potential deviation from rest | mV |
| $\lambda$ | Length constant (space constant) | 0.1–1 mm (dendrites), 1–5 mm (axons) |
| $\tau$ | Membrane time constant | 10–50 ms |
| $r_m$ | Membrane resistance per unit length | MΩ·cm |
| $r_i$ | Intracellular (axial) resistance per unit length | MΩ/cm |
| $c_m$ | Membrane capacitance per unit length | μF/cm |

**Key insight:** Myelination increases $r_m$ dramatically → increases $\lambda$ → signal propagates much further without decaying → saltatory conduction between nodes of Ranvier.

---

## 4.3 Myelinated Conduction Velocity — Rushton G-Ratio Model

**What it models:** The relationship between axon diameter, myelin thickness, and conduction velocity in myelinated white matter tracts (corpus callosum, internal capsule, corticospinal tract).

**Ref:** Rushton, W.A.H. (1951). "A theory of the effects of fibre size in medullated nerve." *Journal of Physiology*, 115(1), 101–122.

### G-Ratio

$$
g = \frac{d}{D}
$$

### Conduction Velocity (Empirical)

$$
v = \kappa \cdot D \approx 5.7 \, D \quad \text{(m/s, where } D \text{ in μm)}
$$

### Optimal G-Ratio (Maximizes Conduction Velocity)

$$
g_{\text{opt}} \approx 0.6
$$

This maximizes:

$$
v \propto d \cdot \sqrt{-\ln(g)}
$$

| Variable | Definition | Typical Values |
|----------|-----------|----------------|
| $g$ | G-ratio (inner/outer diameter ratio) | 0.6–0.7 (CNS optimal) |
| $d$ | Inner axon diameter | 0.2–20 μm |
| $D$ | Outer fiber diameter (including myelin) | $d/g$ |
| $v$ | Conduction velocity | 1–120 m/s |
| $\kappa$ | Proportionality constant | ~5.7 (m/s)/μm |

**Key insight:** Conduction velocity is proportional to fiber diameter (not diameter²). The optimal g-ratio of ~0.6 represents the best trade-off: too thin myelin (high g) → poor insulation; too thick myelin (low g) → reduced axon space → higher axial resistance.

---

## 4.4 CSF Dynamics — Davson Equation & Marmarou Model

**What it models:** Cerebrospinal fluid production, absorption, and intracranial pressure dynamics. Relevant to the ventricular system described in the anatomy chapter.

**Refs:**
- Davson, H. (1956). *Physiology of the Ocular and Cerebrospinal Fluids*. Churchill.
- Marmarou, A., Shulman, K. & LaMorgese, J. (1975). "Compartmental analysis of compliance and outflow resistance of the cerebrospinal fluid system." *Journal of Neurosurgery*, 43(5), 523–534.

### Davson Equation (Steady-State ICP)

$$
ICP = P_v + R_{\text{out}} \cdot I_f
$$

| Variable | Definition | Typical Values |
|----------|-----------|----------------|
| $ICP$ | Intracranial pressure | 7–15 mmHg (normal) |
| $P_v$ | Venous sinus pressure | 5–8 mmHg |
| $R_{\text{out}}$ | Resistance to CSF outflow | 6–10 mmHg/(mL/min) |
| $I_f$ | CSF formation rate | 0.3–0.4 mL/min (~500 mL/day) |

### Marmarou Dynamic Model

$$
\frac{dICP}{dt} = \frac{1}{C(ICP)} \left[ I_f - \frac{ICP - P_v}{R_{\text{out}}} + I_{\text{ext}} \right]
$$

### Pressure-Volume Relationship (Exponential Compliance)

$$
C(ICP) = \frac{1}{E \cdot ICP}
$$

$$
PVI = \frac{V}{\log_{10}\!\left(\frac{ICP_{\text{peak}}}{ICP_{\text{baseline}}}\right)}
$$

| Variable | Definition |
|----------|-----------|
| $C(ICP)$ | Intracranial compliance (decreases as ICP rises) |
| $E$ | Elastance coefficient (brain stiffness) |
| $I_{\text{ext}}$ | External volume injection rate (for clinical testing) |
| $PVI$ | Pressure-Volume Index (mL; clinical measure of compliance) |
| $V$ | Volume of injected fluid (mL) |

**Key insight:** The exponential compliance means small volume additions at high ICP cause dangerous pressure spikes. Normal brain has ~150 mL CSF acting as a buffer; in hydrocephalus, $R_{\text{out}}$ increases → ICP rises → ventricles expand.

---

# 5. Case Studies

## Case Study 1: Motor Cortex Population Vector — Predicting Movement Direction

**Scenario:** A rhesus monkey reaches toward a target. We record from 4 neurons in primary motor cortex (M1) during the reach.

**Given Data:**

| Neuron | Preferred Direction $\theta_{pref}$ | Baseline $f_0$ (sp/s) | Observed $f_i$ (sp/s) |
|--------|--------------------------------------|--------------------------|--------------------------|
| 1 | 0° (right) | 20 | 45 |
| 2 | 90° (up) | 22 | 50 |
| 3 | 180° (left) | 18 | 12 |
| 4 | 270° (down) | 20 | 15 |

**Solution:**

**Step 1:** Compute weighted contribution of each neuron.

$$
\vec{M} = \sum_{i=1}^{4} (f_i - f_0) \hat{d}_i
$$

Neuron 1: $(45 - 20)(\cos 0°, \sin 0°) = 25(1, 0) = (25, 0)$

Neuron 2: $(50 - 22)(\cos 90°, \sin 90°) = 28(0, 1) = (0, 28)$

Neuron 3: $(12 - 18)(\cos 180°, \sin 180°) = -6(-1, 0) = (6, 0)$

Neuron 4: $(15 - 20)(\cos 270°, \sin 270°) = -5(0, -1) = (0, 5)$

**Step 2:** Sum all contributions.

$$
\vec{M} = (25 + 0 + 6 + 0, \; 0 + 28 + 0 + 5) = (31, 33)
$$

**Step 3:** Compute direction.

$$
\theta_M = \arctan\!\left(\frac{33}{31}\right) = \arctan(1.065) \approx 46.8°
$$

**Result:** The population vector predicts movement direction of ~47° (northeast), roughly halfway between right and up. The magnitude $|\vec{M}| = \sqrt{31^2 + 33^2} = 45.3$ indicates a vigorous reach.

**Interpretation:** Even though each neuron is broadly tuned (responds to many directions), the population vector accurately recovers the movement direction. Neurons below their baseline (3 and 4) contribute through subtraction — their suppression is informative.

---

## Case Study 2: V1 Gabor Filter — Orientation Selectivity

**Scenario:** A V1 simple cell has orientation preference $\theta = 45°$, spatial frequency $1/\lambda = 2$ cycles/degree, and receptive field size $\sigma = 0.3°$. We present bars at different orientations and compute the cell's response.

**Given Parameters:**
- $\theta_0 = 45°$, $\lambda = 0.5°$, $\sigma = 0.3°$, $\gamma = 0.5$, $\psi = 0$

**Computing response to a bar at orientation $\theta_{\text{stim}}$:**

Using the tuning curve approximation:

$$
R(\theta_{\text{stim}}) \approx R_{\max} \exp\!\left(-\frac{(\theta_{\text{stim}} - \theta_0)^2}{2\sigma_\theta^2}\right)
$$

where $\sigma_\theta \approx 25°$ for typical V1 neurons.

| Stimulus Orientation | $\theta_{\text{stim}} - \theta_0$ | Response (% of max) |
|---------------------|-----------------------------------|---------------------|
| 45° (preferred) | 0° | 100% |
| 55° | 10° | 92.3% |
| 70° | 25° | 60.7% |
| 90° | 45° | 16.5% |
| 135° (orthogonal) | 90° | 0.07% |

**Result:** The neuron shows strong orientation selectivity with a bandwidth of ~25°. Response drops to half-maximum at ~21° from preferred orientation. The orthogonal orientation (135°) produces essentially zero response.

**Interpretation:** This sharp tuning emerges from the elongated Gabor structure — the sinusoidal component matched to the bar's spatial frequency, and the Gaussian envelope limiting the receptive field. A population of such cells covering all orientations (0°–180°) provides a complete representation.

---

## Case Study 3: Drift-Diffusion Decision — Easy vs Hard Discrimination

**Scenario:** A subject performs a motion discrimination task (left vs right moving dots). We compare an easy condition (high coherence, $v = 0.3$) with a hard condition (low coherence, $v = 0.05$), both with same boundary $a = 0.12$ and non-decision time $T_{er} = 300$ ms.

**Given:** $s = 1$ (noise scaling), $z = a/2$ (unbiased)

**Computing accuracy:**

$$
P(\text{correct}) = \frac{1}{1 + e^{-2va/s^2}}
$$

**Easy:** $P = \frac{1}{1 + e^{-2(0.3)(0.12)/1}} = \frac{1}{1 + e^{-0.072}} = \frac{1}{1 + 0.931} = 0.518$

Wait — these are typically used with larger $a$ values. Let me recalculate with standard parameterization where $a = 0.12$, $s = 0.1$:

$$
P_{\text{easy}} = \frac{1}{1 + e^{-2(0.3)(0.12)/(0.1)^2}} = \frac{1}{1 + e^{-72}} \approx 1.0 \quad (99.99\%)
$$

$$
P_{\text{hard}} = \frac{1}{1 + e^{-2(0.05)(0.12)/(0.1)^2}} = \frac{1}{1 + e^{-12}} \approx 0.9999 \quad (99.99\%)
$$

**Using more standard parameters** ($a = 1.5$, $s = 1$):

$$
P_{\text{easy}} = \frac{1}{1 + e^{-2(0.3)(1.5)}} = \frac{1}{1 + e^{-0.9}} = \frac{1}{1.407} = 71.1\%
$$

$$
P_{\text{hard}} = \frac{1}{1 + e^{-2(0.05)(1.5)}} = \frac{1}{1 + e^{-0.15}} = \frac{1}{1.861} = 53.7\%
$$

**Computing mean decision time:**

$$
\mathbb{E}[T]_{\text{easy}} = \frac{a}{2v} \tanh\!\left(\frac{va}{2}\right) + T_{er} = \frac{1.5}{0.6} \tanh(0.225) + 0.3 = 2.5 \times 0.221 + 0.3 = 0.853 \text{ s}
$$

$$
\mathbb{E}[T]_{\text{hard}} = \frac{1.5}{0.1} \tanh(0.0375) + 0.3 = 15 \times 0.0375 + 0.3 = 0.862 \text{ s}
$$

**Result Summary:**

| Condition | Accuracy | Mean RT |
|-----------|----------|---------|
| Easy ($v = 0.3$) | 71.1% | 853 ms |
| Hard ($v = 0.05$) | 53.7% | 862 ms |

**Interpretation:** Higher drift rate → better accuracy with similar RT. The hard condition approaches chance (50%) because the low signal is overwhelmed by noise. This matches neural recordings in LIP: neurons show steeper ramping activity for easier discriminations.

---

## Case Study 4: Hippocampal STDP — Synaptic Weight Changes

**Scenario:** We record from a CA3 → CA1 synapse (Schaffer collateral) during a hippocampal replay event. We observe 5 spike pairs with different timings.

**Given Parameters:** $A_+ = 0.01$, $A_- = 0.012$, $\tau_+ = 20$ ms, $\tau_- = 20$ ms

| Spike Pair | $t_{\text{pre}}$ (ms) | $t_{\text{post}}$ (ms) | $\Delta t$ (ms) |
|-----------|----------------------|----------------------|----------------|
| 1 | 100 | 110 | +10 |
| 2 | 200 | 205 | +5 |
| 3 | 300 | 295 | -5 |
| 4 | 400 | 420 | +20 |
| 5 | 500 | 460 | -40 |

**Solution:**

$$
\Delta w = \begin{cases} A_+ \exp(-\Delta t / \tau_+) & \text{if } \Delta t > 0 \\ -A_- \exp(\Delta t / \tau_-) & \text{if } \Delta t < 0 \end{cases}
$$

| Pair | $\Delta t$ | Calculation | $\Delta w$ | Type |
|------|-----------|-------------|------------|------|
| 1 | +10 ms | $0.01 \times e^{-10/20}$ | **+0.00607** | LTP |
| 2 | +5 ms | $0.01 \times e^{-5/20}$ | **+0.00779** | LTP |
| 3 | -5 ms | $-0.012 \times e^{-5/20}$ | **-0.00934** | LTD |
| 4 | +20 ms | $0.01 \times e^{-20/20}$ | **+0.00368** | LTP |
| 5 | -40 ms | $-0.012 \times e^{-40/20}$ | **-0.00163** | LTD |

**Net synaptic change:**

$$
\sum \Delta w = 0.00607 + 0.00779 - 0.00934 + 0.00368 - 0.00163 = +0.00657
$$

**Result:** Net LTP (strengthening). The synapse is potentiated because causal pairs (pre before post) slightly outweigh anti-causal pairs.

**Interpretation:** This is how hippocampal replay during sleep consolidates spatial memories — replayed sequences preserve the temporal order of place cell firing, causing systematic LTP at synapses encoding the experienced trajectory. The asymmetric window (slightly stronger LTD than LTP, $A_- > A_+$) ensures stability; only consistently causal relationships survive.

---

## Case Study 5: Rescorla-Wagner Fear Conditioning — Amygdala Learning

**Scenario:** A rat undergoes fear conditioning. A tone (CS, $\alpha = 0.4$) is paired with a foot shock (US, $\beta = 0.3$, $\lambda = 1.0$) for 10 trials. We track the associative strength $V$ trial by trial.

**Given:** $V_0 = 0$ (naive), one CS present ($\sum V = V_{\text{tone}}$)

$$
V^{(n+1)} = V^{(n)} + \alpha \beta (\lambda - V^{(n)}) = V^{(n)} + 0.12(1 - V^{(n)})
$$

| Trial | $V^{(n)}$ | Prediction Error $(\lambda - V)$ | $\Delta V$ |
|-------|-----------|----------------------------------|------------|
| 1 | 0.000 | 1.000 | 0.120 |
| 2 | 0.120 | 0.880 | 0.106 |
| 3 | 0.226 | 0.774 | 0.093 |
| 4 | 0.319 | 0.681 | 0.082 |
| 5 | 0.400 | 0.600 | 0.072 |
| 6 | 0.472 | 0.528 | 0.063 |
| 7 | 0.536 | 0.464 | 0.056 |
| 8 | 0.591 | 0.409 | 0.049 |
| 9 | 0.640 | 0.360 | 0.043 |
| 10 | 0.683 | 0.317 | 0.038 |

**After trial 10:** $V = 0.721$

**Now extinction (5 trials, CS alone, no US → $\lambda = 0$):**

$$
\Delta V = 0.12(0 - V^{(n)}) = -0.12 V^{(n)}
$$

| Trial | $V^{(n)}$ | $\Delta V$ |
|-------|-----------|------------|
| 11 | 0.721 | -0.087 |
| 12 | 0.635 | -0.076 |
| 13 | 0.558 | -0.067 |
| 14 | 0.492 | -0.059 |
| 15 | 0.433 | -0.052 |

**Result:** After 10 conditioning trials, the tone predicts ~72% of the shock. Extinction reduces this to ~43% after 5 unreinforced trials. Learning slows as prediction error decreases — the classic negatively-accelerated learning curve.

**Interpretation:** The prediction error $(\lambda - V)$ maps onto BLA neuron responses: large early, diminishing with learning. This matches dopamine neuron recordings — initial CS-US pairings produce large dopamine bursts; after learning, the burst shifts to CS onset (predictive signal). Extinction isn't "unlearning" — it's new inhibitory learning that suppresses the original CS-US association.

---

## Case Study 6: CSF Dynamics — Normal vs Hydrocephalus

**Scenario:** We use the Davson equation to compare intracranial pressure in a healthy adult vs a patient with communicating hydrocephalus (increased outflow resistance).

**Given:**

| Parameter | Normal | Hydrocephalus |
|-----------|--------|---------------|
| $P_v$ (venous pressure) | 7 mmHg | 7 mmHg |
| $R_{\text{out}}$ (outflow resistance) | 8 mmHg/(mL/min) | 24 mmHg/(mL/min) |
| $I_f$ (CSF production) | 0.35 mL/min | 0.35 mL/min |

**Davson Equation:**

$$
ICP = P_v + R_{\text{out}} \cdot I_f
$$

**Normal:**

$$
ICP = 7 + 8 \times 0.35 = 7 + 2.8 = 9.8 \text{ mmHg}
$$

**Hydrocephalus:**

$$
ICP = 7 + 24 \times 0.35 = 7 + 8.4 = 15.4 \text{ mmHg}
$$

**Dynamic response (Marmarou): What happens if we inject 1 mL saline?**

Using PVI = 25 mL (normal) vs PVI = 10 mL (hydrocephalus):

$$
ICP_{\text{peak}} = ICP_{\text{baseline}} \times 10^{V/PVI}
$$

**Normal:** $ICP_{\text{peak}} = 9.8 \times 10^{1/25} = 9.8 \times 1.096 = 10.7$ mmHg (rise of 0.9 mmHg)

**Hydrocephalus:** $ICP_{\text{peak}} = 15.4 \times 10^{1/10} = 15.4 \times 1.259 = 19.4$ mmHg (rise of 4.0 mmHg)

**Result Summary:**

| Measure | Normal | Hydrocephalus |
|---------|--------|---------------|
| Baseline ICP | 9.8 mmHg | 15.4 mmHg |
| ICP after 1 mL injection | 10.7 mmHg | 19.4 mmHg |
| Pressure rise | 0.9 mmHg | 4.0 mmHg |
| Compliance | High | Low (4.4× less) |

**Interpretation:** The hydrocephalic brain has both higher baseline ICP (due to $3\times$ outflow resistance) and dramatically reduced compliance — a small volume change causes a disproportionately large pressure increase. This explains why hydrocephalus patients are vulnerable to ICP crises from minor perturbations (coughing, Valsalva) and why shunt placement ($R_{\text{out}}$ reduction) is the primary treatment.

---

# 6. References

## Cerebral Cortex Models

1. **Georgopoulos, A.P., Schwartz, A.B. & Kettner, R.E.** (1986). Neuronal population coding of movement direction. *Science*, 233(4771), 1416–1419. doi:10.1126/science.3749885

2. **Jones, J.P. & Palmer, L.A.** (1987). An evaluation of the two-dimensional Gabor filter model of simple receptive fields in cat striate cortex. *Journal of Neurophysiology*, 58(6), 1233–1258. doi:10.1152/jn.1987.58.6.1233

3. **Adelson, E.H. & Bergen, J.R.** (1985). Spatiotemporal energy models for the perception of motion. *Journal of the Optical Society of America A*, 2(2), 284–299. doi:10.1364/JOSAA.2.000284

4. **Patterson, R.D., Holdsworth, J., Nimmo-Smith, I. & Rice, P.** (1988). SVOS Final Report: The Auditory Filterbank. *Institute of Hearing Research*, Cambridge, UK.

5. **Fechner, G.T.** (1860). *Elemente der Psychophysik*. Leipzig: Breitkopf und Härtel.

6. **Stevens, S.S.** (1957). On the psychophysical law. *Psychological Review*, 64(3), 153–181. doi:10.1037/h0046162

7. **Seung, H.S. & Sompolinsky, H.** (1993). Simple models for reading neuronal population codes. *Proceedings of the National Academy of Sciences*, 90(22), 10749–10753. doi:10.1073/pnas.90.22.10749

8. **Compte, A., Brunel, N., Goldman-Rakic, P.S. & Wang, X.J.** (2000). Synaptic mechanisms and network dynamics underlying spatial working memory in a cortical network model. *Cerebral Cortex*, 10(9), 910–923. doi:10.1093/cercor/10.9.910

9. **Wimmer, K., Nykamp, D.Q., Constantinidis, C. & Compte, A.** (2014). Bump attractor dynamics in prefrontal cortex explains behavioral precision in spatial working memory. *Nature Neuroscience*, 17(3), 431–439. doi:10.1038/nn.3645

10. **Ratcliff, R.** (1978). A theory of memory retrieval. *Psychological Review*, 85(2), 59–108. doi:10.1037/0033-295X.85.2.59

11. **Wilson, H.R. & Cowan, J.D.** (1972). Excitatory and inhibitory interactions in localized populations of model neurons. *Biophysical Journal*, 12(1), 1–24. doi:10.1016/S0006-3495(72)86068-5

## Cerebellum Models

12. **Marr, D.** (1969). A theory of cerebellar cortex. *Journal of Physiology*, 202(2), 437–470. doi:10.1113/jphysiol.1969.sp008820

13. **Albus, J.S.** (1971). A theory of cerebellar function. *Mathematical Biosciences*, 10(1-2), 25–61. doi:10.1016/0025-5564(71)90051-4

14. **Ito, M.** (1984). *The Cerebellum and Neural Control*. New York: Raven Press.

15. **Fujita, M.** (1982). Adaptive filter model of the cerebellum. *Biological Cybernetics*, 45(3), 195–206. doi:10.1007/BF00336192

16. **Jansen, B.H. & Rit, V.G.** (1995). Electroencephalogram and visual evoked potential generation in a mathematical model of coupled cortical columns. *Biological Cybernetics*, 73(4), 357–366. doi:10.1007/BF00199471

## Subcortical Models

17. **Destexhe, A., Bal, T., McCormick, D.A. & Bhattacharjee, A.** (1996). Ionic mechanisms underlying synchronized oscillations and propagating waves in a model of ferret thalamic slices. *Journal of Neurophysiology*, 76(3), 2049–2070. doi:10.1152/jn.1996.76.3.2049

18. **Bi, G. & Poo, M.** (1998). Synaptic modifications in cultured hippocampal neurons: dependence on spike timing, synaptic strength, and postsynaptic cell type. *Journal of Neuroscience*, 18(24), 10464–10472. doi:10.1523/JNEUROSCI.18-24-10464.1998

19. **Bienenstock, E., Cooper, L. & Munro, P.** (1982). Theory for the development of neuron selectivity: orientation specificity and binocular interaction in visual cortex. *Journal of Neuroscience*, 2(1), 32–48. doi:10.1523/JNEUROSCI.02-01-00032.1982

20. **O'Keefe, J. & Dostrovsky, J.** (1971). The hippocampus as a spatial map. *Brain Research*, 34(1), 171–175. doi:10.1016/0006-8993(71)90358-1

21. **Hafting, T., Fyhn, M., Molden, S., Moser, M-B. & Moser, E.I.** (2005). Microstructure of a spatial map in the entorhinal cortex. *Nature*, 436(7052), 801–806. doi:10.1038/nature03721

22. **Rodriguez, G.G. & Caplan, J.B.** (2019). A hexagonal Fourier model of grid cells. *Hippocampus*, 29(1), 37–45. doi:10.1002/hipo.23014

23. **Rescorla, R.A. & Wagner, A.R.** (1972). A theory of Pavlovian conditioning: Variations in the effectiveness of reinforcement and nonreinforcement. In Black, A.H. & Prokasy, W.F. (Eds.), *Classical Conditioning II: Current Research and Theory*, pp. 64–99. New York: Appleton-Century-Crofts.

24. **Barto, A.G.** (1995). Adaptive critics and the basal ganglia. In Houk, J.C., Davis, J.L. & Beiser, D.G. (Eds.), *Models of Information Processing in the Basal Ganglia*, pp. 215–232. Cambridge, MA: MIT Press.

25. **Frank, M.J.** (2006). Hold your horses: A dynamic computational role for the subthalamic nucleus in decision making. *Neural Computation*, 18(6), 1322–1348. doi:10.1162/neco.2006.18.6.1322

26. **Goldbeter, A.** (1995). A model for circadian oscillations in the Drosophila period protein (PER). *Proceedings of the Royal Society B*, 261(1362), 319–324. doi:10.1098/rspb.1995.0153

27. **Leloup, J-C. & Goldbeter, A.** (2003). Toward a detailed computational model for the mammalian circadian clock. *Proceedings of the National Academy of Sciences*, 100(12), 7051–7056. doi:10.1073/pnas.1132112100

## Neural Signaling & White Matter Models

28. **Hodgkin, A.L. & Huxley, A.F.** (1952). A quantitative description of membrane current and its application to conduction and excitation in nerve. *Journal of Physiology*, 117(4), 500–544. doi:10.1113/jphysiol.1952.sp004764

29. **Rushton, W.A.H.** (1951). A theory of the effects of fibre size in medullated nerve. *Journal of Physiology*, 115(1), 101–122. doi:10.1113/jphysiol.1951.sp004655

30. **Davson, H.** (1956). *Physiology of the Ocular and Cerebrospinal Fluids*. London: Churchill.

31. **Marmarou, A., Shulman, K. & LaMorgese, J.** (1975). Compartmental analysis of compliance and outflow resistance of the cerebrospinal fluid system. *Journal of Neurosurgery*, 43(5), 523–534. doi:10.3171/jns.1975.43.5.0523

## Homeostatic & Control Models

32. **Hammel, H.T.** (1965). Neurons and temperature regulation. In Hardy, J.D. (Ed.), *Physiological Controls and Regulations*, pp. 71–97. Philadelphia: Saunders.

---

*Back to: [Chapter 1 — Structural Anatomy](../Structural_Anatomy.md)*
