# Chapter 12: Neuroendocrine and Neuroimmune Systems — Mathematical Equations

## Section 1: Blood-Brain Barrier Transport Kinetics

### 1.1 Carrier-Mediated Transport (Michaelis-Menten)

The rate of transport across the BBB for substrates requiring specific carriers (e.g., glucose via GLUT1, amino acids via LAT1):

$$v = \frac{V_{max}[S]}{K_m + [S]}$$

| Symbol | Meaning | Typical Value |
|---|---|---|
| $v$ | Transport velocity (flux; nmol·cm⁻²·min⁻¹) | — |
| $V_{max}$ | Maximum transport rate | 50–200 nmol·cm⁻²·min⁻¹ (glucose) |
| $[S]$ | Substrate concentration (mmol/L) | 5 (glucose in blood) |
| $K_m$ | Michaelis constant; half-saturation concentration | 1.7 (glucose/GLUT1) |

**Explanation**: As substrate concentration increases, transport accelerates initially (first-order) but plateaus as carriers become saturated. At plasma glucose (~5 mmol/L), GLUT1 operates near saturation, ensuring reliable glucose supply to brain despite fluctuations in blood levels.

---

### 1.2 Paracellular Diffusion and Lipophilicity

For passive transcellular diffusion through endothelial lipid bilayers (bypassing carriers), the permeability coefficient depends on octanol-water partition coefficient (lipophilicity):

$$P = P_0 \cdot \log(K_{ow})^{-0.5} \quad \text{or simplified} \quad P = k_p \cdot e^{-0.001 \cdot MW}$$

| Symbol | Meaning | Typical Value |
|---|---|---|
| $P$ | Permeability coefficient (cm/s) | $10^{-7}$ (hydrophilic) to $10^{-5}$ (lipophilic) |
| $P_0$ | Baseline permeability | Reference constant |
| $K_{ow}$ | Octanol-water partition coefficient (lipophilicity) | 0.01 (glucose) to 400 (lipophilic drugs) |
| $MW$ | Molecular weight (Da) | — |
| $k_p$ | Empirical permeability coefficient | ~0.001 cm/s |

**Explanation**: Lipophilic molecules (ethanol, anesthetics, lipid-soluble drugs) cross the BBB readily via transcellular diffusion; hydrophilic molecules are excluded. Molecular weight >400–500 Da without specific transporters cannot cross. This relationship explains why many therapeutic agents fail to penetrate the brain.

---

## Section 2: HPA Axis Dynamics

### 2.1 Cortisol-Mediated Negative Feedback

The suppression of CRH/ACTH release by circulating cortisol follows a sigmoidal (Hill) dose-response relationship:

$$\text{CRH release} = \text{CRH}_{basal} \cdot \left(1 - \frac{[Cortisol]^n}{IC_{50}^n + [Cortisol]^n}\right)$$

| Symbol | Meaning | Typical Value |
|---|---|---|
| $\text{CRH}_{basal}$ | Basal CRH secretion rate | 1.0 (arbitrary units) |
| $[Cortisol]$ | Plasma cortisol concentration (μmol/L) | 0.2–0.5 (basal); 0.5–1.0 (stress) |
| $IC_{50}$ | Cortisol concentration suppressing CRH by 50% | ~0.15–0.25 μmol/L |
| $n$ | Hill coefficient (steepness) | 1.5–2.0 |

**Explanation**: Cortisol inhibits both CRH (via parvocellular neurons) and ACTH (via corticotrophs) in a dose-dependent manner. At basal cortisol (~0.2 μmol/L), ~20% suppression occurs. At stress levels (~0.8 μmol/L), ~90% suppression is reached. The Hill coefficient >1 indicates cooperativity — steep suppression within a narrow cortisol range, allowing sharp on/off control.

---

### 2.2 Diurnal Cortisol Rhythm

Cortisol exhibits a characteristic circadian oscillation with highest levels at dawn (awakening) and lowest at midnight, superimposed on a declining exponential baseline over the 24-h cycle:

$$[Cortisol](t) = A_0 e^{-\lambda t} + A_c \cos\left(\frac{2\pi t}{T}\right) + C_{min}$$

| Symbol | Meaning | Typical Value |
|---|---|---|
| $A_0$ | Amplitude of exponential decline over 24 h | ~0.2 μmol/L |
| $\lambda$ | Exponential decay rate | ~0.03 h⁻¹ |
| $A_c$ | Amplitude of circadian oscillation | ~0.15 μmol/L |
| $T$ | Period (circadian; 24 h = 86,400 s) | 24 h |
| $t$ | Time of day (hours from midnight) | 0–24 h |
| $C_{min}$ | Minimum cortisol level (midnight) | ~0.05 μmol/L |

**Explanation**: The diurnal pattern emerges from SCN-driven circadian control of ACTH release via CRH. At ~6–8 AM, cortisol peaks (~0.5 μmol/L; facilitating awakening, metabolism, stress preparedness). By 11 PM, levels fall to ~0.05 μmol/L, promoting sleep. Chronotype (morning person vs. evening person) shifts this curve earlier or later. Disrupted circadian rhythm (shift work, jet lag) flattens the oscillation and elevates baseline — increasing metabolic disease and psychiatric risk.

---

### 2.3 Dexamethasone Suppression Test (DST) and Glucocorticoid Receptor Binding

Dexamethasone, a synthetic glucocorticoid, suppresses ACTH and cortisol via GR binding. The degree of suppression is described by:

$$\frac{[Cortisol]_{suppressed}}{[Cortisol]_{baseline}} = \frac{1}{1 + ([Dex]/IC_{50,Dex})^{n_{Dex}}}$$

| Symbol | Meaning | Typical Value |
|---|---|---|
| $[Dex]$ | Dexamethasone dose (μg/kg) | 0.5–8 μg/kg (low-dose DST: 0.5 μg/kg) |
| $IC_{50,Dex}$ | Dexamethasone concentration suppressing cortisol by 50% | ~0.001 μmol/L (high affinity for GR) |
| $n_{Dex}$ | Hill coefficient | 1.0–1.5 |
| $[Cortisol]_{baseline}$ | Pre-dexamethasone cortisol (8 AM; ~0.4–0.5 μmol/L) | — |
| $[Cortisol]_{suppressed}$ | Cortisol at 8–24 h post-dexamethasone | Expected <0.1 μmol/L if normal |

**Explanation**: In healthy individuals, 0.5 μg/kg dexamethasone suppresses next-morning cortisol to <0.1 μmol/L. Non-suppression (cortisol >0.1 μmol/L) indicates **DST resistance**, seen in major depression, Cushing's syndrome, and severe stress — reflecting either elevated baseline ACTH or impaired GR sensitivity. This test diagnoses hypercortisolism and treatment resistance.

