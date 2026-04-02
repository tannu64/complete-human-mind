# Mathematical Equations of Neurotransmitter Systems

> **Source Chapter:** [Neurotransmitter Systems](../Neurotransmitter_Systems.md)
>
> This document converts every major neurotransmitter function described in Chapter 4 into published computational and biochemical mathematical models. Equations cover synthesis kinetics, receptor binding/activation, signal transduction cascades, reuptake dynamics, and neuromodulatory systems.

---

## Table of Contents

1. [Neurotransmitter Synthesis Kinetics](#1-neurotransmitter-synthesis-kinetics)
2. [Glutamate Receptor Models](#2-glutamate-receptor-models)
3. [GABA Receptor Models](#3-gaba-receptor-models)
4. [Monoamine Systems](#4-monoamine-systems)
5. [Acetylcholine System](#5-acetylcholine-system)
6. [Neuropeptides and Neuromodulators](#6-neuropeptides-and-neuromodulators)
7. [Intracellular Signaling Cascades](#7-intracellular-signaling-cascades)
8. [Case Studies](#8-case-studies)
9. [References](#9-references)

---

# 1. Neurotransmitter Synthesis Kinetics

## 1.1 Michaelis-Menten Enzyme Kinetics — General Synthesis Rate

**What it models:** Rate of neurotransmitter synthesis by biosynthetic enzymes (Tyrosine Hydroxylase for dopamine/norepinephrine; Glutamic Acid Decarboxylase for GABA; Tryptophan Hydroxylase for serotonin; Choline Acetyltransferase for ACh). All follow Michaelis-Menten kinetics.

**Ref:** Michaelis, L. & Menten, M.L. (1913). "Die Kinetik der Invertinwirkung." *Biochemische Zeitschrift*, 49, 333–369.

### Michaelis-Menten Equation

$$
v = V_{\max} \frac{[S]}{K_m + [S]}
$$

| Variable | Definition | Typical Values |
|----------|-----------|----------------|
| $v$ | Reaction velocity (synthesis rate) | nM/min or μM/s |
| $V_{\max}$ | Maximum velocity (saturated enzyme) | varies by enzyme |
| $[S]$ | Substrate concentration | mM |
| $K_m$ | Michaelis constant (substrate at $v = V_{\max}/2$) | μM–mM |

### Rate-Limiting Enzyme Parameters

| Enzyme | Neurotransmitter | Substrate | $K_m$ |
|--------|----------------|-----------|-------|
| Tyrosine Hydroxylase (TH) | Dopamine/NE | L-Tyrosine | 50–100 μM |
| Tryptophan Hydroxylase (TPH2) | Serotonin | L-Tryptophan | 30–60 μM |
| Glutamic Acid Decarboxylase (GAD67) | GABA | Glutamate | 0.6–2.0 mM |
| Choline Acetyltransferase (ChAT) | ACh | Choline | 0.5–1.0 mM |

**Key insight:** Since TH $K_m \approx 50$ μM and typical brain tyrosine is ~100–150 μM, TH operates near half-saturation — synthesis rate is sensitive to tyrosine availability. This is why dietary tyrosine can modestly influence dopamine synthesis.

---

## 1.2 Tyrosine Hydroxylase Feedback Inhibition

**What it models:** TH (the rate-limiting enzyme for dopamine and norepinephrine synthesis) is inhibited by its own product — end-product inhibition provides homeostatic control of synthesis rate.

**Ref:** Leviel, V. (2011). "Dopamine release mediated by the dopamine transporter, facts and consequences." *Journal of Neurochemistry*, 118(4), 475–489.

### Competitive Inhibition by End Product

$$
v = V_{\max} \frac{[S]}{K_m \left(1 + \frac{[I]}{K_i}\right) + [S]}
$$

| Variable | Definition | Units |
|----------|-----------|-------|
| $[I]$ | Concentration of inhibitor (dopamine or NE) | μM |
| $K_i$ | Inhibition constant (affinity for inhibitor) | μM |

### Phosphorylation Activation of TH (by PKA/CaMKII)

$$
V_{\max,\text{phospho}} = V_{\max,\text{basal}} \times k_{\text{phos}}
$$

where $k_{\text{phos}} \approx 3$–10-fold increase upon serine phosphorylation (Ser19, Ser31, Ser40).

**Key insight:** DA neurons regulate their own synthesis via two parallel mechanisms: (1) product inhibition by cytoplasmic dopamine, and (2) D2 autoreceptor signaling → inhibits TH phosphorylation → reduces synthesis. This creates a homeostatic feedback loop that stabilizes dopamine output.

---

## 1.3 Vesicular Neurotransmitter Loading

**What it models:** Packaging of neurotransmitter into synaptic vesicles by vesicular transporters (VGLUT for glutamate, VGAT for GABA, VMAT2 for monoamines, VAChT for ACh).

**Ref:** Parsons, S.M. (2000). "Transport mechanisms in acetylcholine and monoamine storage." *FASEB Journal*, 14(15), 2423–2434.

### Vesicular Transport Rate

$$
\frac{d[NT]_v}{dt} = V_{\text{vesicle}} \frac{[NT]_{\text{cytosol}}}{K_T + [NT]_{\text{cytosol}}} - k_{\text{leak}} [NT]_v
$$

| Variable | Definition |
|----------|-----------|
| $[NT]_v$ | Vesicular neurotransmitter concentration |
| $V_{\text{vesicle}}$ | Maximum vesicular uptake velocity |
| $[NT]_{\text{cytosol}}$ | Cytosolic neurotransmitter concentration |
| $K_T$ | Transporter affinity constant |
| $k_{\text{leak}}$ | Passive leak rate |

**Steady-state vesicle filling:**

$$
[NT]_v^* = \frac{V_{\text{vesicle}} [NT]_{\text{cytosol}}}{k_{\text{leak}}(K_T + [NT]_{\text{cytosol}})}
$$

**Quantal size:** The amount of neurotransmitter in a single vesicle:

$$
Q = [NT]_v \times V_{\text{vesicle,volume}} \times N_A
$$

where $V_{\text{vesicle,volume}} \approx 10^{-20}$ L (20 nm diameter), $N_A$ = Avogadro's number.

---

# 2. Glutamate Receptor Models

## 2.1 AMPA Receptor Kinetics — 4-State Markov Model

**What it models:** Fast activation, rapid desensitization, and deactivation of AMPA receptors. This determines the time course of fast excitatory postsynaptic currents (EPSCs).

**Ref:** Destexhe, A., Mainen, Z.F. & Sejnowski, T.J. (1994). "Synthesis of models for excitable membranes, synaptic transmission and neuromodulation using a common kinetic formalism." *Journal of Computational Neuroscience*, 1(3), 195–230.

### State Transitions

$$
C \underset{k_{-1}}{\overset{r_1[T]}{\rightleftharpoons}} C^* \underset{\beta}{\overset{\alpha}{\rightleftharpoons}} O
$$

$$
C^* \underset{k_{-d}}{\overset{k_d}{\rightleftharpoons}} D \quad \text{(desensitization)}
$$

### Conductance from Open State Fraction

$$
g_{\text{AMPA}}(t) = \bar{g}_{\text{AMPA}} \cdot O(t)
$$

$$
I_{\text{AMPA}} = g_{\text{AMPA}}(t) (V_m - E_{\text{AMPA}})
$$

### Two-Exponential Approximation (Practical Use)

$$
g_{\text{AMPA}}(t) = \bar{g}_{\text{AMPA}} \left( e^{-t/\tau_{\text{decay}}} - e^{-t/\tau_{\text{rise}}} \right)
$$

| Parameter | Definition | Typical Values |
|-----------|-----------|----------------|
| $r_1$ | Binding rate (glutamate) | 1–10 μM⁻¹ms⁻¹ |
| $k_{-1}$ | Unbinding rate | 0.5–5 ms⁻¹ |
| $\alpha, \beta$ | Opening/closing rates | 0.1–1 ms⁻¹ |
| $k_d, k_{-d}$ | Desensitization/recovery rates | 0.02–1 ms⁻¹ |
| $\tau_{\text{rise}}$ | Rise time | 0.2–1 ms |
| $\tau_{\text{decay}}$ | Decay time | 2–10 ms |
| $E_{\text{AMPA}}$ | Reversal potential | 0 mV |

---

## 2.2 NMDA Receptor Model — Voltage-Dependent Mg²⁺ Block + Kinetics

**What it models:** NMDA receptors as coincidence detectors requiring both glutamate binding AND postsynaptic depolarization. The Mg²⁺ block provides the voltage gate.

**Ref:** Jahr, C.E. & Stevens, C.F. (1990). "Voltage dependence of NMDA-activated macroscopic conductances predicted by single-channel kinetics." *Journal of Neuroscience*, 10(9), 3178–3182.

### NMDA Conductance with Mg²⁺ Block

$$
g_{\text{NMDA}}(V_m, t) = \bar{g}_{\text{NMDA}} \cdot s(t) \cdot B(V_m)
$$

### Voltage-Dependent Mg²⁺ Blockade

$$
B(V_m) = \frac{1}{1 + \frac{[\text{Mg}^{2+}]_o}{K_{\text{Mg}}} \exp\!\left(-\frac{V_m}{\delta \cdot 25.7}\right)}
$$

**Year & Stevens (1990) parameters:** $K_{\text{Mg}} = 3.57$ mM, $\delta = 0.89$

### NMDA Synaptic Gating Variable

$$
\frac{ds}{dt} = -\frac{s}{\tau_{\text{NMDA}}} + \alpha_s [T](1-s)
$$

| Parameter | Definition | Typical Values |
|-----------|-----------|----------------|
| $[\text{Mg}^{2+}]_o$ | Extracellular Mg²⁺ | 1–2 mM |
| $K_{\text{Mg}}$ | Mg²⁺ affinity constant | 3.57 mM |
| $\delta$ | Electrical distance from outside | 0.89 |
| $\tau_{\text{NMDA}}$ | NMDA decay time constant | 50–300 ms |
| $\alpha_s$ | Binding rate | 0.072 ms⁻¹μM⁻¹ |
| $[T]$ | Glutamate concentration (transmitter) | 1 mM (peak) |

### Ca²⁺ Flux through NMDA

$$
I_{\text{Ca}}^{\text{NMDA}} = P_{\text{Ca}} \cdot g_{\text{NMDA}}(V_m,t) \cdot (V_m - E_{\text{Ca}})
$$

where $P_{\text{Ca}} \approx 0.1$ (fraction of NMDA current carried by Ca²⁺).

**Key insight:** $B(V_m)$ creates a nonlinear "AND gate": glutamate binding alone at rest (−70 mV) produces minimal Ca²⁺ influx because $B \approx 0.1$. Depolarization to 0 mV increases $B$ to ~0.8, enabling full Ca²⁺ influx. This coincidence detection is the molecular basis of Hebbian synaptic plasticity (LTP).

---

## 2.3 Excitotoxicity Model — Ca²⁺-Dependent Neuronal Death

**What it models:** Excessive NMDA activation during stroke/TBI leads to Ca²⁺ overload and neuronal death through a threshold mechanism.

**Ref:** Tymianski, M., Charlton, M.P., Carlen, P.L. & Tator, C.H. (1993). "Source specificity of early calcium neurotoxicity in cultured embryonic spinal neurons." *Journal of Neuroscience*, 13(5), 2085–2104.

### Ca²⁺ Accumulation During Excitotoxicity

$$
\frac{d[\text{Ca}^{2+}]_i}{dt} = J_{\text{NMDA}} + J_{\text{VDCC}} + J_{\text{RyR}} - J_{\text{PMCA}} - J_{\text{SERCA}} - J_{\text{NCX}}
$$

### Cell Death Probability (Threshold Model)

$$
P_{\text{death}} = \frac{1}{1 + \exp\!\left(-\frac{[\text{Ca}^{2+}]_i - [\text{Ca}^{2+}]_{\text{threshold}}}{\sigma}\right)}
$$

| Parameter | Definition | Values |
|-----------|-----------|--------|
| $[\text{Ca}^{2+}]_{\text{threshold}}$ | Death threshold | ~5–10 μM (sustained) |
| $\sigma$ | Sigmoid slope (sensitivity) | 1–2 μM |
| $J_{\text{SERCA}}$ | ER pump flux | nM/ms |
| $J_{\text{RyR}}$ | Ryanodine receptor ER release | nM/ms |

---

## 2.4 Glutamate Reuptake — EAAT Transporter Kinetics

**What it models:** Astrocytic glutamate transporter (EAAT2) clears ~90% of released glutamate from the synaptic cleft, preventing excitotoxicity.

**Ref:** Danbolt, N.C. (2001). "Glutamate uptake." *Progress in Neurobiology*, 65(1), 1–105.

### Transporter Uptake Rate

$$
J_{\text{EAAT}} = J_{\max} \frac{[\text{Glu}]_{\text{cleft}}}{K_m^{\text{EAAT}} + [\text{Glu}]_{\text{cleft}}}
$$

### Cleft Glutamate Clearance

$$
\frac{d[\text{Glu}]_{\text{cleft}}}{dt} = \frac{N_v \cdot Q}{\Omega_{\text{cleft}}} \delta(t) - J_{\text{EAAT}} - J_{\text{diffusion}}
$$

| Parameter | Definition | Typical Values |
|-----------|-----------|----------------|
| $K_m^{\text{EAAT}}$ | EAAT2 affinity for glutamate | 1–3 μM |
| $J_{\max}$ | Maximum uptake rate | 1–50 nmol/(min·mg protein) |
| $\Omega_{\text{cleft}}$ | Synaptic cleft volume | ~10⁻¹⁸ L |
| Clearance time | Time to restore baseline [Glu] | 1–5 ms |

---

# 3. GABA Receptor Models

## 3.1 GABA-A Receptor — Kinetic Model

**What it models:** Fast GABAergic inhibition mediated by Cl⁻ influx through ligand-gated GABA-A channels.

**Ref:** Destexhe, A., Mainen, Z.F. & Sejnowski, T.J. (1994). *Journal of Computational Neuroscience*, 1(3), 195–230.

### Three-State Kinetic Scheme

$$
C \underset{k_{-1}}{\overset{r_1[T]}{\rightleftharpoons}} C^* \underset{r_d}{\overset{\alpha_g}{\rightleftharpoons}} O
$$

### IPSC Conductance

$$
g_{\text{GABA}_A}(t) = \bar{g}_{\text{GABA}_A} \left(e^{-t/\tau_{\text{decay}}} - e^{-t/\tau_{\text{rise}}}\right)
$$

$$
I_{\text{GABA}_A} = g_{\text{GABA}_A}(t)(V_m - E_{\text{Cl}})
$$

| Parameter | Definition | Typical Values |
|-----------|-----------|----------------|
| $E_{\text{Cl}}$ | Chloride reversal potential (adults) | −70 mV |
| $E_{\text{Cl}}^{\text{immature}}$ | Chloride reversal (neonates) | −40 to −50 mV |
| $\tau_{\text{rise}}$ | Rise time | 0.5–1.0 ms |
| $\tau_{\text{decay}}$ | Decay time | 5–30 ms (phasic) |

### Developmental Switch: GABA from Excitatory to Inhibitory

$$
E_{\text{Cl}} = \frac{RT}{(-1)F} \ln\left(\frac{[\text{Cl}^-]_o}{[\text{Cl}^-]_i}\right)
$$

**Immature neurons:** $[\text{Cl}^-]_i \approx 30$–40 mM (high, due to NKCC1 importer activity)

$$
E_{\text{Cl}}^{\text{immature}} = \frac{61.5}{-1} \log_{10}\!\left(\frac{110}{35}\right) \approx -30 \text{ mV}
$$

**Mature neurons:** $[\text{Cl}^-]_i \approx 5$–10 mM (low, KCC2 extruder dominant)

$$
E_{\text{Cl}}^{\text{mature}} = \frac{61.5}{-1} \log_{10}\!\left(\frac{110}{7}\right) \approx -70 \text{ mV}
$$

Since $E_{\text{Cl}}^{\text{immature}} = -30$ mV $> V_{\text{rest}} = -70$ mV, GABA-A activation depolarizes → **excitatory**

Since $E_{\text{Cl}}^{\text{mature}} = -70$ mV $\approx V_{\text{rest}}$, GABA-A activation is inhibitory (shunting or hyperpolarizing).

---

## 3.2 GABA-B Receptor — G-Protein Coupled Inhibition (GIRK)

**What it models:** Slow GABA-B-mediated hyperpolarization via G-protein activated inwardly-rectifying K⁺ channels (GIRK/Kir3).

**Ref:** Dutar, P. & Nicoll, R.A. (1988). "A physiological role for GABA-B receptors in the central nervous system." *Nature*, 332(6160), 156–158.

### GABA-B/GIRK Slow IPSP

$$
g_{\text{GABA}_B}(t) = \bar{g}_K \frac{[G]^n}{K_d^n + [G]^n}
$$

where $[G]$ is the intracellular G-protein (Gβγ) concentration.

### G-protein activation kinetics

$$
\frac{d[G]}{dt} = k_1 [R^*] - k_2 [G]
$$

$$
I_{\text{GABA}_B} = g_{\text{GABA}_B}(t)(V_m - E_K)
$$

| Parameter | Definition | Typical Values |
|-----------|-----------|----------------|
| $[R^*]$ | Activated GABA-B receptor fraction | 0–1 |
| $k_1, k_2$ | G-protein activation/deactivation rates | 0.001–0.01 ms⁻¹ |
| $K_d$ | G-protein to GIRK affinity | μM |
| $n$ | Hill coefficient (cooperativity) | 4 |
| $E_K$ | Potassium reversal potential | −90 mV |
| $\tau_{\text{IPSP}}$ | Slow IPSP time constant | 100–300 ms |

**Key insight:** The slow kinetics (τ ~100–300 ms) arise from multi-step G-protein cascade: GABA-B activation → Gβγ → GIRK channel opening. This creates a late hyperpolarization ideal for limiting burst firing.

---

# 4. Monoamine Systems

## 4.1 Dopamine — Reward Prediction Error (Schultz Model)

**What it models:** Dopamine neuron firing encodes the temporal difference (TD) prediction error between expected and received reward. This is the mathematical equivalent of TD learning in reinforcement learning.

**Ref:** Schultz, W., Dayan, P. & Montague, P.R. (1997). "A neural substrate of prediction and reward." *Science*, 275(5306), 1593–1599.

### Temporal Difference (TD) Error

$$
\delta(t) = r(t) + \gamma V(s_{t+1}) - V(s_t)
$$

### Value Function Update

$$
V(s_t) \leftarrow V(s_t) + \alpha \cdot \delta(t)
$$

| Variable | Definition | Typical Values |
|----------|-----------|----------------|
| $\delta(t)$ | TD prediction error (≈ dopamine firing change) | −1 to +1 (normalized) |
| $r(t)$ | Reward received at time $t$ | 0 or 1 (binary) |
| $\gamma$ | Temporal discount factor | 0.9–0.99 |
| $V(s)$ | Estimated value of state $s$ | learned |
| $\alpha$ | Learning rate | 0.01–0.1 |

### Mapping to Neural Activity

$$
\text{DA firing rate}(t) = f_{\text{baseline}} + k \cdot \delta(t)
$$

| Scenario | $\delta(t)$ | DA firing |
|----------|------------|-----------|
| Unexpected reward | $\delta > 0$ | Phasic burst (+20–40 Hz) |
| Expected reward received | $\delta = 0$ | No change (baseline ~5 Hz) |
| Expected reward omitted | $\delta < 0$ | Phasic pause (0–2 Hz) |

**Key insight:** This equation explains the 3 canonical dopamine firing patterns observed by Schultz (1997): burst to surprise, no change to prediction, pause to omission. It also explains why drugs of abuse (cocaine: blocks DAT; amphetamine: reverses DAT) generate excessive DA → unnatural "reward" signal.

---

## 4.2 Dopamine Inverted-U Curve — Prefrontal Cortex Optimization

**What it models:** PFC cognitive performance follows an inverted-U relationship with dopamine D1 receptor stimulation. Both too little and too much dopamine impairs working memory.

**Ref:** Arnsten, A.F.T. & Goldman-Rakic, P.S. (1998). "Noise stress impairs prefrontal cortical cognitive function in monkeys." *Archives of General Psychiatry*, 55(4), 362–368.

### Inverted-U Function (Phenomenological)

$$
\text{Performance} = P_{\max} \exp\!\left(-\frac{([\text{DA}] - [\text{DA}]_{\text{opt}})^2}{2\sigma_{\text{DA}}^2}\right)
$$

| Parameter | Definition | Typical Values |
|-----------|-----------|----------------|
| $P_{\max}$ | Maximum cognitive performance | 1.0 (normalized) |
| $[\text{DA}]_{\text{opt}}$ | Optimal dopamine level | ~0.5–1 nM tonic extracellular |
| $\sigma_{\text{DA}}$ | Width of optimal range | ~0.3 nM |

**Key insight:** D1 receptor stimulation in PFC strengthens recurrent network connections (for working memory) at moderate levels via cAMP/PKA signaling. Excessive D1 stimulation activates HCN channels → weakens connections. This explains: ADHD (insufficient DA → suboptimal), stress/anxiety (excess DA/NE → impaired), and why stimulant medications work at low doses but worsen cognition at high doses.

---

## 4.3 Locus Coeruleus (LC) Norepinephrine — Adaptive Gain Model

**What it models:** LC norepinephrine modulates cortical gain (signal-to-noise ratio). An inverted-U relationship between tonic LC firing and task performance: optimal performance at intermediate tonic LC activity.

**Ref:** Aston-Jones, G. & Cohen, J.D. (2005). "An integrative theory of locus coeruleus-norepinephrine function: Adaptive gain and optimal performance." *Annual Review of Neuroscience*, 28, 403–450.

### Cortical Gain Modulation

$$
y = f(x \cdot G)
$$

where:
- $x$ = input signal (stimulus)
- $G$ = gain (controlled by NE level)
- $y$ = output (neural response)
- $f(\cdot)$ = activation function (sigmoid)

### Gain as a Function of NE

$$
G(\text{NE}) = G_{\max} \exp\!\left(-\frac{(\text{NE} - \text{NE}_{\text{opt}})^2}{2\sigma^2}\right)
$$

### LC Modes

$$
r_{\text{LC,tonic}}(t) = \bar{r} + \xi(t) \qquad \text{(low phasic, high tonic = exploration)}
$$

$$
r_{\text{LC,phasic}}(t) = \bar{r} + A_{\text{task}} \cdot \delta(t - t_{\text{decision}}) \qquad \text{(high phasic = exploitation)}
$$

| Mode | Tonic NE | Phasic response | Behavior |
|------|----------|----------------|---------|
| Drowsy | Very low | Absent | Sleep/inattention |
| Optimal | Moderate | Strong task-related bursts | Focused task performance |
| Stressed | Very high | Broad/undifferentiated | Distractibility, anxiety |

---

## 4.4 Monoamine Transporter — Reuptake Kinetics

**What it models:** Dopamine (DAT), Serotonin (SERT), and Norepinephrine (NET) transporters clear released neurotransmitter from the synapse via secondary active transport.

**Ref:** Sonders, M.S., Zhu, S.J., Zahniser, N.R., et al. (1997). "Multiple ionic conductances of the human dopamine transporter: the actions of dopamine and psychostimulants." *Journal of Neuroscience*, 17(3), 960–974.

### Transporter Uptake Rate (Michaelis-Menten)

$$
v_{\text{uptake}} = V_{\max} \frac{[\text{NT}]_{\text{extracellular}}}{K_m + [\text{NT}]_{\text{extracellular}}}
$$

### Drug Competition (Cocaine/SSRI Blockade)

$$
v_{\text{uptake}}^{\text{drug}} = V_{\max} \frac{[\text{NT}]}{K_m\left(1 + \frac{[\text{drug}]}{K_i}\right) + [\text{NT}]}
$$

| Transporter | $K_m$ (NT) | $K_i$ (cocaine) | $K_i$ (SSRI fluoxetine) |
|-------------|-----------|-----------------|------------------------|
| DAT | 0.2–2 μM | 0.2–0.5 μM | ~3,000 μM |
| SERT | 0.2–0.5 μM | 0.3 μM | 0.003 μM |
| NET | 0.1–0.5 μM | 0.05 μM | ~1,000 μM |

**Resulting extracellular NT rise after drug:**

$$
[\text{NT}]_{\text{ext}} = [\text{NT}]_{\text{baseline}} \cdot \frac{K_m(1 + [\text{drug}]/K_i)}{K_m}
$$

---

## 4.5 Monoamine Degradation — MAO Kinetics

**What it models:** Monoamine oxidase (MAO-A, MAO-B) degrades dopamine, serotonin, and norepinephrine in mitochondria. First-order intracellular degradation kinetics.

$$
\frac{d[\text{NT}]_{\text{intracell}}}{dt} = -k_{\text{MAO}} [\text{NT}]_{\text{intracell}}
$$

$$
v_{\text{MAO}} = V_{\max}^{\text{MAO}} \frac{[\text{NT}]}{K_m^{\text{MAO}} + [\text{NT}]}
$$

| Variable | Definition |
|----------|-----------|
| $k_{\text{MAO}}$ | First-order degradation rate constant |
| $K_m^{\text{MAO}}$ | MAO substrate affinity |
| Products | DA → DOPAC/HVA; 5-HT → 5-HIAA; NE → MHPG |

---

# 5. Acetylcholine System

## 5.1 Acetylcholinesterase (AChE) Enzyme Kinetics

**What it models:** AChE hydrolyzes ACh at the neuromuscular junction and CNS synapses. One of the fastest enzymes known (~25,000 reactions/sec/enzyme molecule). Inhibition by organophosphates or clinical drugs prolongs cholinergic transmission.

**Ref:** Massoulié, J. & Bon, S. (1982). "The molecular forms of cholinesterase and acetylcholinesterase in vertebrates." *Annual Review of Neuroscience*, 5, 57–106.

### AChE Michaelis-Menten Kinetics

$$
v_{\text{AChE}} = V_{\max}^{\text{AChE}} \frac{[\text{ACh}]}{K_m^{\text{AChE}} + [\text{ACh}]}
$$

### Substrate Inhibition at High [ACh]

AChE shows **substrate inhibition** at very high ACh concentrations (two ACh molecules can bind simultaneously, blocking catalysis):

$$
v_{\text{AChE}} = \frac{V_{\max}[\text{ACh}]}{K_m + [\text{ACh}](1 + [\text{ACh}]/K_{ss})}
$$

| Parameter | Definition | Values |
|-----------|-----------|--------|
| $K_m^{\text{AChE}}$ | Michaelis constant | 50–100 μM |
| $V_{\max}^{\text{AChE}}$ | Maximum hydrolysis rate | ~25,000 ACh/s per enzyme |
| $K_{ss}$ | Substrate inhibition constant | ~1 mM |

### Inhibitor Pharmacokinetics (Donepezil)

$$
v_{\text{inhibited}} = V_{\max} \frac{[\text{ACh}]}{K_m\left(1 + \frac{[\text{inhibitor}]}{K_i}\right) + [\text{ACh}]}
$$

**Donepezil (Alzheimer's drug):** $K_i \approx 6$ nM (extremely potent, reversible).

**Organophosphates (nerve agents):** Irreversible binding → $v_{\text{inhibited}} \to 0$.

---

## 5.2 Nicotinic ACh Receptor (nAChR) — Desensitization Kinetics

**What it models:** Rapid activation followed by desensitization (ligand-bound but closed state) — a hallmark of nicotinic receptors, especially α7. Explains why continuous nicotine exposure leads to receptor desensitization and upregulation.

**Ref:** Katz, B. & Thesleff, S. (1957). "A study of the 'desensitization' produced by acetylcholine at the motor end-plate." *Journal of Physiology*, 138(1), 63–80.

### Three-State Model (Resting → Active → Desensitized)

$$
R \overset{k_1[L]}{\underset{k_{-1}}{\rightleftharpoons}} R^* \overset{k_d}{\underset{k_{-d}}{\rightleftharpoons}} D
$$

### Open Probability

$$
P_o = \frac{k_1[L]/(k_{-1})}{1 + k_1[L]/k_{-1} + k_d/k_{-d}}
$$

### Desensitized Fraction

$$
f_D(t) = f_{D,\infty} + (f_{D,0} - f_{D,\infty}) e^{-t/\tau_D}
$$

| Variable | Definition | α7 nAChR | α4β2 nAChR |
|----------|-----------|----------|-----------|
| $\tau_D$ | Desensitization time constant | 1–10 ms (fast) | 100–1000 ms (slow) |
| $k_d$ | Desensitization rate | fast | slow |
| $f_{D,\infty}$ | Steady-state desensitized fraction | ~0.9 | ~0.5 |

---

# 6. Neuropeptides and Neuromodulators

## 6.1 Endocannabinoid Retrograde Signaling — DSI/DSE Model

**What it models:** Depolarization-induced suppression of inhibition (DSI) and excitation (DSE): postsynaptic neuron releases endocannabinoids (2-AG) that retrogradely suppress presynaptic transmitter release via CB1 receptors.

**Ref:** Wilson, R.I. & Nicoll, R.A. (2001). "Endogenous cannabinoids mediate retrograde signalling at hippocampal synapses." *Nature*, 410(6828), 588–592.

### 2-AG Synthesis (On-Demand from Postsynaptic Membrane)

$$
\frac{d[\text{2-AG}]}{dt} = k_{\text{syn}} \cdot [\text{Ca}^{2+}]_{\text{post}}^n - k_{\text{deg}} [\text{2-AG}]
$$

### CB1-Mediated Presynaptic Suppression

$$
P_{\text{release}}^{\text{CB1}} = P_{\text{release}}^{\text{baseline}} \cdot \frac{K_d^{CB1}}{K_d^{CB1} + [\text{2-AG}]_{\text{pre}}}
$$

### DSI Time Course

$$
\text{IPSC}_{\text{DSI}}(t) = \text{IPSC}_{\text{baseline}} \left[1 - f_{\text{DSI}} \cdot e^{-t/\tau_{\text{DSI}}}\right]
$$

| Parameter | Definition | Typical Values |
|-----------|-----------|----------------|
| $n$ | Ca²⁺ cooperativity for 2-AG synthesis | 2–4 |
| $k_{\text{deg}}$ | 2-AG degradation rate (by MAGL) | 0.1–0.5 s⁻¹ |
| $K_d^{CB1}$ | CB1 affinity for 2-AG | ~100 nM |
| $\tau_{\text{DSI}}$ | DSI recovery time constant | 5–30 s |
| $f_{\text{DSI}}$ | Fractional suppression | 30–70% |

---

## 6.2 Opioid Receptor — Gi-Coupled Inhibition

**What it models:** Mu opioid receptor (MOR) activation inhibits cAMP production, opens K⁺ channels (hyperpolarization), and closes Ca²⁺ channels — the molecular basis of opioid analgesia.

**Ref:** Connor, M. & Christie, M.D. (1999). "Opioid receptor signalling mechanisms." *Clinical and Experimental Pharmacology and Physiology*, 26(7), 493–499.

### cAMP Inhibition

$$
[\text{cAMP}](t) = [\text{cAMP}]_{\text{baseline}} \cdot \frac{1}{1 + [\text{opioid}]/IC_{50}}
$$

### K⁺ Current (GIRK Activation)

$$
I_K^{\text{opioid}} = g_K^{\text{GIRK}} (V_m - E_K) \cdot f_{\text{receptor,active}}
$$

### Pain Threshold (Sigmoidal Dose-Response)

$$
\text{Analgesia}(\%) = \frac{E_{\max}[\text{opioid}]^n}{EC_{50}^n + [\text{opioid}]^n}
$$

| Receptor | $E_{\max}$ | $EC_{50}$ (morphine) | Effect |
|----------|-----------|---------------------|--------|
| MOR (μ) | 100% | ~1–10 nM | Analgesia, euphoria, respiratory depression |
| KOR (κ) | ~60% | ~1–10 nM | Analgesia, dysphoria, diuresis |
| DOR (δ) | ~40% | ~1–10 nM | Analgesia, mood elevation |

---

## 6.3 HPA Axis — CRH-ACTH-Cortisol Cascade

**What it models:** The hypothalamic-pituitary-adrenal (HPA) stress axis. CRH released by hypothalamic PVN → pituitary ACTH release → adrenal cortisol → negative feedback on hypothalamus and pituitary.

**Ref:** Kyrylov, V., Severyanova, L.A. & Vieira, A. (2005). "Modeling robust oscillatory behavior of the hypothalamic-pituitary-adrenal axis." *IEEE Transactions on Biomedical Engineering*, 52(12), 1977–1983.

### 3-Compartment Cascade ODE System

$$
\frac{d[\text{CRH}]}{dt} = s_1 - d_1[\text{CRH}] - k_1[\text{CRH}][\text{Cortisol}]
$$

$$
\frac{d[\text{ACTH}]}{dt} = k_2 [\text{CRH}] - d_2 [\text{ACTH}] - k_3 [\text{ACTH}][\text{Cortisol}]
$$

$$
\frac{d[\text{Cortisol}]}{dt} = k_4 [\text{ACTH}] - d_3 [\text{Cortisol}]
$$

| Variable | Definition | Baseline Value |
|----------|-----------|----------------|
| $[\text{CRH}]$ | Hypothalamic CRH | 0–100 pg/mL |
| $[\text{ACTH}]$ | Pituitary ACTH | 10–50 pg/mL |
| $[\text{Cortisol}]$ | Adrenal cortisol | 5–20 μg/dL (morning peak) |
| $k_1, k_3$ | Negative feedback rate constants | — |
| $s_1$ | CRH synthesis rate | — |
| $d_1, d_2, d_3$ | Degradation rates | — |

**Circadian rhythm:** The HPA axis oscillates with ~24-hour period; cortisol peaks within 30–45 min of waking (Cortisol Awakening Response, CAR) and nadir at midnight. The oscillation emerges from the negative feedback loop combined with pulsatile secretion.

---

## 6.4 Adenosine — Homeostatic Sleep Pressure (Process S)

**What it models:** Adenosine accumulates during wakefulness (reflecting metabolic activity) and creates sleep pressure. This is the biochemical basis of the Two-Process Model of sleep regulation.

**Ref:** Borbély, A.A. (1982). "A two process model of sleep regulation." *Human Neurobiology*, 1(3), 195–204.

### Process S — Sleep Pressure Accumulation

$$
\frac{dS}{dt} = \begin{cases} \mu_w (S_{\text{upper}} - S) & \text{during wakefulness} \\ -\mu_s (S - S_{\text{lower}}) & \text{during sleep} \end{cases}
$$

### Adenosine Accumulation (Biochemical Implementation)

$$
\frac{d[\text{Ado}]}{dt} = k_{\text{prod}} \cdot r_{\text{firing}} - k_{\text{clear}} [\text{Ado}]
$$

**Caffeine mechanism:**

$$
[\text{A1R}_{\text{occupied}}] = \frac{[\text{Ado}]}{K_{d,\text{Ado}}\left(1 + \frac{[\text{caffeine}]}{K_{d,\text{caff}}}\right) + [\text{Ado}]}
$$

| Parameter | Definition | Typical Values |
|-----------|-----------|----------------|
| $\mu_w$ | Wake-time accumulation rate | ~0.5–1 h⁻¹ |
| $\mu_s$ | Sleep dissipation rate | ~0.3–0.5 h⁻¹ |
| $S_{\text{upper}}$ | Upper sleep threshold | 1.0 (normalized) |
| $S_{\text{lower}}$ | Lower wake threshold | 0 (normalized) |
| $K_{d,\text{Ado}}$ | A1R affinity for adenosine | ~100 nM |
| $K_{d,\text{caff}}$ | A1R affinity for caffeine | ~50 μM |

---

# 7. Intracellular Signaling Cascades

## 7.1 cAMP-PKA Signaling — Gs-Coupled Receptors (D1, β-adrenergic, 5-HT4)

**What it models:** Gs-coupled receptor activation (e.g., D1 dopamine receptor) → adenylyl cyclase → cAMP → PKA → phosphorylation of downstream targets (AMPAR, DARPP-32, CREB). The primary excitatory intracellular cascade.

**Ref:** Bhalla, U.S. & Iyengar, R. (1999). "Emergent properties of networks of biological signaling pathways." *Science*, 283(5400), 381–387.

### cAMP Production

$$
\frac{d[\text{cAMP}]}{dt} = k_{\text{AC}} [\text{Gs}^*] - k_{\text{PDE}} [\text{cAMP}]
$$

### PKA Activation

$$
[\text{PKA}^*] = \frac{[\text{cAMP}]^4}{K_A^4 + [\text{cAMP}]^4}
$$

(Hill coefficient $n = 4$ reflects the 4 cAMP binding sites on PKA holoenzyme)

### DARPP-32 Phosphorylation (Striatal Integration Hub)

$$
\frac{d[\text{pDARPP-32}]}{dt} = k_{\text{phos}} [\text{PKA}^*][\text{DARPP-32}] - k_{\text{dephos}} [\text{pDARPP-32}][\text{PP2B}]
$$

| Signal | Effect on DARPP-32 phosphorylation | Downstream consequence |
|--------|-----------------------------------|----------------------|
| D1 (DA burst) | Increases | Inhibits PP1 → amplifies phosphorylation signals |
| D2 (DA dip) | Decreases | Activates PP1 → promotes dephosphorylation |
| NMDA/Ca²⁺ (via PP2B) | Decreases | Calcineurin dephosphorylates DARPP-32 |

---

## 7.2 MAPK/ERK Cascade — Synaptic Plasticity Signaling

**What it models:** The MAPK cascade (Ras → Raf → MEK → ERK) activated downstream of NMDA, BDNF/TrkB, and dopamine receptors. ERK translocates to nucleus to activate CREB for long-term memory.

**Ref:** Bhalla, U.S. & Iyengar, R. (1999). *Science*, 283(5400), 381–387.

### Cascade (3-Tier Kinase Relay)

$$
\frac{d[\text{Ras}^*]}{dt} = k_1 [\text{GEF}][\text{Ras}] - k_{-1} [\text{Ras}^*]
$$

$$
\frac{d[\text{MEK}^*]}{dt} = k_2 [\text{Raf}^*][\text{MEK}] - k_{-2} [\text{MEK}^*]
$$

$$
\frac{d[\text{ERK}^*]}{dt} = k_3 [\text{MEK}^*][\text{ERK}] - k_{-3} [\text{ERK}^*]
$$

### Bistability and Switch-Like Behavior

The MAPK cascade exhibits **ultrasensitivity** (Hill-like response):

$$
[\text{ERK}^*]_{\text{ss}} \approx \frac{[\text{ERK}]_{\text{total}}}{1 + (K_{\text{half}} / [\text{stimulus}])^n}
$$

where $n \approx 5$–20 (emergent from cascade amplification), giving a switch-like all-or-none activation.

**Key insight:** The ultrasensitivity creates a threshold: weak stimuli produce no ERK activation; strong stimuli produce near-complete activation. This threshold determines which synaptic events are "tagged" for long-term memory consolidation.

---

## 7.3 Receptor Desensitization — β-Arrestin Internalization

**What it models:** Prolonged agonist exposure leads to GPCR phosphorylation by GRK → β-arrestin binding → receptor internalization → reduced sensitivity. Universal for all GPCRs (dopamine, serotonin, adrenergic receptors).

**Ref:** Lefkowitz, R.J. (1998). "G protein-coupled receptors." *Journal of Biological Chemistry*, 273(30), 18677–18680.

### Receptor Internalization Kinetics

$$
\frac{dR_s}{dt} = k_{\text{synth}} - k_{\text{int}} R_s \cdot f([A]) - k_{\text{deg}} R_s + k_{\text{rec}} R_i
$$

$$
\frac{dR_i}{dt} = k_{\text{int}} R_s \cdot f([A]) - k_{\text{rec}} R_i - k_{\text{deg,i}} R_i
$$

| Variable | Definition |
|----------|-----------|
| $R_s$ | Surface receptor density |
| $R_i$ | Internalized receptor density |
| $k_{\text{int}}$ | Internalization rate (increased by β-arrestin) |
| $k_{\text{rec}}$ | Recycling rate (receptor back to surface) |
| $f([A])$ | Agonist occupancy (0–1) |

**SSRI delayed onset:** 5-HT1A autoreceptors desensitize over 2–4 weeks with repeated SSRI exposure → reduced inhibitory feedback → increased 5-HT firing → therapeutic effect. This explains the 2–4 week lag for clinical antidepressant response.

---

# 8. Case Studies

## Case Study 1: Dopamine Synthesis — TH Rate Calculation

**Scenario:** Estimate dopamine synthesis rate in a substantia nigra neuron with and without end-product inhibition by accumulated dopamine.

**Given:**
- Tyrosine $[S] = 100$ μM, $K_m = 60$ μM, $V_{\max} = 50$ nM/min
- Cytoplasmic dopamine $[I] = 20$ μM, $K_i = 40$ μM (competitive inhibition)

**Without inhibition (Equation 1.1):**

$$
v = V_{\max} \frac{[S]}{K_m + [S]} = 50 \times \frac{100}{60 + 100} = 50 \times 0.625 = 31.25 \text{ nM/min}
$$

**With end-product inhibition (Equation 1.2):**

$$
v = 50 \times \frac{100}{60(1 + 20/40) + 100} = 50 \times \frac{100}{60(1.5) + 100} = 50 \times \frac{100}{190} = 26.3 \text{ nM/min}
$$

**Reduction:** $31.25 - 26.3 = 4.95$ nM/min (**16% reduction**)

**Interpretation:** Accumulated dopamine provides modest self-regulation. After a burst of firing (rapid vesicle release → temporary drop in cytoplasmic DA → $[I]$ decreases → inhibition relieved → synthesis increases). This homeostatic mechanism prevents long-term DA depletion.

---

## Case Study 2: GABA-A Developmental Reversal

**Scenario:** Calculate $E_{\text{Cl}}$ in an immature neuron (NKCC1-dominant) and a mature neuron (KCC2-dominant). Determine whether GABA is excitatory or inhibitory.

**Immature neuron:** $[\text{Cl}^-]_i = 35$ mM, $[\text{Cl}^-]_o = 110$ mM

$$
E_{\text{Cl}}^{\text{immature}} = \frac{61.5}{-1} \log_{10}\!\left(\frac{110}{35}\right) = -61.5 \times \log_{10}(3.14) = -61.5 \times 0.497 = -30.6 \text{ mV}
$$

**Mature neuron:** $[\text{Cl}^-]_i = 7$ mM, $[\text{Cl}^-]_o = 110$ mM

$$
E_{\text{Cl}}^{\text{mature}} = \frac{61.5}{-1} \log_{10}\!\left(\frac{110}{7}\right) = -61.5 \times \log_{10}(15.7) = -61.5 \times 1.196 = -73.5 \text{ mV}
$$

**Resting potential:** $V_{\text{rest}} = -70$ mV

| Neuron Stage | $E_{\text{Cl}}$ | $E_{\text{Cl}}$ vs $V_{\text{rest}}$ | GABA effect |
|---|---|---|---|
| Immature | −30.6 mV | $E_{\text{Cl}} > V_{\text{rest}}$ | Cl⁻ flows OUT → **Depolarizing (Excitatory)** |
| Mature | −73.5 mV | $E_{\text{Cl}} < V_{\text{rest}}$ | Cl⁻ flows IN → **Hyperpolarizing (Inhibitory)** |

**Interpretation:** GABA depolarizes immature neurons because intracellular Cl⁻ is high (flows out = positive charge out). This depolarization activates NMDA receptors and is critical for proper neuronal maturation and circuit formation. Clinical note: neonatal seizure treatment with phenobarbital (GABA-A agonist) may be paradoxically excitatory in neonates.

---

## Case Study 3: Dopamine Reward Prediction Error — Blocking Paradigm

**Scenario:** Simulate the Rescorla-Wagner prediction error in a blocking paradigm. A previously trained CS1 (bell) prevents learning to a new CS2 (light).

**Phase 1 — Train CS1 alone (10 trials, β=0.3, α=0.5, λ=1.0):**

$$
V_{\text{CS1}}^{(n+1)} = V_{\text{CS1}}^{(n)} + 0.5 \times 0.3 \times (1.0 - V_{\text{CS1}}^{(n)})
$$

After 10 trials: $V_{\text{CS1}} \approx 0.97$ (asymptotic)

**Phase 2 — Train CS1 + CS2 compound (5 trials):**

$$
\delta = \lambda - (V_{\text{CS1}} + V_{\text{CS2}}) = 1.0 - (0.97 + 0.0) = 0.03
$$

$$
\Delta V_{\text{CS2}} = \alpha_{\text{CS2}} \times \beta \times 0.03 = 0.5 \times 0.3 \times 0.03 = 0.0045
$$

After 5 compound trials: $V_{\text{CS2}} \approx 0.02$ (essentially no learning!)

**Result:** CS2 is "blocked" — no learning occurs because the compound total $\sum V \approx \lambda$ (already fully predicted).

**Neural mapping:** DA neurons show no burst response to US in Phase 2 (prediction error ≈ 0) → no LTP at CS2 synapses in amygdala/striatum. This is why blocking experiments were so important: they proved that dopamine encodes prediction error, not raw reward.

---

## Case Study 4: Caffeine and Adenosine — Sleep Pressure Suppression

**Scenario:** Calculate the fraction of A1 adenosine receptors blocked by a typical coffee dose.

**Given:**
- Adenosine $[\text{Ado}] = 150$ nM (after 16 hours of wakefulness)
- $K_{d,\text{Ado}} = 100$ nM
- Caffeine from 1 cup of coffee ≈ 1 μM (peak plasma)
- $K_{d,\text{caff}} = 50$ μM

**Unoccupied A1R without caffeine:**

$$
[\text{A1R}]_{\text{free}} = 1 - \frac{[\text{Ado}]}{K_{d,\text{Ado}} + [\text{Ado}]} = 1 - \frac{150}{100 + 150} = 1 - 0.60 = 40\%
$$

**With caffeine (competitive antagonist raises apparent $K_d$):**

$$
K_{d,\text{app}} = K_{d,\text{Ado}}\left(1 + \frac{[\text{caff}]}{K_{d,\text{caff}}}\right) = 100\left(1 + \frac{1}{50}\right) = 100 \times 1.02 = 102 \text{ nM}
$$

$$
[\text{A1R}]_{\text{adenosine-occupied}} = \frac{150}{102 + 150} = 59.5\%
$$

Without caffeine: **60% occupied** → strong sleep pressure

With caffeine: **59.5% occupied** → almost identical occupancy

**Interpretation:** Caffeine's effect is not to block most adenosine receptors — it barely changes occupancy! Rather, caffeine binds the unoccupied (~40%) receptors, preventing adenosine from producing additional inhibitory tone as brain activity increases during the day. The effect is **competitive prevention of increasing adenosine signal**, not blockade of existing sleep pressure. This explains why caffeine delays sleep onset but doesn't eliminate the need for sleep.

---

## Case Study 5: AChE Inhibition — Donepezil in Alzheimer's Disease

**Scenario:** In Alzheimer's disease, cholinergic neurons are lost, reducing synaptic ACh by ~40%. Calculate the effect of donepezil (AChE inhibitor) on synaptic ACh levels.

**Normal synapse:** $[\text{ACh}]_{\text{peak}} = 1$ mM (cleft), $K_m^{\text{AChE}} = 80$ μM, $V_{\max} = 100\%$

$$
v_{\text{normal}} = 100 \times \frac{1000}{80 + 1000} = 92.6\% \text{ of max rate}
$$

**Alzheimer's synapse (40% less ACh released):** $[\text{ACh}]_{\text{peak}} = 600$ μM

$$
v_{\text{AD}} = 100 \times \frac{600}{80 + 600} = 88.2\% \text{ of max rate}
$$

**With donepezil:** $K_i = 0.006$ μM, clinical dose gives $[\text{donepezil}] \approx 0.1$ μM

$$
K_m^{\text{app}} = 80\left(1 + \frac{0.1}{0.006}\right) = 80 \times 17.7 = 1,413 \text{ μM}
$$

$$
v_{\text{AD+donepezil}} = 100 \times \frac{600}{1413 + 600} = 29.8\% \text{ of max rate}
$$

**ACh clearance rate comparison:**

| Condition | AChE activity | Effective [ACh] |
|---|---|---|
| Normal | 92.6% | Normal |
| Alzheimer's | 88.2% | 40% less (less ACh released) |
| Alzheimer's + donepezil | 29.8% | Extended duration → compensates |

**Interpretation:** Donepezil reduces AChE activity by ~3-fold, slowing ACh clearance and prolonging its postsynaptic effect. This partially compensates for the reduced ACh release, improving cholinergic signaling. However, AChE is not completely blocked (would cause cholinergic crisis), allowing ACh to still be cleared after prolonged synaptic activity.

---

# 9. References

## Enzyme Kinetics

1. **Michaelis, L. & Menten, M.L.** (1913). Die Kinetik der Invertinwirkung. *Biochemische Zeitschrift*, 49, 333–369.

2. **Katz, B. & Thesleff, S.** (1957). A study of the 'desensitization' produced by acetylcholine at the motor end-plate. *Journal of Physiology*, 138(1), 63–80.

## Glutamate Receptors

3. **Destexhe, A., Mainen, Z.F. & Sejnowski, T.J.** (1994). Synthesis of models for excitable membranes, synaptic transmission and neuromodulation using a common kinetic formalism. *Journal of Computational Neuroscience*, 1(3), 195–230.

4. **Jahr, C.E. & Stevens, C.F.** (1990). Voltage dependence of NMDA-activated macroscopic conductances predicted by single-channel kinetics. *Journal of Neuroscience*, 10(9), 3178–3182.

5. **Danbolt, N.C.** (2001). Glutamate uptake. *Progress in Neurobiology*, 65(1), 1–105.

## GABA Receptors

6. **Dutar, P. & Nicoll, R.A.** (1988). A physiological role for GABA-B receptors in the central nervous system. *Nature*, 332(6160), 156–158.

7. **Ben-Ari, Y.** (2002). Excitatory actions of GABA during development: the nature of the nurture. *Nature Reviews Neuroscience*, 3(9), 728–739.

## Dopamine System

8. **Schultz, W., Dayan, P. & Montague, P.R.** (1997). A neural substrate of prediction and reward. *Science*, 275(5306), 1593–1599.

9. **Arnsten, A.F.T. & Goldman-Rakic, P.S.** (1998). Noise stress impairs prefrontal cortical cognitive function in monkeys. *Archives of General Psychiatry*, 55(4), 362–368.

10. **Leviel, V.** (2011). Dopamine release mediated by the dopamine transporter, facts and consequences. *Journal of Neurochemistry*, 118(4), 475–489.

## Norepinephrine System

11. **Aston-Jones, G. & Cohen, J.D.** (2005). An integrative theory of locus coeruleus-norepinephrine function: Adaptive gain and optimal performance. *Annual Review of Neuroscience*, 28, 403–450.

## Transporters

12. **Sonders, M.S., Zhu, S.J., Zahniser, N.R., et al.** (1997). Multiple ionic conductances of the human dopamine transporter. *Journal of Neuroscience*, 17(3), 960–974.

13. **Parsons, S.M.** (2000). Transport mechanisms in acetylcholine and monoamine storage. *FASEB Journal*, 14(15), 2423–2434.

## Acetylcholine

14. **Massoulié, J. & Bon, S.** (1982). The molecular forms of cholinesterase and acetylcholinesterase in vertebrates. *Annual Review of Neuroscience*, 5, 57–106.

## Neuropeptides and Neuromodulators

15. **Wilson, R.I. & Nicoll, R.A.** (2001). Endogenous cannabinoids mediate retrograde signalling at hippocampal synapses. *Nature*, 410(6828), 588–592.

16. **Connor, M. & Christie, M.D.** (1999). Opioid receptor signalling mechanisms. *Clinical and Experimental Pharmacology and Physiology*, 26(7), 493–499.

17. **Borbély, A.A.** (1982). A two process model of sleep regulation. *Human Neurobiology*, 1(3), 195–204.

18. **Kyrylov, V., Severyanova, L.A. & Vieira, A.** (2005). Modeling robust oscillatory behavior of the hypothalamic-pituitary-adrenal axis. *IEEE Transactions on Biomedical Engineering*, 52(12), 1977–1983.

## Signaling Cascades

19. **Bhalla, U.S. & Iyengar, R.** (1999). Emergent properties of networks of biological signaling pathways. *Science*, 283(5400), 381–387.

20. **Lefkowitz, R.J.** (1998). G protein-coupled receptors. *Journal of Biological Chemistry*, 273(30), 18677–18680.

---

*Back to: [Chapter 4 — Neurotransmitter Systems](../Neurotransmitter_Systems.md)*

*Next: [Chapter 5 — Neural Circuits and Networks Mathematical Equations](../../05_Neural_Circuits_And_Networks/Mathematical_Equations/)*