---

## Section 3: Hypothalamic-Pituitary-Gonadal (HPG) Axis

### 3.1 GnRH Pulsatility and Gonadotropin Release

GnRH is released in pulses (~1 pulse per hour in humans) from hypothalamic neurons, driving FSH and LH secretion. The pulsatile pattern can be modeled as:

$$\text{GnRH}(t) = A \sum_{i} \exp\left(-\frac{(t - t_i)^2}{2\sigma_{pulse}^2}\right) + \text{baseline}$$

or as a square-wave pulse train:

$$\text{GnRH}(t) = \begin{cases} A & \text{if } t_i < t < t_i + \Delta t_{pulse} \\ \text{baseline} & \text{otherwise} \end{cases}$$

| Symbol | Meaning | Typical Value |
|---|---|---|
| $A$ | Amplitude of GnRH pulse | 0.5–10 nM (depending on assay) |
| $t_i$ | Time of $i$-th pulse | ~60 min apart |
| $\sigma_{pulse}$ | Duration of pulse (Gaussian SD) | ~10–15 min |
| $\Delta t_{pulse}$ | Width of pulse (square wave) | ~10–20 min |
| $\text{baseline}$ | Interpulse baseline GnRH | ~0.01–0.1 nM |

**Explanation**: GnRH pulsatility is essential for FSH/LH secretion. Too-slow pulses (<1/h) favor FSH; too-fast pulses (>2/h) favor LH. Pulse frequency is modulated by estradiol, progesterone, and kisspeptin neurons. Loss of pulsatility (as in hypogonadotropic hypogonadism or during GnRH agonist therapy) arrests gonadal function.

---

### 3.2 Estradiol-Driven FSH/LH Surge (Positive Feedback)

During the follicular phase, rising estradiol triggers a massive LH surge (positive feedback) when estradiol exceeds a threshold (~200 pg/mL). The surge can be modeled as:

$$[LH]_{surge} = [LH]_{basal} + A_{LH} \cdot f_{surge}(E_2)$$

where

$$f_{surge}(E_2) = \begin{cases} 0 & \text{if } [E_2] < E_2^{thresh} \\ \frac{([E_2] - E_2^{thresh})^n}{K_d^n + ([E_2] - E_2^{thresh})^n} & \text{if } [E_2] \geq E_2^{thresh} \end{cases}$$

| Symbol | Meaning | Typical Value |
|---|---|---|
| $[LH]_{basal}$ | Basal LH during follicular phase | 2–5 mIU/mL |
| $[LH]_{surge}$ | Peak LH during surge | 30–100 mIU/mL |
| $A_{LH}$ | Amplitude of surge | ~50–80 mIU/mL |
| $[E_2]$ | Plasma estradiol (pg/mL) | 100 (early follicular) → 300–400 (surge) |
| $E_2^{thresh}$ | Estradiol threshold for LH surge | ~200–250 pg/mL |
| $K_d$ | Half-saturation for surge activation | ~50 pg/mL (above threshold) |
| $n$ | Hill coefficient | 2.0–3.0 (steep threshold) |

**Explanation**: The LH surge (occurring ~36 h before ovulation) is triggered by sustained estradiol elevation above ~200 pg/mL for ~48 h. The high cooperativity ($n \approx 2$) ensures a sharp, switch-like surge. Progesterone, rising postovulation, suppresses the surge by shortening GnRH pulse frequency, re-establishing negative feedback.

---

## Section 4: Hypothalamic-Pituitary-Thyroid (HPT) Axis

### 4.1 TSH Suppression by T3/T4 (Thyroid Hormone Feedback)

TSH secretion is suppressed by circulating thyroid hormones (T3 and T4) via a Hill equation. T3 (the active form) is more potent than T4:

$$\text{TSH} = \text{TSH}_{max} \cdot \frac{1}{1 + \left(\frac{[T_3] + 0.1[T_4]}{IC_{50}^{TSH}}\right)^{n_{TSH}}}$$

| Symbol | Meaning | Typical Value |
|---|---|---|
| $[T_3]$ | Plasma T3 concentration (pmol/L) | 4–8 pmol/L |
| $[T_4]$ | Plasma T4 concentration (pmol/L) | 70–140 pmol/L |
| $IC_{50}^{TSH}$ | T3/T4 concentration suppressing TSH by 50% | ~4 pmol/L (T3-equivalent) |
| $n_{TSH}$ | Hill coefficient | 2.0–3.0 |
| $\text{TSH}_{max}$ | Maximal TSH in absence of inhibition | ~10 mIU/L |
| $\text{TSH}$ | Normal TSH | 0.5–2.5 mIU/L |

**Explanation**: Thyroid hormones exert negative feedback at the pituitary (direct suppression of TSH-secreting thyrotrophs) and hypothalamus (suppression of TRH). The factor 0.1 reflects that T4 is ~10× less potent than T3. In primary hypothyroidism (reduced T3/T4), TSH rises to 5–50+ mIU/L, driving the thyroid to produce more hormone (until exhaustion in complete hypothyroidism). In hyperthyroidism, TSH falls to <0.01 mIU/L.

---

## Section 5: Neuroinflammation and Cytokine Signaling

### 5.1 Microglial Activation Dynamics (Cytokine Production)

Activated microglia produce pro-inflammatory cytokines (TNF-α, IL-1β) in a concentration-dependent manner, modeled as second-order kinetics accumulation with degradation:

$$\frac{d[Cytokine]}{dt} = k_{prod} \cdot [Stimulus]^n - k_{deg} \cdot [Cytokine]$$

where $k_{prod}$ is the production rate constant and $k_{deg}$ is the degradation rate (TNF-α, IL-1β have half-lives ~20–30 min in tissue).

At steady state:

$$[Cytokine]_{ss} = \frac{k_{prod}}{k_{deg}} \cdot [Stimulus]^n$$

| Symbol | Meaning | Typical Value |
|---|---|---|
| $k_{prod}$ | Cytokine production rate constant | ~0.1–1.0 (nmol/mL·min) |
| $k_{deg}$ | Degradation rate constant | ~0.03–0.1 min⁻¹ (τ = 1/k_{deg} = 10–30 min) |
| $[Stimulus]$ | Microglial activator (LPS, ATP, IgG-opsonized debris) | Concentration-dependent |
| $n$ | Hill coefficient for stimulus cooperativity | 1.5–2.5 |
| $[Cytokine]_{ss}$ | Steady-state cytokine concentration | 10–100 nM (pathological) |

**Explanation**: Acute immune challenge (e.g., LPS from gram-negative bacteria) rapidly induces microglial TNF-α/IL-1β production (within minutes), peaking ~2–4 h post-challenge. Chronic stimulation (as in aging, neurodegeneration, or persistent viral/bacterial antigen) maintains elevated baseline cytokine levels, driving neuronal toxicity. NLRP3 inflammasome activation amplifies IL-1β production (secondary feedback).

---

### 5.2 Cytokine-Mediated Neuronal Excitotoxicity

TNF-α and IL-1β increase neuronal NMDA receptor surface expression and enhance glutamate-induced Ca²⁺ influx, leading to excitotoxic cascade. The relationship between cytokine concentration and NMDA calcium current can be modeled as:

$$I_{Ca}^{NMDA} = I_{max} \cdot \frac{[Cytokine]^n}{EC_{50}^n + [Cytokine]^n}$$

where $I_{Ca}^{NMDA}$ is the NMDA-mediated Ca²⁺ current (pA).

| Symbol | Meaning | Typical Value |
|---|---|---|
| $I_{max}$ | Maximum cytokine-enhanced Ca²⁺ current | 50–200 pA |
| $[Cytokine]$ | IL-1β or TNF-α concentration | 0.1–10 nM |
| $EC_{50}$ | Cytokine concentration enhancing current by 50% | ~1 nM |
| $n$ | Hill coefficient | 1.5–2.0 |
| $I_{Ca}^{NMDA}$ | NMDA-mediated calcium current | ~10–100 pA |

Excess Ca²⁺ influx activates:
- Proteases (calpains) → cytoskeletal breakdown
- Mitochondrial dysfunction → ROS production
- Apoptotic cascades (caspase-9, caspase-3)

**Explanation**: Chronic IL-1β elevation (seen in depression, Alzheimer's, aging) hyperactivates NMDA receptors and lowers the threshold for excitotoxic neuronal death. This mechanism links "inflammatory subtype" depression to synaptic loss and cognitive impairment.

---

### 5.3 Complement-Mediated Synaptic Tagging and Pruning

Weak synapses are tagged with complement proteins (C1q, then C3) — a mechanism of activity-dependent pruning. The fraction of synapses tagged can be modeled as:

$$f_{tagged} = \frac{1}{1 + e^{-\beta(\phi - \phi_0)}}$$

where $\phi$ is the synaptic strength (potentiation index; $\phi_0$ is the threshold for tagging).

Microglia with CR3 receptors recognize C3-tagged synapses and engulf them:

$$\text{Phagocytosis rate} = k_{phag} \cdot f_{tagged} \cdot [Microglia]$$

| Symbol | Meaning | Typical Value |
|---|---|---|
| $\beta$ | Steepness of tagging threshold | 5–10 |
| $\phi_0$ | Synaptic strength threshold for C1q tagging | 0.3–0.5 (relative units) |
| $\phi$ | Synaptic strength (LTP/synaptic weight) | 0–1 (normalized) |
| $k_{phag}$ | Phagocytic rate constant | ~0.01–0.1 (per min) |
| $[Microglia]$ | Local microglial density | 0.5–5 cells per 100 μm³ |

**Explanation**: During critical periods (especially adolescent synaptic pruning in PFC), complement activation removes weak synapses. In schizophrenia, genetic risk factors (C4 gene duplication, TREM2 variants) enhance complement-mediated pruning, leading to excessive synapse loss and cognitive deficits. Conversely, complement inhibition partially restores circuit function in preclinical models.

---

## Section 6: Gut-Brain Axis

### 6.1 Microbial Short-Chain Fatty Acid (SCFA) Production from Dietary Fiber

Colonic microbiota ferment insoluble dietary fiber to produce butyrate, propionate, and acetate. The production rate can be modeled as Michaelis-Menten kinetics:

$$v_{SCFA} = \frac{V_{max}^{SCFA} \cdot [Fiber]}{K_m^{Fiber} + [Fiber]}$$

| Symbol | Meaning | Typical Value |
|---|---|---|
| $v_{SCFA}$ | SCFA production rate (mmol/day) | 100–200 mmol/day (colon-wide) |
| $V_{max}^{SCFA}$ | Maximum SCFA production | ~300 mmol/day |
| $[Fiber]$ | Concentration of fermentable fiber in colon | 20–50 g/day → ~1–5 mM (effective) |
| $K_m^{Fiber}$ | Michaelis constant for fiber fermentation | ~1–2 mM |

Butyrate is produced at ~60% of total SCFA (200 mmol/day total → ~120 mmol/day butyrate).

**Explanation**: High-fiber diet (>25 g/day) supports SCFA production and maintains microbial diversity. Butyrate serves as the primary energy source for colonocytes, enhances intestinal barrier function (tight junctions), and crosses the BBB (via monocarboxylate transporters) to exert neuroprotective effects: (1) HDAC inhibition → histone acetylation → increased BDNF expression, (2) G-protein coupled receptor (GPR43, GPR109A) signaling → reduced neuroinflammation, (3) microglia suppression. Low-fiber diet (<10 g/day) reduces SCFA production and is associated with dysbiosis, increased inflammation, and cognitive impairment.

---

### 6.2 Tryptophan Depletion via Kynurenine Pathway

When IL-1β and TNF-α activate indoleamine 2,3-dioxygenase (IDO), tryptophan is catabolized to kynurenine, reducing serotonin synthesis. The competition can be modeled as:

$$\text{Serotonin synthesis} = k_1 \cdot [Trp] - k_{IDO} \cdot [Trp] \cdot [IL-1\beta]$$

or more formally:

$$\frac{[Serotonin]}{[Serotonin]_{baseline}} = \frac{1}{1 + \left(\frac{[IL-1\beta]}{IC_{50}^{IDO}}\right)^{n_{IDO}}}$$

| Symbol | Meaning | Typical Value |
|---|---|---|
| $[Trp]$ | Plasma tryptophan concentration (μmol/L) | 50–100 μmol/L (baseline) |
| $k_1$ | Tryptophan hydroxylase rate constant | ~0.01–0.1 (arbitrary units) |
| $k_{IDO}$ | IDO activity (tryptophan catabolism rate) | ~0.001–0.01 (per nmol IL-1β) |
| $[IL-1\beta]$ | Plasma/CSF IL-1β (pg/mL) | 1–5 (baseline); 50–500 (inflammation) |
| $IC_{50}^{IDO}$ | IL-1β concentration suppressing serotonin by 50% | ~10–50 pg/mL |
| $n_{IDO}$ | Hill coefficient | 1.5–2.0 |

**Explanation**: Inflammatory depression (elevated IL-1β, TNF-α in ~30% of MDD patients) activates IDO, shunting tryptophan away from serotonin synthesis and toward kynurenine metabolites (some of which are excitotoxic — quinolinic acid, KYNA). This explains why SSRIs show reduced efficacy in inflammatory depression; blocking tryptophan depletion (e.g., IDO inhibitors like indoximod) is a therapeutic target in development.

---

## Section 7: Circadian Molecular Clock

### 7.1 CLOCK/BMAL1 and PER/CRY Oscillator

The core clock mechanism is a transcriptional-translational feedback loop. A simplified model captures the essential negative feedback:

$$\frac{d[PER]}{dt} = k_1 \cdot [CLOCK/BMAL1] - k_2 \cdot [PER] - k_3 \cdot [PER] \cdot [PP2A]$$

$$\frac{d[CLOCK/BMAL1]}{dt} = k_4 - k_5 \cdot [PER]^n - k_6 \cdot [CLOCK/BMAL1]$$

At oscillatory steady state (limit cycle), these equations generate approximately 24-h oscillations. A more explicit form uses a phase variable:

$$\phi(t) = \frac{2\pi t}{T} + A \sin\left(\frac{2\pi t}{T} + \psi\right)$$

where $T \approx 24.2$ h in humans (free-running period without light).

| Symbol | Meaning | Typical Value |
|---|---|---|
| $[PER]$ | Per/Cry protein concentration (arbitrary) | ~0.5–3.0 a.u. (oscillates) |
| $[CLOCK/BMAL1]$ | CLOCK/BMAL1 dimer concentration | ~1.0–2.5 a.u. |
| $k_1, k_4$ | Transcription/translation rates | ~0.1–0.5 min⁻¹ |
| $k_2, k_3, k_5, k_6$ | Degradation/phosphorylation/inhibition rates | ~0.01–0.05 min⁻¹ |
| $n$ | Cooperativity of PER inhibition | 2–3 |
| $T$ | Free-running period | 24.2 h (humans); 23.5–24.5 h (range) |
| $\phi$ | Circadian phase (0–2π) | — |
| $\psi$ | Phase offset | — |

**Explanation**: The oscillator is a genetic toggle switch: CLOCK/BMAL1 drives Per/Cry transcription; PER/CRY proteins accumulate, translocate to the nucleus, and suppress CLOCK/BMAL1 activity; as PER/CRY degrade (via CK1ε phosphorylation and ubiquitin-proteasome degradation), CLOCK/BMAL1 activity resumes, restarting the cycle. Without external time cues, the period drifts (~24.2 h, slightly longer than 24 h), causing desynchrony if clock is not reset daily by light.

---

### 7.2 Melatonin Synthesis and Diurnal Rhythm

Melatonin is synthesized in the pineal gland exclusively during darkness (night), following a circadian rhythm controlled by SCN-driven sympathetic signaling (norepinephrine → β1-adrenergic receptors → cAMP → CREB → AANAT upregulation):

$$[Melatonin](t) = M_{peak} \cdot f(t)$$

where

$$f(t) = \begin{cases} 
e^{-(t - t_{onset})^2 / 2\sigma_{night}^2} & \text{if darkness phase} \\
M_{basal} & \text{if light phase}
\end{cases}$$

or a smooth sinusoidal model:

$$[Melatonin](t) = M_{basal} + M_{peak} \cdot \sin\left(\frac{2\pi(t - t_{offset})}{24}\right) \cdot \left[1 + \text{tanh}\left(k \cdot (Darkness - 0.5)\right)\right]$$

| Symbol | Meaning | Typical Value |
|---|---|---|
| $M_{peak}$ | Peak melatonin (midnight, darkness) | 50–200 pg/mL (CSF: 2–5× higher) |
| $M_{basal}$ | Daytime melatonin (light suppression) | <10 pg/mL |
| $t_{onset}$ | Evening melatonin rise (dusk + 1–2 h) | ~20:00–21:00 (8–9 PM) |
| $\sigma_{night}$ | Duration (SD) of melatonin elevation | ~4–6 h |
| $k$ | Steepness of light suppression | ~5–10 |
| $t_{offset}$ | Circadian phase offset from local time | —(−0.5 to +0.5 h, chronotype-dependent) |

**Explanation**: Melatonin peaks ~12 h after SCN activity minimum (circadian trough occurs ~2 AM; melatonin peaks ~2 PM of the previous night—wait, this needs correction: melatonin peaks at night, ~2 AM; SCN is most active during day, least active at night). Light-induced phase advances occur if light exposure happens before the melatonin minimum (subjective dawn); phase delays if after (subjective dusk). Dim light melatonin onset (DLMO, <10 lux) occurs ~2 h before sleep onset in most people. Melatonin receptor agonists (ramelteon, tasimelteon) and melatonin supplements shift circadian phase and promote sleep onset.

---

### 7.3 Phase Response Curve (PRC) — Light-Induced Circadian Phase Shifts

Light input to the SCN via melanopsin-expressing retinal ganglion cells (ipRGCs) shifts the circadian clock phase. The magnitude and direction of the shift depend on the circadian phase at which light is delivered:

$$\Delta\phi = A \cdot \sin\left(\phi - \phi_c\right) \cdot e^{-\lambda \cdot |I - I_{half}|}$$

or (Hill model):

$$\Delta\phi = \Delta\phi_{max} \cdot \frac{[Light]^{n}}{[Light]^{n} + I_{50}^{n}} \cdot h(\phi)$$

where $\Delta\phi$ is phase shift (hours), $\phi$ is current circadian phase, and $h(\phi)$ is a phase-dependent gating function.

| Symbol | Meaning | Typical Value |
|---|---|---|
| $\Delta\phi$ | Phase shift (hours; + = delay, − = advance) | ±1–4 h per 1–2 h light exposure |
| $A$ | Amplitude of PRC | ~1–4 h |
| $\phi$ | Current circadian phase (0–24 h; 0 = circadian midnight) | — |
| $\phi_c$ | Critical phase (maximum sensitivity) | ~14–16 h (early subjective night) |
| $[Light]$ | Light intensity (lux) | 100–10,000 lux |
| $I_{50}$ | Light intensity causing 50% max phase shift | 500–1000 lux |
| $n$ | Hill coefficient | 2–4 (steep dose-response) |
| $\lambda$ | Intensity saturation parameter | ~0.5–1.0 |

**Explanation**: Light in the early night (circadian hours 10–16) causes phase **delays** (shifts clock later, useful for evening light exposure to stay awake longer). Light in the late night/early morning (hours 20–4) causes phase **advances** (shifts clock earlier, useful for morning light exposure to wake earlier). Mid-day light has minimal effect. This PRC is the basis for chronotherapy: bright light (10,000 lux, 30 min) in early morning advances the clock; evening light delays it. Shift workers and jet-lagged travelers exploit this for re-entrainment.

---

## Section 8: BBB Tight Junction Integrity and Disruption

### 8.1 Claudin-5/ZO-1 Tight Junction Conductance

The electrical resistance of the BBB (a measure of paracellular permeability) depends on tight junction protein abundance. During BBB breakdown (stroke, inflammation), tight junction conductance increases (resistance decreases):

$$G_{BBB}(t) = G_0 - k_{loss} \cdot t$$

or (inflammation-driven):

$$G_{BBB} = G_{max} \cdot \frac{1}{1 + \left(\frac{[TNF-\alpha]}{IC_{50}^{TJ}}\right)^{n_{TJ}}}$$

where $G$ is conductance (1/Resistance, in mS/cm²) and increased conductance reflects BBB disruption.

| Symbol | Meaning | Typical Value |
|---|---|---|
| $G_0$ | Baseline tight junction conductance (intact BBB) | ~0.001–0.01 mS/cm² (very low, high-resistance barrier) |
| $G_{max}$ | Maximum conductance (disrupted BBB) | ~0.1–1.0 mS/cm² (leaky state) |
| $k_{loss}$ | Rate of tight junction protein loss | ~0.001–0.01 mS/(cm²·min) |
| $[TNF-\alpha]$ | TNF-α concentration in blood/CSF (pg/mL) | <5 (normal); 50–500 (stroke, inflammation) |
| $IC_{50}^{TJ}$ | TNF-α concentration causing 50% conductance increase | ~20–50 pg/mL |
| $n_{TJ}$ | Hill coefficient | 1.5–2.5 |

**Explanation**: The intact BBB has exceptionally high resistance (>1,500 Ω·cm²), preventing paracellular ion leakage and protein entry. TNF-α, IL-1β, and complement (C5a) induce internalization of claudin-5 and ZO-1, rapidly increasing conductance. During stroke, ischemic stress induces ROS production → degradation of tight junction proteins → BBB disruption within hours, allowing plasma proteins and immune cells to enter brain → edema and neuroinflammation. Therapeutic strategies include anti-TNF antibodies, tight junction protein stabilizers (e.g., VE-cadherin agonists), and Ang-1 mimetics to restore BBB integrity.

---

## Section 9: Sex Hormone Signaling

### 9.1 Estradiol Receptor Binding and Transcriptional Activation

Estradiol (E₂) binds to estrogen receptors (ERα, ERβ, GPER) and recruits coactivators to enhance transcription of target genes (e.g., BDNF, synaptic plasticity genes). Binding follows a Hill equation:

$$f_{bound} = \frac{[E_2]^{n_{ER}}}{K_d^{n_{ER}} + [E_2]^{n_{ER}}}$$

Transcriptional output:

$$\text{Gene expression} = \text{Basal} + A_{E2} \cdot f_{bound}$$

| Symbol | Meaning | Typical Value |
|---|---|---|
| $[E_2]$ | Free estradiol concentration (pM) | 10–100 pM (menstrual cycle average ~30 pM) |
| $K_d^{ER}$ | Dissociation constant for ER (ERα) | ~0.1–1 nM (~100–1000 pM) |
| $n_{ER}$ | Hill coefficient (cooperativity) | 1.0–1.5 |
| $f_{bound}$ | Fraction of ER bound by estradiol | 0–1 |
| $A_{E2}$ | Transcriptional amplitude (fold-change above basal) | 2–10× (gene-dependent) |

**Explanation**: Estradiol has high affinity for ERα (Kd ~100 pM), so at typical circulating levels (30–100 pM), receptors are 25–50% occupied. Increases in estradiol (e.g., during follicular phase surge to ~300 pM) saturate receptors, driving gene expression. This explains menstrual cycle-dependent changes in spine density (~2% hippocampal volume change), working memory, and mood. In perimenopause, estradiol fluctuations are erratic, potentially contributing to mood symptoms. HRT stabilizes estradiol, improving mood and cognition in some women.

---

### 9.2 Progesterone Metabolite (Allopregnanolone) Enhancement of GABA-A Receptors

Progesterone is metabolized to allopregnanolone (3α,5α-tetrahydroprogesterone) by 5α-reductase and 3α-HSD, respectively. Allopregnanolone acts as a positive allosteric modulator (PAM) of GABA-A receptors, enhancing chloride conductance:

$$g_{Cl}(V) = \bar{g}_{Cl} \cdot (1 + P_{allo}) \cdot \frac{[Cl^-]_o e^{-F V/RT} - [Cl^-]_i}{[Cl^-]_o + [Cl^-]_i e^{-F V/RT}}$$

where the effect of allopregnanolone is to increase the conductance by a factor $(1 + P_{allo})$:

$$P_{allo} = \frac{P_{max} \cdot [Allo]^n}{EC_{50}^n + [Allo]^n}$$

| Symbol | Meaning | Typical Value |
|---|---|---|
| $[Allo]$ | Allopregnanolone concentration (nM) | 0.5–5 nM (variable; luteal phase: 2–5 nM; follicular: <0.5 nM) |
| $EC_{50}$ | Allopregnanolone concentration producing 50% max effect | ~1–2 nM |
| $P_{max}$ | Maximum conductance enhancement | 2–5× (membrane hyperpolarization, GABA-A sensitization) |
| $n$ | Hill coefficient | 1–2 |
| $\bar{g}_{Cl}$ | Baseline chloride conductance (pS) | ~10–100 pS (single channel); picoSiemens |

**Explanation**: Allopregnanolone is a "neurosteroid" — allosteric modulator that does not require nuclear receptor binding. It enhances GABA-A sensitivity to GABA, increasing hyperpolarizing chloride current and reducing neuronal excitability. Luteal phase allopregnanolone elevations (~2–5 nM) produce anxiolytic and anticonvulsant effects. Postpartum, allopregnanolone crashes suddenly (progesterone clearance), potentially contributing to postpartum depression. Brexanolone (synthetic allopregnanolone) IV infusion rapidly improves postpartum depression (FDA-approved 2019), confirming the causal link. Menstrual-exacerbated seizures (catamenial epilepsy) are partly driven by allopregnanolone fluctuations.

---

## Section 10: Case Studies

### Case Study 10.1: HPA Axis Cortisol Suppression with Dexamethasone

**Scenario**: A 45-year-old woman with depression undergoes a dexamethasone suppression test (DST) to assess HPA axis integrity. She receives 0.5 μg/kg dexamethasone at 11 PM. Her baseline 8 AM cortisol is 0.45 μmol/L. Next morning (8 AM post-dex), her cortisol is measured.

**Calculations**:

1. **Expected suppression (normal)**: Using the equation from Section 2.3:
   $$\frac{[Cortisol]_{suppressed}}{[Cortisol]_{baseline}} = \frac{1}{1 + ([Dex] / IC_{50,Dex})^{1.2}}$$
   
   Assume $[Dex]$ post-absorption ≈ 0.003 μmol/L (typical peak post-0.5 μg/kg oral dose), $IC_{50,Dex}$ ≈ 0.001 μmol/L:
   
   $$\text{Suppression factor} = \frac{1}{1 + (0.003 / 0.001)^{1.2}} = \frac{1}{1 + 3^{1.2}} = \frac{1}{1 + 5.8} = 0.15$$
   
   Expected suppressed cortisol = 0.45 × 0.15 = **0.067 μmol/L** ✓ (Normal; <0.1 μmol/L)

2. **Observed cortisol**: 0.15 μmol/L (abnormally HIGH — indicates DST resistance)

3. **Interpretation**: Non-suppression suggests:
   - Increased ACTH drive (secondary to depression or HPA axis hyperactivity)
   - Reduced GR sensitivity (glucocorticoid resistance)
   - Elevated CRH/AVP drive

   **Conclusion**: Consistent with **major depressive disorder** (seen in ~50% of depressed patients). Predicts poorer response to antidepressants; may benefit from augmentation with anti-inflammatory agents (NSAIDs, IL-6 antagonists) if inflammatory subtype.

---

### Case Study 10.2: BBB Glucose Transport (GLUT1 Kinetics)

**Scenario**: Compare glucose transport across the BBB in a healthy brain vs. during acute ischemic stroke. Normal blood glucose = 5 mmol/L; cerebral capillary GLUT1 density is reduced by 50% during stroke (endothelial cell swelling, internalization).

**Calculations**:

Using Section 1.1 Michaelis-Menten equation:

1. **Normal BBB**:
   $$v = \frac{V_{max}[S]}{K_m + [S]} = \frac{100 \times 5}{1.7 + 5} = \frac{500}{6.7} = 74.6 \text{ nmol/(cm}^2\cdot\text{min)}$$

2. **During acute stroke** (Vmax reduced by 50%, i.e., Vmax = 50):
   $$v = \frac{50 \times 5}{1.7 + 5} = \frac{250}{6.7} = 37.3 \text{ nmol/(cm}^2\cdot\text{min)}$$

3. **Fold-change**: $37.3 / 74.6 = 0.5$ (50% reduction in glucose influx)

4. **Consequence**: Brain glucose supply falls 50% in stroke, exacerbating ischemic injury (reduced ATP → failure of Na⁺/K⁺-ATPase → cytotoxic edema, excitotoxicity). Hyperglycemia (blood glucose >10 mmol/L during stroke) paradoxically worsens outcome (lactate accumulation, acidosis).

**Clinical implication**: Tight glycemic control during acute stroke improves outcomes; hypoglycemia must also be avoided.

---

### Case Study 10.3: Circadian Melatonin Rhythm and Light Exposure

**Scenario**: A shift worker on night shift (sleep attempt 8 AM–4 PM) returns to day shift (sleep 11 PM–7 AM) and receives bright light therapy to re-entrain. Estimate melatonin suppression and re-entrainment time.

**Calculations**:

1. **Normal melatonin rhythm** (before shift change):
   - Night phase (~11 PM to 7 AM): Peak melatonin = 150 pg/mL at ~2 AM
   - Day phase: Melatonin <10 pg/mL
   - On night shift, melatonin rhythm is delayed by ~8 h (peaks ~10 AM in dark sleep environment)

2. **Light exposure effect** (Section 7.3, PRC):
   
   Assume bright light (5,000 lux) exposure at 7 AM (early morning):
   - Circadian phase at 7 AM (during night shift): ~φ = 14 h (early subjective night)
   - This is near the critical phase for phase **advance** (early night → delays clock, but morning light advances)
   
   Actually, clarify: If the worker's clock is delayed by 8 h, their circadian time is:
   - 7 AM real time = ~11 PM circadian time (early subjective night)
   - Early subjective night experiences phase delays (at night, light is unexpected and triggers delay)
   
   But 7 AM is morning, which should advance the clock. However, because the worker's internal clock is 8 h behind, 7 AM real = 11 PM on their circadian clock.
   
   Using approximate PRC data: early morning light (clock is delayed) can still produce advance if the light is bright enough to overcome the phase-advance zone boundary. Assume maximum phase advance of 1.5 h per 30 min light exposure at the critical phase:
   
   $$\Delta\phi = 1.5 \times \frac{[Light]}{[Light]_{ref}} = 1.5 \times \frac{5000}{5000} = 1.5 \text{ h/day}$$

3. **Re-entrainment timeline**:
   - Initial phase offset: 8 h
   - Daily advance via light: 1.5 h/day
   - Days to re-entrain: $8 \text{ h} / 1.5 \text{ h/day} \approx 5.3$ days
   
   **Expected melatonin at 8 AM after 5–6 days**:
   - Melatonin should decline toward <10 pg/mL by day 6
   - Sleep onset should shift from 8 AM (forced) back toward 11 PM

**Clinical outcome**: Bright light therapy (10,000 lux, 30 min) at 7 AM can re-entrain a circadian rhythm delayed by 8 h within ~5–7 days. Combined with sleep hygiene and melatonin timing (take melatonin ~2 h before desired bedtime), faster re-entrainment is achievable.

---

### Case Study 10.4: Cytokine-Induced Reduction in Hippocampal BDNF (Depression Model)

**Scenario**: An elderly patient (age 72) develops depression following a respiratory infection. Inflammatory markers are elevated: IL-1β = 8 pg/mL (normal <3), TNF-α = 6 pg/mL (normal <2). Model the effect on hippocampal BDNF over 4 weeks.

**Calculations**:

1. **Baseline BDNF** (no inflammation): 
   $$[BDNF]_{baseline} = 200 \text{ ng/mL (hippocampus)}$$

2. **IL-1β-driven suppression** (Section 6.2; repurposed for BDNF):
   
   Assume IL-1β suppresses BDNF via IDO (tryptophan depletion) and direct NF-κB signaling:
   $$\frac{[BDNF]}{[BDNF]_{baseline}} = \frac{1}{1 + \left(\frac{[IL-1\beta]}{IC_{50}^{BDNF}}\right)^{n_{BDNF}}}$$
   
   Let $IC_{50}^{BDNF} = 5$ pg/mL, $n_{BDNF} = 1.8$:
   
   $$\frac{[BDNF]}{[BDNF]_{baseline}} = \frac{1}{1 + (8/5)^{1.8}} = \frac{1}{1 + 1.6^{1.8}} = \frac{1}{1 + 3.1} = 0.24$$
   
   **[BDNF] = 200 × 0.24 = 48 ng/mL** (78% reduction)

3. **Over 4 weeks** (assuming IL-1β decreases as infection resolves; half-life ~2 weeks):
   
   Week 1: [IL-1β] = 8 pg/mL → [BDNF] ≈ 48 ng/mL
   
   Week 2: [IL-1β] = 6 pg/mL → [BDNF] ≈ 75 ng/mL (50% recovery)
   
   Week 3: [IL-1β] = 4 pg/mL → [BDNF] ≈ 120 ng/mL
   
   Week 4: [IL-1β] = 2 pg/mL → [BDNF] ≈ 170 ng/mL (approaching baseline)

4. **Neurobiological consequence**:
   - Reduced BDNF → impaired hippocampal synaptic plasticity (LTP) and neurogenesis
   - Cognitive impairment (memory, concentration) during week 1–2
   - Depression symptoms (low motivation, anhedonia) correlate with BDNF nadir
   - Recovery timeline: 3–4 weeks

**Therapeutic implications**: 
- NSAIDs (reduce IL-1β production)
- Antidepressants + anti-inflammatory agents (e.g., minocycline, IL-1 receptor antagonist anakinra in trials)
- Exercise (increases BDNF independently of cytokine reduction)
- Dietary SCFA/butyrate (suppresses IL-1β via GPR43)

---

### Case Study 10.5: Estradiol Effects on Hippocampal Spine Density (Menstrual Cycle)

**Scenario**: Track spine density in hippocampal CA1 pyramidal neurons across the menstrual cycle in a 28-year-old woman. Spine density correlates with synaptic strength and memory.

**Calculations**:

1. **Estradiol levels across cycle**:
   - Early follicular (day 1–5): [E₂] ≈ 30 pg/mL
   - Late follicular (day 8–14): [E₂] rises to 200–300 pg/mL (ovulation surge, day 14)
   - Early luteal (day 15–21): [E₂] drops to ~80 pg/mL (progesterone dominates)
   - Late luteal (day 22–28): [E₂] ≈ 60 pg/mL (pre-menstrual nadir)

2. **Spine density as function of estradiol** (using Section 9.1 ERα signaling):
   
   Assume baseline spine density at low E₂:
   $$\text{Spine density} = \text{Density}_{min} + (\text{Density}_{max} - \text{Density}_{min}) \cdot f_{ER}$$
   
   where
   $$f_{ER} = \frac{[E_2]^{1.2}}{500^{1.2} + [E_2]^{1.2}} \quad \text{(K}_d \approx 500 \text{ pM, adjusted for synaptic effects)}$$
   
   - Density_min = 8 spines/10 μm (low E₂)
   - Density_max = 10 spines/10 μm (high E₂)

3. **Cycle estimates**:
   
   **Early follicular (day 3; [E₂] = 30 pg/mL = 30 pM)**:
   $$f_{ER} = \frac{30^{1.2}}{500^{1.2} + 30^{1.2}} ≈ \frac{50}{1100} ≈ 0.045$$
   $$\text{Spine density} = 8 + (10 - 8) \times 0.045 = 8.09 \text{ spines/10 μm}$$
   
   **Late follicular (day 12; [E₂] = 250 pg/mL = 250 pM)**:
   $$f_{ER} = \frac{250^{1.2}}{500^{1.2} + 250^{1.2}} ≈ \frac{600}{1100} ≈ 0.55$$
   $$\text{Spine density} = 8 + 2 \times 0.55 = 9.1 \text{ spines/10 μm}$$
   
   **Early luteal (day 18; [E₂] = 80 pg/mL = 80 pM)**:
   $$f_{ER} ≈ 0.18 → \text{Spine density} ≈ 8.36 \text{ spines/10 μm}$$
   
   **Late luteal (day 26; [E₂] = 60 pg/mL = 60 pM)**:
   $$f_{ER} ≈ 0.12 → \text{Spine density} ≈ 8.24 \text{ spines/10 μm}$$

4. **Summary**:
   - Peak spine density: 9.1 spines/10 μm (late follicular; ~13% increase from baseline)
   - Minimum spine density: 8.09 spines/10 μm (early follicular)
   - Variation: ~1.3 spines/10 μm across cycle (~16% range)

5. **Cognitive correlate**:
   - Working memory and hippocampal-dependent memory are **enhanced in late follicular phase** (peak E₂)
   - Performance dips in early follicular and late luteal phases
   - Menstrual cycle effects on cognition are modest but reliable across studies

**Clinical note**: Oral contraceptives suppress this cycle (constant synthetic estrogen/progesterone) — effects on cognition and mood vary by formulation.

---

### Case Study 10.6: Microbiota-Derived Butyrate and Colonocyte Energy Supply

**Scenario**: Model butyrate accumulation in the colon over 24 h in a person consuming 40 g/day of fermentable fiber (e.g., inulin, resistant starch). Estimate butyrate clearance rate and steady-state concentration.

**Calculations**:

1. **Butyrate production** (Section 6.1, Michaelis-Menten):
   
   Assume [Fiber] in colonic lumen ~ 40 g/day = ~0.18 mol/day (MW ~200 g/mol for polysaccharide); concentration in luminal liquid (~400 mL) = 0.18/0.4 L ≈ 0.45 M (unrealistically high; use effective concentration post-absorption).
   
   More realistic: effective fermentable substrate concentration ~ 1–2 mM in colonic contents.
   
   Using Section 6.1:
   $$v_{SCFA} = \frac{V_{max}^{SCFA} \times [Fiber]}{K_m^{Fiber} + [Fiber]} = \frac{300 \times 1.5}{1.5 + 1.5} = \frac{450}{3} = 150 \text{ mmol/day}$$
   
   Butyrate = 60% of SCFA = 0.6 × 150 = **90 mmol/day** (consistent with literature: 60–120 mmol/day with high-fiber diet)

2. **Butyrate clearance** (absorbed by colonocytes, remainder excreted):
   
   - β-oxidation in colonocytes: ~90–95% of butyrate (energy source; yields ~8 ATP/butyrate via Krebs cycle)
   - Portal absorption + hepatic metabolism: ~5–10%
   - Fecal loss: <5 mmol/day
   
   Assume exponential absorption kinetics:
   $$[Butyrate]_{colonic} = \frac{v_{SCFA}}{k_{abs}} \times (1 - e^{-k_{abs} \times t})$$
   
   where $k_{abs}$ = absorption rate constant ~ 0.1–0.2 h⁻¹ (half-life ~ 3.5–7 h)

3. **Steady-state butyrate** (intestinal lumen):
   $$[Butyrate]_{ss} = \frac{v_{SCFA}}{k_{abs}} = \frac{90 \text{ mmol/day}}{0.15 \text{ h}^{-1} \times 24 \text{ h}} = \frac{90}{3.6} = 25 \text{ mmol}$$
   
   Concentration in ~400 mL colonic liquid: 25 mmol / 0.4 L = **62.5 mM** (typical: 50–100 mM)

4. **Fecal butyrate excretion**:
   - If ~5 mmol/day escapes absorption:
     $$\text{Fecal butyrate} = 5 \text{ mmol/day} = 5 \text{ mmol/day} \times 88 \text{ g/mol} = 0.44 \text{ g/day}$$

5. **Metabolic yield for colonocytes**:
   - 85 mmol/day absorbed × 8 ATP/butyrate = 680 mmol ATP/day (assumes complete β-oxidation)
   - Energy = 680 mmol × 30.5 kJ/mol ATP = 20.74 MJ/day (~5 kcal/g butyrate × 85 mmol/day)
   - Colonocyte ATP production: **~40–50% of total colonocyte ATP** (critical energy source; explains why butyrate depletion causes colitis)

6. **Health implications**:
   - High-fiber diet (40 g/day) → 90 mmol/day butyrate
   - Low-fiber diet (10 g/day) → ~20 mmol/day butyrate
   - Butyrate crosses BBB via MCT1 → neuroprotective effects (HDAC inhibition, anti-inflammatory)
   - Dysbiosis (reduced SCFA producers) → low butyrate → intestinal barrier dysfunction (reduced tight junction proteins) + reduced BDNF in hippocampus

**Recommendation**: Adequate fiber intake (25–35 g/day) maintains optimal butyrate production and gut-brain axis health.

---

## References

1. Zlokovic, B. V. (2008). The blood-brain barrier in health and chronic neurodegenerative disorders. *Neuron*, 57(2), 178–201.

2. Abbott, N. J., Patabendige, A. A., Dolman, D. E., Yusof, S. R., & Begley, D. J. (2010). Structure and function of the blood-brain barrier. *Neurobiology of Disease*, 37(1), 13–25.

3. Funder, J. W. (2010). The role of mineralocorticoid receptors in the cardiovascular system. *Journal of Steroid Biochemistry and Molecular Biology*, 120(2-3), 88–95.

4. Tsigos, C., & Chrousos, G. P. (2002). Hypothalamic-pituitary-adrenal axis, neuroendocrine factors and stress. *Journal of Psychosomatic Research*, 53(4), 865–871.

5. McEwen, B. S. (2008). Central effects of stress hormones in health and disease: Understanding the protective and damaging effects of stress and stress mediators. *European Journal of Pharmacology*, 583(2-3), 174–185.

6. Lightman, S. L., & Conway-Campbell, B. L. (2010). The crucial role of pulsatile activity of the HPA axis for continuous dynamic equilibration. *Nature Reviews Neuroscience*, 11(10), 710–718.

7. Marshall, J. C., & Eagleson, C. A. (1999). Neuroendocrine aspects of polycystic ovary syndrome. *Endocrinology and Metabolism Clinics of North America*, 28(2), 295–324.

8. Freeman, M. E., Kanyicska, B., Lerant, A., & Nagy, G. (2000). Prolactin: Structure, function, and regulation of secretion. *Physiological Reviews*, 80(4), 1523–1631.

9. De Vos, A., Ström, A., & Clapham, D. E. (2016). Calcium signaling. *Cold Spring Harbor Perspectives in Biology*, 8(6), a020907.

10. Merrill, A. H., & Sullards, M. C. (2002). Sphingolipid metabolism: Roles in signal transduction and other cellular processes. *Advances in Lipid Research*, 34, 115–175.

11. Beaulieu, J. M., & Gainetdinov, R. R. (2011). The physiology, signaling, and pharmacology of dopamine receptors. *Pharmacological Reviews*, 63(1), 182–217.

12. Dantzer, R., O'Connor, J. C., Freund, G. G., Johnson, R. W., & Kelley, K. W. (2008). From inflammation to sickness and depression: When the immune system subjugates the brain. *Nature Reviews Neuroscience*, 9(1), 46–56.

13. Baune, B. T., & Tully, P. J. (2014). Metabolic syndrome and inflammatory markers in major depressive disorder: A population-based, cross-sectional study. *Journal of Affective Disorders*, 165, 78–85.

14. Cryan, J. F., & Dinan, T. G. (2012). Mind-altering microorganisms: The impact of the gut microbiota on brain and behaviour. *Nature Reviews Neuroscience*, 13(10), 701–712.

15. Dinan, T. G., Stanton, C., & Cryan, J. F. (2013). Psychobiotics: A novel class of psychotropic. *Biological Psychiatry*, 74(10), 720–726.

16. Bourassa, M. W., Lesperance, M. M., Melendez, G. C., & Bowman, A. B. (2016). Manganese transporters, homeostasis, and disease. *Neurotoxicology*, 46, 35–45.

17. Dinan, T. G., & Cryan, J. F. (2017). Gut instincts: Microbiota as a key regulator of brain development, ageing and neurodegeneration. *The Journal of Physiology*, 595(2), 489–503.

18. Barclay, J. L., Husse, J., Bode, B., Naujokat, N., Meyer-Kovac, J., Schmid, S. M., & Lehnert, H. (2012). Circadian desynchrony promotes metabolic disruption in a mouse model of shiftwork. *PLOS ONE*, 7(5), e37150.

19. Panda, S., Antoch, M. P., Miller, B. H., et al. (2002). Coordinated transcription of key pathways in the mouse by the circadian clock. *Cell*, 109(3), 307–320.

20. Kohsaka, A., & Bass, J. (2007). A sense of time: How molecular clocks organize metabolism. *Trends in Endocrinology & Metabolism*, 18(1), 4–11.

21. Scheer, F. A., Hu, K., Evoniuk, H., Kelly, E. E., Malhotra, A., Hilton, M. F., & Shea, S. A. (2010). Impact of the human circadian system, exercise, and their interaction on cardiovascular function. *PNAS*, 107(47), 20541–20546.

22. Tetel, M. J., de Vries, G. J., Melcangi, R. C., Panzica, G., & O'Mahony, S. M. (2018). Steroids, stress and the gut microbiome: Alterations in the estrobolome by stressors and steroids. *Psychoneuroendocrinology*, 104, 104–113.

23. Engler-Chiurzoza, E. B., & Iadecola, C. (2020). Sex and gender differences in Alzheimer's disease: Focus on the ER. *Current Opinion in Behavioral Sciences*, 35, 92–98.

24. Moran, L. J., Misso, M. L., Wild, R. A., & Norman, R. J. (2010). Impaired glucose tolerance, type 2 diabetes and metabolic syndrome in polycystic ovary syndrome: A systematic review and meta-analysis. *Human Reproduction Update*, 16(4), 347–363.

25. Klingerman, C. M., Tchantchou, F., Kakarla, S. K., Shanmugam, S., Rowe, W. B., Meade, M., & Pauly, J. R. (2011). Interactions between aging and Parkinson's disease in transgenic mice. *Neurochemistry International*, 58(7), 739–747.

---

**End of Chapter 12 — Neuroendocrine and Neuroimmune Systems**
