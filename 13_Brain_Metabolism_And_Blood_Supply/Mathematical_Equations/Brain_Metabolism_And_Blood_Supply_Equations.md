# Chapter 13: Brain Metabolism and Blood Supply — Mathematical Equations

## Section 1: Brain Energy Budget and ATP Demand

### 1.1 Brain ATP Consumption Breakdown

The brain consumes ATP at a rate proportional to its mass and metabolic intensity. The total ATP consumption is distributed among three major processes:

$$\text{ATP}_{total} = \text{ATP}_{Na^+/K^+-ATPase} + \text{ATP}_{synaptic} + \text{ATP}_{other}$$

with approximate proportions:

$$\text{ATP}_{Na^+/K^+-ATPase} \approx 0.50 \cdot \text{ATP}_{total}$$
$$\text{ATP}_{synaptic} \approx 0.25 \cdot \text{ATP}_{total}$$
$$\text{ATP}_{other} \approx 0.25 \cdot \text{ATP}_{total}$$

The total brain ATP consumption rate can also be expressed as:

$$\text{ATP consumption rate} = \frac{P_{brain}}{E_{ATP}}$$

| Symbol | Meaning | Typical Value |
|---|---|---|
| $P_{brain}$ | Brain metabolic power | ~20 watts (1,400 kcal/day) |
| $E_{ATP}$ | Energy per ATP hydrolysis | 30.5 kJ/mol (−ΔG° under physiological conditions) |
| $\text{ATP}_{total}$ | Total brain ATP consumption | ~90 mmol/day or ~6 mmol/min |
| $\text{ATP}_{Na^+/K^+-ATPase}$ | ATP for maintaining ion gradients | ~45 mmol/day |

**Explanation**: The Na⁺/K⁺-ATPase (Na⁺/K⁺-pump) is the single largest ATP consumer in the brain (~50% of all ATP), reflective of the enormous cost of maintaining transmembrane ion gradients—each neuron fires hundreds of action potentials per second, allowing Na⁺ influx and K⁺ efflux that must be reversed. Synaptic transmission (glutamate release, AMPA/NMDA receptor opening, reuptake) accounts for ~25%. The remaining 25% covers protein synthesis, mRNA processing, axonal transport, and other housekeeping processes.

---

### 1.2 ATP Yield from Glucose Oxidation

Complete glucose oxidation to CO₂ and H₂O generates approximately 30–32 ATP per glucose molecule under physiological conditions (theoretical maximum ~38 ATP, but the proton gradient across the inner mitochondrial membrane reduces the yield):

$$\text{Glucose} + 6\,\text{O}_2 + n\,\text{ADP} + n\,\text{P}_i \rightarrow 6\,\text{CO}_2 + 6\,\text{H}_2\text{O} + n\,\text{ATP}$$

where $n \approx 30–32$.

The breakdown is:
- **Glycolysis**: 2 ATP (net) + 2 NADH → ~5 ATP equivalent
- **Pyruvate dehydrogenase**: Converts 2 pyruvate to 2 acetyl-CoA (2 NADH → ~5 ATP equivalent)
- **TCA cycle**: 2 turns yield 6 NADH (~15 ATP) + 2 FADH₂ (~3 ATP) + 2 GTP/ATP (2 ATP) = ~20 ATP
- **Total**: ~2 + 5 + 5 + 20 = **32 ATP/glucose**

| Symbol | Meaning | Typical Value |
|---|---|---|
| $n$ | ATP yield per glucose | 30–32 ATP |
| $P_1$ | ATP from glycolysis | 2 ATP net |
| $P_2$ | ATP equivalents from pyruvate oxidation to acetyl-CoA | ~5 ATP |
| $P_3$ | ATP from TCA cycle + ETC | ~25 ATP |
| $\Delta G^\circ'$ | Standard free energy of glucose oxidation | −2,870 kJ/mol |
| $E_{ATP}$ | Energy released per ATP hydrolysis | 30.5 kJ/mol |
| Efficiency | Energy captured as ATP / total energy released | ~33% |

**Explanation**: Under basal brain metabolism (~5.6 mg glucose/100g/min), the brain oxidizes approximately 100 g glucose per day. This yields ~3,200 mmol ATP per day, sustaining the 90 mmol ATP per day needed by the brain. The 33% efficiency of ATP capture reflects the inevitable thermodynamic loss due to the need to maintain a large proton gradient.

---

## Section 2: Glucose Transport and Cellular Metabolism

### 2.1 Endothelial GLUT1 and Neuronal GLUT3 Transport

Glucose enters the brain via GLUT1 (predominantly on endothelial cells of the BBB and on astrocytes) and is taken up by neurons via GLUT3. Both follow Michaelis-Menten kinetics (see Chapter 12, Section 1):

$$v_{GLUT1} = \frac{V_{max}^{GLUT1} \cdot [Glucose]_{blood}}{K_m^{GLUT1} + [Glucose]_{blood}}$$

$$v_{GLUT3} = \frac{V_{max}^{GLUT3} \cdot [Glucose]_{astrocyte}}{K_m^{GLUT3} + [Glucose]_{astrocyte}}$$

| Symbol | Meaning | Typical Value |
|---|---|---|
| $v_{GLUT1}, v_{GLUT3}$ | Glucose transport velocity (flux) | — |
| $V_{max}^{GLUT1}$ | Maximum GLUT1 transport rate | ~100–150 nmol/(cm²·min) |
| $V_{max}^{GLUT3}$ | Maximum GLUT3 transport rate | ~50–100 nmol/(min·mg protein) |
| $K_m^{GLUT1}$ | Michaelis constant for GLUT1 | ~1.7 mmol/L |
| $K_m^{GLUT3}$ | Michaelis constant for GLUT3 (lower affinity than GLUT1) | ~0.5–1.0 mmol/L |
| $[Glucose]_{blood}$ | Blood glucose concentration | 5 mmol/L (fasting); 4–6 mmol/L (normal range) |
| $[Glucose]_{astrocyte}$ | Astrocytic glucose concentration | ~1–2 mmol/L |

**Explanation**: GLUT1 has a higher Km than GLUT3, meaning GLUT1 is more efficient at low glucose concentrations, ensuring steady BBB glucose supply. GLUT3's lower Km means neurons preferentially take up glucose when astrocyte glucose is available. The two-step uptake (blood → astrocyte via GLUT1; astrocyte → neuron via gap junctions or via GLUT3) allows metabolic regulation and coupling of glucose supply to astrocytic glutamate handling.

---

### 2.2 Astrocyte Glycolysis and Pyruvate Production

Astrocytes are more glycolytic than neurons and constitute the primary site of glucose metabolism in response to increased glutamatergic activity. The rate of glycolysis can be modeled as:

$$v_{glycolysis} = k_1 \cdot [Glucose]_{astrocyte} \cdot f(activity)$$

where $f(activity)$ depends on intracellular calcium or glutamate uptake signals:

$$f(activity) = 1 + \frac{([Ca^{2+}]_{in} - [Ca^{2+}]_{baseline})}{K_{Ca}}$$

The pyruvate and NADH produced can be used locally or exported:

$$2\,\text{Glucose} \rightarrow 4\,\text{Pyruvate} + 4\,\text{NADH} + 4\,\text{ATP (net)}$$

| Symbol | Meaning | Typical Value |
|---|---|---|
| $v_{glycolysis}$ | Glycolytic flux in astrocytes | ~0.5–2.0 μmol/(min·mg protein) |
| $k_1$ | Rate constant for glucose consumption | ~0.01–0.1 min⁻¹ |
| $[Ca^{2+}]_{in}$ | Intracellular astrocytic Ca²⁺ during activity | ~0.5–1.0 μM |
| $[Ca^{2+}]_{baseline}$ | Baseline astrocytic Ca²⁺ (resting) | ~0.1 μM |
| $K_{Ca}$ | Sensitivity constant for Ca²⁺-mediated activation | ~0.2 μM |
| $f(activity)$ | Activity-dependent stimulation factor | 1–5× (depending on neural activity) |

**Explanation**: Glutamatergic synaptic activity → astrocytic glutamate uptake via EAAT1/2 → astrocytic depolarization and Ca²⁺ influx → increased glycolytic enzyme activity (especially phosphofructokinase, the rate-limiting step). This activity-dependent glycolysis is the foundation of the astrocyte-neuron lactate shuttle (ANLS), linking neural activity to energy supply.

---

## Section 3: Astrocyte-Neuron Lactate Shuttle (ANLS)

### 3.1 Lactate Production and Export from Astrocytes

In response to neuronal glutamatergic activity, astrocytes produce lactate via glycolysis and export it via monocarboxylate transporters (MCT1 on astrocyte membranes). The rate of lactate production depends on glycolytic flux:

$$v_{lactate, prod} = 2 \cdot v_{glycolysis} \quad \text{(1 glucose → 2 lactate)}$$

Lactate export follows carrier kinetics:

$$v_{lactate, export} = \frac{V_{max}^{MCT1} \cdot [Lactate]_{astrocyte}}{K_m^{MCT1} + [Lactate]_{astrocyte}}$$

At steady state (during sustained activity):

$$[Lactate]_{astrocyte, ss} = \frac{V_{max}^{MCT1} \cdot K_m^{MCT1}}{v_{prod} - v_{export}}$$

| Symbol | Meaning | Typical Value |
|---|---|---|
| $v_{lactate, prod}$ | Lactate production rate in astrocytes | ~1.0–4.0 μmol/(min·mg protein) |
| $v_{lactate, export}$ | Lactate export rate via MCT1 | ~0.5–2.0 μmol/(min·mg protein) |
| $V_{max}^{MCT1}$ | Maximum MCT1 transport rate | ~200–500 nmol/(cm²·min) |
| $K_m^{MCT1}$ | Michaelis constant for MCT1 | ~4–5 mmol/L |
| $[Lactate]_{astrocyte}$ | Intracellular astrocytic lactate | ~2–5 mmol/L during activity |

**Explanation**: During active neural transmission, astrocytes produce lactate faster than it can be oxidized locally, causing lactate to accumulate and be exported. This lactate is taken up by nearby neurons via MCT2 (lower Km, ~0.5–1 mmol/L) and oxidized in mitochondria. The ANLS hypothesis suggests this coupling ensures active neurons receive preferential fuel delivery from surrounding astrocytes—a form of activity-dependent metabolic support.

---

### 3.2 Neuronal Lactate Uptake and Oxidation

Neurons import lactate via MCT2 and convert it to pyruvate via lactate dehydrogenase (LDH), then to acetyl-CoA for oxidative metabolism:

$$\text{Lactate} \rightarrow \text{Pyruvate} \rightarrow \text{Acetyl-CoA} \rightarrow \text{TCA cycle} \rightarrow 15\,\text{ATP} \text{ (per lactate)}$$

This is 6 ATP less than glucose (which yields ~32 ATP), but it does not require glycolysis and proceeds directly to the TCA cycle. The rate of neuronal lactate uptake:

$$v_{lactate, neuron} = \frac{V_{max}^{MCT2} \cdot [Lactate]_{extracellular}}{K_m^{MCT2} + [Lactate]_{extracellular}}$$

| Symbol | Meaning | Typical Value |
|---|---|---|
| $V_{max}^{MCT2}$ | Maximum MCT2 transport rate | ~50–100 nmol/(cm²·min) |
| $K_m^{MCT2}$ | Michaelis constant for MCT2 | ~0.5–1.0 mmol/L |
| $[Lactate]_{extracellular}$ | Brain interstitial lactate (extracellular) | ~1–2 mmol/L (resting); ~3–5 mmol/L during activity |
| ATP yield per lactate | Energy from complete oxidation | ~15 ATP |

**Explanation**: Lactate is a more efficient fuel than glucose for direct neuronal energy production because it bypasses glycolysis, yielding 15 ATP per lactate (vs 16 ATP per half-glucose equivalent). During intense activity, elevated extracellular lactate signals adequate fuel availability and supports the increase in neuronal ATP demand. Exercise-induced lactate elevation in blood also crosses the BBB and may explain some cognitive benefits of aerobic exercise.

---

## Section 4: Alternative Brain Fuels

### 4.1 Ketone Body Metabolism

During prolonged fasting, low-carbohydrate diet (ketogenic diet), or starvation, the liver produces ketone bodies (β-hydroxybutyrate, acetoacetate) from fatty acid oxidation. Ketones cross the BBB via MCT1 transporters and are metabolized in mitochondria:

$$\text{β-hydroxybutyrate} \rightarrow \text{Acetoacetate} \rightarrow 2\,\text{Acetyl-CoA} \rightarrow \text{TCA cycle} \rightarrow 29\,\text{ATP}$$

The rate of ketone utilization by the brain follows Michaelis-Menten kinetics:

$$v_{ketone} = \frac{V_{max}^{ketone} \cdot [Ketones]_{blood}}{K_m^{ketone} + [Ketones]_{blood}}$$

| Symbol | Meaning | Typical Value |
|---|---|---|
| $[Ketones]_{blood}$ | Plasma ketone concentration | 0.1–0.2 mmol/L (fed state); 1–5 mmol/L (fasting); 5–10 mmol/L (ketogenic diet) |
| $K_m^{ketone}$ | Michaelis constant for ketone transporters | ~1–2 mmol/L |
| $V_{max}^{ketone}$ | Maximum ketone utilization rate | ~50–100 μmol/(min·100g brain) |
| ATP yield per ketone pair | Energy from β-hydroxybutyrate (2 acetyl-CoA) | 29 ATP |

**Explanation**: Ketones are more oxygen-efficient than glucose — they yield 29 ATP per molecule vs 32 ATP per glucose, but each ketone is derived from one 4-carbon acetoacetyl-CoA precursor, so the molar yield is comparable. Crucially, ketones produce **less ROS** (reactive oxygen species) during oxidation, making them neuroprotective under hypoxic/ischemic conditions. The brain can derive up to 60–70% of its ATP from ketones during prolonged fasting, reducing glucose requirement. Therapeutic ketosis is used for drug-resistant epilepsy and is under investigation for Alzheimer's disease and stroke neuroprotection.

---

### 4.2 Lactate as Circulating Fuel

Beyond local ANLS, circulating blood lactate (from skeletal muscle during exercise or hepatic gluconeolysis) crosses the BBB and can supply neuronal energy:

$$v_{lactate, blood} = \frac{V_{max}^{MCT1-BBB} \cdot [Lactate]_{blood}}{K_m^{MCT1-BBB} + [Lactate]_{blood}}$$

Typical blood lactate is <2 mmol/L at rest, rising to 5–20 mmol/L during intense exercise. The brain extracts lactate proportionally to its concentration:

$$\text{Lactate uptake}_{brain} = CBF \times ([Lactate]_{arterial} - [Lactate]_{venous})$$

| Symbol | Meaning | Typical Value |
|---|---|---|
| $[Lactate]_{blood}$ | Plasma lactate concentration | 1–2 mmol/L (resting); 5–20 mmol/L (exercise) |
| $CBF$ | Cerebral blood flow | ~750 mL/min (whole brain) |
| Lactate extraction fraction | Brain lactate uptake / arterial lactate | ~5–20% (varies with activity) |

**Explanation**: During endurance exercise, circulating lactate rises dramatically and the brain extracts 5–20% of arterial lactate, supplementing local glucose and astrocytic lactate. This lactate-driven fuel supply may contribute to exercise's cognitive benefits (improved mood, alertness, neuroplasticity) via both direct ATP supply and lactate signaling (lactate activates G-protein coupled receptors like GPR81, which modulates neuroinflammation and BDNF).

---

## Section 5: Cerebral Blood Flow Regulation

### 5.1 CO₂-Mediated Vasodilation (Metabolic Regulation)

Carbon dioxide is the most potent cerebral vasodilator. Increased arterial PCO₂ (hypercapnia) lowers local pH and causes arteriolar smooth muscle relaxation, increasing cerebral blood flow. The relationship is nearly linear:

$$\Delta CBF = \text{CBF}_{baseline} \times k_{CO_2} \times (\Delta P_{aCO_2})$$

or in terms of vascular conductance:

$$G_{vascular} = G_0 \times (1 + k_{CO_2} \times (P_{aCO_2} - P_{aCO_2,ref}))$$

| Symbol | Meaning | Typical Value |
|---|---|---|
| $CBF_{baseline}$ | Baseline cerebral blood flow | ~50 mL/(min·100g) |
| $k_{CO_2}$ | CO₂ sensitivity coefficient | ~4% CBF change per mmHg PaCO₂ change |
| $\Delta P_{aCO_2}$ | Change in arterial CO₂ partial pressure | ±5 mmHg |
| $P_{aCO_2}$ | Arterial CO₂ partial pressure | 35–45 mmHg (normal; ~40 mmHg) |
| $G_{vascular}$ | Vascular conductance | — |

**Example**: 
- Hyperventilation → PaCO₂ drops from 40 to 35 mmHg (−5 mmHg) → CBF drops ~20% → CBF ≈ 40 mL/(min·100g)
- Hypercapnia (breath-holding) → PaCO₂ rises to 50 mmHg (+10 mmHg) → CBF increases ~40% → CBF ≈ 70 mL/(min·100g)

**Explanation**: CO₂/H⁺ acts on arteriolar smooth muscle directly (acidosis → relaxation) and on astrocytes (increased intracellular H⁺ → reduced pH → astrocytic signaling). This mechanism is clinically exploited: hyperventilation temporarily reduces intracranial pressure in acute brain injury (by reducing cerebral blood volume), while hypercapnia increases it. The CO₂-flow coupling is essential for matching blood supply to metabolic demand.

---

### 5.2 Myogenic Autoregulation (Pressure-Flow Relationship)

The brain maintains relatively constant blood flow across a wide range of mean arterial pressures (MAP) via myogenic regulation—smooth muscle cells of cerebral arterioles contract in response to increased pressure (stretch) and relax in response to decreased pressure. This autoregulation is described by:

$$CBF = CBF_{ref} \quad \text{for} \quad 60 < MAP < 150 \text{ mmHg}$$

Outside this range:
- **Below 60 mmHg MAP**: Vasodilation reaches maximum; cerebral ischemia begins; CBF drops below critical threshold
- **Above 150 mmHg MAP**: Vasoconstriction reaches maximum; breakthrough autoregulation fails; hydrostatic pressure overcomes vasodilation → cerebral edema

The autoregulatory efficiency can be expressed as:

$$\text{Autoregulatory index} = \frac{d\log(CBF)}{d\log(MAP)}$$

where a value near 0 indicates perfect autoregulation (CBF independent of MAP) and >0.5 indicates loss of autoregulation.

| Symbol | Meaning | Typical Value |
|---|---|---|
| $CBF_{ref}$ | Reference cerebral blood flow (maintained constant) | ~50 mL/(min·100g) |
| $MAP$ | Mean arterial pressure | 60–150 mmHg (autoregulatory range) |
| $P_{critical}$ | Critical pressure below which ischemia begins | ~60 mmHg MAP; ~20 mL/(min·100g) CBF |

**Explanation**: This autoregulation depends on the myogenic response of smooth muscle (Bayliss effect) and metabolic factors (adenosine, K⁺ accumulation). Loss of autoregulation occurs in hypertensive encephalopathy (MAP >180–200 mmHg), head injury, or ischemic stroke. Chronic hypertension shifts the autoregulatory curve rightward (higher baseline MAP), explaining why sudden blood pressure lowering can precipitate stroke in hypertensive patients.

---

## Section 6: Neurovascular Coupling

### 6.1 Neural Activity-Evoked Astrocytic Calcium Dynamics

Neural activity (action potentials, synaptic transmission) triggers astrocytic calcium (Ca²⁺) elevations via glutamate receptor signaling. The time course of astrocytic Ca²⁺ elevation can be modeled as:

$$\frac{d[Ca^{2+}]_{ast}}{dt} = k_{in}(activity) \cdot f_{GPCR} - k_{out} \cdot ([Ca^{2+}]_{ast} - [Ca^{2+}]_{baseline})$$

where $f_{GPCR}$ depends on mGluR5 activation by synaptic glutamate:

$$f_{GPCR} = \frac{[Glu]^n}{K_d^n + [Glu]^n}$$

The Ca²⁺ rise follows a characteristic time course: **rise to peak in 1–3 seconds**, then decay over 5–20 seconds.

| Symbol | Meaning | Typical Value |
|---|---|---|
| $[Ca^{2+}]_{ast}$ | Astrocytic intracellular Ca²⁺ concentration | 0.1–0.3 μM (resting); 0.5–2 μM (activated) |
| $[Ca^{2+}]_{baseline}$ | Baseline astrocytic Ca²⁺ | ~0.1 μM |
| $k_{in}(activity)$ | Ca²⁺ influx rate (activity-dependent) | ~0.5–2 μM/s (during activity) |
| $k_{out}$ | Ca²⁺ extrusion rate constant | ~0.1–0.2 s⁻¹ |
| $[Glu]$ | Synaptic glutamate concentration | 0.1–1 mM (during transmission) |
| $K_d$ | mGluR5 half-saturation (glutamate) | ~5–10 μM |
| $n$ | Hill coefficient | 2–3 |
| Rise time to peak | Time for Ca²⁺ to rise from baseline | ~1–3 s |
| Decay time constant | Time to decline back to baseline | ~5–20 s |

**Explanation**: Astrocytic Ca²⁺ is the trigger for the metabolic cascade. mGluR5 (metabotropic glutamate receptor) activation by synaptically-released glutamate opens IP₃ receptors on the endoplasmic reticulum, releasing intracellular Ca²⁺ stores. This Ca²⁺ rise activates phospholipase C and other enzymes, initiating the arachidonic acid cascade and lactate release.

---

### 6.2 Astrocytic Signaling Cascade: Ca²⁺ → Arachidonic Acid → Vasodilation

Elevated astrocytic Ca²⁺ triggers phospholipase A₂ (PLA₂), which cleaves arachidonic acid from membrane phospholipids. Arachidonic acid is converted to vasodilatory prostanoids (prostaglandin E₂, prostacyclin) or to epoxyeicosatrienoic acids (EETs). These diffuse to vascular smooth muscle and cause relaxation:

$$\frac{d[AA]}{dt} = k_{PLA_2} \cdot [Ca^{2+}]_{ast} - k_{deg} \cdot [AA]$$

The production of prostaglandin E₂ (PGE₂) follows:

$$v_{PGE_2} = k_{COX} \cdot [AA]$$

PGE₂ binds EP2/EP4 receptors on smooth muscle cells, increasing cAMP → smooth muscle relaxation → vasodilation:

$$\frac{d(Vascular\ diameter)}{dt} \propto [PGE_2] \quad \text{(within seconds)}$$

| Symbol | Meaning | Typical Value |
|---|---|---|
| $[AA]$ | Arachidonic acid concentration in astrocyte | ~10–50 μM (elevated during activity) |
| $k_{PLA_2}$ | PLA₂ activity rate constant | ~0.1–0.5 μM/s (at [Ca²⁺] > 0.3 μM) |
| $k_{deg}$ | Arachidonic acid degradation rate | ~0.1–0.2 s⁻¹ |
| $k_{COX}$ | Cyclooxygenase activity rate constant | ~0.01–0.1 s⁻¹ |
| $[PGE_2]$ | Prostaglandin E₂ concentration | ~1–10 nM (produces vasodilation) |
| Vasodilation magnitude | Increase in arteriolar diameter | 10–30% (diameter increase) |
| Vasodilation delay | Time from neural activity to peak vasodilation | ~2–5 s |

**Explanation**: The astrocyte acts as a metabolic sensor: synaptic activity → glutamate release → astrocytic Ca²⁺ rise → arachidonic acid/prostaglandin production → vasodilation. This **neurovascular coupling** delay (~2–5 seconds) matches the typical hemodynamic response function used in fMRI. The coupling ensures blood supply increases where neural activity demands ATP.

---

## Section 7: BOLD Signal Dynamics

### 7.1 Deoxyhemoglobin Dynamics During Neural Activity

Active neurons consume oxygen, producing deoxyhemoglobin (deoxyHb; paramagnetic, reduces local magnetic field homogeneity). However, cerebral blood flow increases **more** than oxygen consumption during activity, causing local blood oxygenation to increase (oxygen supply exceeds demand). This reduces deoxyhemoglobin concentration:

$$[\text{deoxyHb}](t) = [\text{deoxyHb}]_{baseline} - \alpha \cdot \left(1 - e^{-t/\tau}\right)$$

where the reduction is proportional to blood flow increase minus metabolic increase:

$$\Delta[\text{deoxyHb}] = k_1 \cdot \Delta CBF - k_2 \cdot \Delta O_2 \text{ consumption}$$

| Symbol | Meaning | Typical Value |
|---|---|---|
| $[\text{deoxyHb}]_{baseline}$ | Deoxyhemoglobin at rest | ~10–15 μM (voxel-dependent) |
| $\Delta[\text{deoxyHb}]$ | Change in deoxyhemoglobin during activity | −2 to −5 μM (decrease) |
| $\tau$ | Time constant of BOLD response | ~10–30 s (depends on vascular physiology) |
| $\alpha$ | Maximum deoxyhemoglobin reduction | ~0.5–1.5 μM |
| $k_1$ | Coupling between CBF and deoxyhemoglobin | ~0.1–0.2 (unitless) |
| $k_2$ | Coupling between O₂ consumption and deoxyhemoglobin | ~0.05–0.1 |

**Explanation**: The **paradoxical decrease in deoxyhemoglobin despite increased oxygen consumption** is the basis of the BOLD signal. At rest, the brain extracts ~30–40% of oxygen delivered (oxygen extraction fraction, OEF). During activity, CBF increases ~30–50%, but oxygen consumption increases only ~5–10%, so oxygen delivery far exceeds consumption, causing local blood oxygenation to rise (SO₂ increases, deoxyHb decreases).

---

### 7.2 BOLD Contrast and fMRI Signal Intensity

The MRI BOLD signal arises from T2*-weighted imaging, which is sensitive to magnetic field inhomogeneities created by deoxyhemoglobin. The relationship between BOLD signal intensity and deoxyhemoglobin concentration is approximately linear for small changes:

$$S_{BOLD}(t) = S_0 \times \left(1 + k \times \Delta[\text{deoxyHb}](t)\right)$$

where $k$ is the BOLD sensitivity parameter that depends on field strength (3T vs 7T scanner), echo time (TE), and tissue properties.

Alternatively, the percent signal change is:

$$\% \text{BOLD change} = \frac{S_{BOLD}(active) - S_{BOLD}(baseline)}{S_{BOLD}(baseline)} \times 100$$

The time course follows a hemodynamic response function (HRF), typically modeled as a gamma function:

$$HRF(t) = \frac{(t-\delta)^{a-1} e^{-(t-\delta)/b}}{b^a \Gamma(a)}$$

where $a \approx 6$, $b \approx 1$, $\delta \approx 1$ s (delay), yielding peak response at ~6 s post-stimulus.

| Symbol | Meaning | Typical Value |
|---|---|---|
| $S_0$ | Baseline BOLD signal intensity | — |
| $S_{BOLD}$ | BOLD signal during activity | — |
| $k$ | BOLD sensitivity (field-strength dependent) | ~0.1–0.5 (3T); ~0.5–1.5 (7T) |
| $\% \text{BOLD change}$ | Percent signal change from baseline | 0.5–5% (depending on region and task) |
| Peak HRF time | Time to maximum BOLD response | ~5–6 s post-stimulus |
| HRF undershoot | Small negative deflection after peak | Occurs at ~15–20 s |

**Explanation**: The BOLD signal is an indirect measure of neural activity—it reflects synaptic input and local field potentials more than action potential firing. The 5–6 second delay between stimulus and BOLD peak reflects the sluggish hemodynamic response. This latency is crucial for fMRI experimental design (stimulus presentation must be separated by >2–3 seconds for BOLD responses not to overlap). The undershoot (post-stimulus blood flow decrease below baseline) lasts ~15–30 seconds, reflecting prolonged vasoconstriction after activity ceases.

---

## Section 8: Ischemic Cascade

### 8.1 ATP Depletion Kinetics During Cerebral Ischemia

When cerebral blood flow drops below critical levels (typically <20 mL/100g/min in the core), oxygen delivery becomes limiting, aerobic metabolism collapses, and ATP is rapidly depleted. ATP depletion follows approximately first-order kinetics:

$$[ATP](t) = [ATP]_{baseline} \times e^{-k_{depletion} \times t}$$

where $k_{depletion}$ depends on the severity of ischemia:

| Ischemia Severity | CBF (mL/100g/min) | $k_{depletion}$ (min⁻¹) | [ATP] at 5 min | Outcome |
|---|---|---|---|---|
| **Moderate** | 20–35 | ~0.05 | 78% baseline | Potentially reversible |
| **Severe (core)** | <10 | ~0.2–0.3 | 37% baseline | Irreversible necrosis |

At very low CBF (<5 mL/100g/min), ATP drops to 50% in ~3–5 minutes, causing:

$$[ATP](t) = [ATP]_{baseline} - k_{linear} \times t$$

where the rate becomes more linear as ATP synthase becomes ATP-limited.

| Symbol | Meaning | Typical Value |
|---|---|---|
| $[ATP]_{baseline}$ | Normal brain ATP concentration | ~5–10 μmol/g |
| $k_{depletion}$ | ATP depletion rate constant | ~0.05–0.3 min⁻¹ (severity-dependent) |
| $t$ | Time since ischemia onset | 0–60 min |
| Critical [ATP] | ATP level below which Na⁺/K⁺-ATPase fails | ~1–2 μmol/g |
| Time to 50% ATP depletion | — | ~3–15 min (depends on CBF) |

**Explanation**: Severe ischemia (CBF <10 mL/100g/min) causes "core" infarction—irreversible neuronal death within 3–10 minutes. Moderate ischemia (10–25 mL/100g/min) in the "penumbra" preserves some ATP, allowing reversibility if reperfusion occurs within 4.5 hours (tPA thrombolysis window) or 24 hours (mechanical thrombectomy window for large vessel occlusion). During ischemia, anaerobic metabolism produces lactate and H⁺, causing acidosis that accelerates neuronal death.

---

### 8.2 Glutamate Excitotoxicity Cascade

As ATP depletes, Na⁺/K⁺-ATPase fails, causing neuronal depolarization, massive glutamate release from synaptic terminals and glial cells, and uncontrolled NMDA receptor activation. The NMDA-mediated calcium current becomes:

$$I_{NMDA}(t) = I_{max} \times \frac{1}{1 + \left(\frac{[ATP]_i}{K_m^{ATP}}\right)^2}$$

where ATP normally blocks NMDA channels. As ATP drops, blockade is relieved, allowing excessive Ca²⁺ influx:

$$\frac{d[Ca^{2+}]_i}{dt} = k_{NMDA} \times I_{NMDA} - k_{removal}$$

Excessive intracellular Ca²⁺ activates degradative enzymes (calpains, caspases) → cytoskeletal breakdown, mitochondrial dysfunction, free radical production → cell death.

| Symbol | Meaning | Typical Value |
|---|---|---|
| $I_{max}$ | Maximum NMDA current (at zero ATP) | 50–200 pA (whole-cell) |
| $K_m^{ATP}$ | ATP concentration blocking NMDA (50% block) | ~1–3 mM |
| $[Ca^{2+}]_i$ | Intracellular Ca²⁺ concentration | 0.1–0.2 μM (rest); 1–10 μM (pathological) |
| $k_{NMDA}$ | Rate of Ca²⁺ influx via NMDA | ~0.1–1 μM/s (per pA current) |
| $k_{removal}$ | Ca²⁺ extrusion rate constant | ~0.1–0.2 s⁻¹ |
| Lethal [Ca²⁺]_i | Intracellular Ca²⁺ concentration triggering apoptosis | >1–5 μM |

**Explanation**: The excitotoxic cascade is the primary mechanism of ischemic neuronal death. During ischemia, neurons fire repetitively (anoxic depolarization), releasing >1 mM glutamate into the extracellular space. This saturates NMDA receptors, allowing Ca²⁺ influx. High intracellular Ca²⁺ is toxic: (1) activates calpains → neurofilament breakdown; (2) damages mitochondria → cytochrome c release → apoptosis; (3) activates endonucleases → DNA fragmentation. Blocking NMDA receptors (memantine) or reducing intracellular Ca²⁺ (dantrolene, calcium blockers) are neuroprotective in experimental stroke but have limited efficacy clinically, likely because the window is very short (minutes) and multiple cascades are operating in parallel.

---

## Section 9: Metabolic Vulnerability and Protective Mechanisms

### 9.1 Hypoglycemia-Induced Neuronal Dysfunction

Blood glucose below ~3 mmol/L impairs neuronal function (confusion, cognitive slowing), and below ~1 mmol/L causes irreversible damage. The relationship between blood glucose and neuronal function can be modeled as:

$$f(cognition) = \frac{[Glucose]^n}{K_d^n + [Glucose]^n}$$

where $f(cognition)$ is the fraction of normal cognitive function:

| [Glucose] (mmol/L) | Cognitive Status |
|---|---|
| >5 | Normal |
| 3–5 | Mild impairment (confusion) |
| 1–3 | Severe impairment (seizures possible) |
| <1 | Coma, irreversible damage |

| Symbol | Meaning | Typical Value |
|---|---|---|
| $[Glucose]_{normal}$ | Normal blood glucose (fasting) | ~5 mmol/L |
| $[Glucose]_{critical}$ | Glucose threshold for neuronal dysfunction | ~3 mmol/L |
| $K_d$ | Half-saturation glucose (analogous to Km) | ~2–3 mmol/L |
| $n$ | Hill coefficient (steepness of decline) | 2–3 |
| Seizure threshold | Blood glucose below which seizures likely | ~1–1.5 mmol/L |

**Explanation**: The brain depends almost entirely on glucose (no glycogen reserves) and has minimal capacity to use ketones in acute hypoglycemia (ketone production requires hours to days of fasting). During acute hypoglycemia, neurons rapidly lose ATP → Na⁺/K⁺-ATPase failure → depolarization → neuronal hyperexcitability → seizures. Severe hypoglycemia (<1 mmol/L) causes selective neuronal death in hippocampus, cortex, and striatum (regions vulnerable to excitotoxicity). Symptoms include tremor, tachycardia, anxiety (sympathetic), followed by confusion, slurred speech, seizures (neurological). Treatment is rapid glucose (oral if conscious, IV dextrose if unconscious/seizure).

---

### 9.2 Temperature Effects on Brain Metabolism (Q₁₀)

Brain metabolic rate increases exponentially with temperature, following the van 't Hoff equation. The temperature coefficient (Q₁₀) describes the factor by which metabolic rate increases per 10°C rise:

$$\text{Metabolic rate}(T_2) = \text{Metabolic rate}(T_1) \times Q_{10}^{(T_2 - T_1)/10}$$

For the brain, $Q_{10} \approx 2–3$. Therefore:

$$\text{Metabolic rate}(T) = \text{Metabolic rate}(37°C) \times 2.5^{(T - 37)/10}$$

Lowering brain temperature from 37°C to 32°C (therapeutic hypothermia):

$$\text{Metabolic rate}(32°C) = \text{Metabolic rate}(37°C) \times 2.5^{(32-37)/10} = \text{Metabolic rate}(37°C) \times 2.5^{-0.5} \approx 0.63$$

i.e., **37% reduction in metabolic rate**.

| Symbol | Meaning | Typical Value |
|---|---|---|
| $Q_{10}$ | Temperature coefficient for brain metabolism | 2–3 (typically 2.5) |
| $\Delta T$ | Temperature change (°C) | ±1–5°C |
| Metabolism at 37°C | Baseline metabolic rate (normothermia) | 100% (reference) |
| Metabolism at 32°C | Metabolic rate with 5°C cooling | ~63% |
| Metabolism at 35°C | Metabolic rate with 2°C cooling | ~79% |
| Metabolism at 39°C | Metabolic rate with 2°C fever | ~127% |

**Explanation**: Therapeutic hypothermia (32–34°C) reduces neuronal ATP demand, preserving viability during ischemia. It is used after cardiac arrest, neonatal hypoxic-ischemic encephalopathy, and some acute stroke protocols. Each 1°C drop reduces metabolic demand by ~5–10%, extending the ischemic tolerance window. Conversely, fever (>1°C above 37°C) increases metabolic demand and worsens stroke/TBI outcomes. Maintaining normothermia is critical in acute brain injury.

---

## Section 10: Case Studies

### Case Study 10.1: ATP Yield Comparison — Glucose vs Ketones vs Lactate

**Scenario**: Compare the ATP yield from three brain fuels: glucose, β-hydroxybutyrate (ketone), and lactate. Determine how much fuel is needed to support brain ATP demand (~90 mmol ATP/day).

**Calculations**:

1. **Glucose** (complete oxidation):
   $$\text{ATP yield} = 32\,\text{ATP/glucose}$$
   $$\text{Glucose needed} = \frac{90\,\text{mmol ATP/day}}{32\,\text{ATP/glucose}} = 2.8\,\text{mmol glucose/day}$$
   $$= 2.8 \times 180 = 504\,\text{mg glucose/day}$$ (matches ~100 g/day with small error accounting for local NADH use)

2. **β-hydroxybutyrate** (ketone):
   $$\text{ATP yield} = 29\,\text{ATP per ketone}$$
   $$\text{β-HB needed} = \frac{90}{29} = 3.1\,\text{mmol/day}$$
   $$= 3.1 \times 104 = 322\,\text{mg/day}$$
   
   At ketone concentration ~5 mmol/L (ketogenic diet), plasma contains ~5 mmol/L × 3 L = 15 mmol ketones, yielding 15 × 29 = 435 mmol ATP—sufficient for ~4.8 days if not consumed.

3. **Lactate** (from ANLS or circulating):
   $$\text{ATP yield per lactate} = 15\,\text{ATP}$$
   $$\text{Lactate needed} = \frac{90}{15} = 6\,\text{mmol/day}$$
   $$= 6 \times 90 = 540\,\text{mg/day}$$

4. **Comparison**:
   | Fuel | ATP/molecule | Daily requirement | Energy efficiency |
   |---|---|---|---|
   | Glucose | 32 | 2.8 mmol | Baseline (100%) |
   | Ketone | 29 | 3.1 mmol | 91% (similar to glucose) |
   | Lactate | 15 | 6 mmol | 47% (lower per molecule, but bypasses glycolysis) |

**Conclusion**: Ketones are nearly as efficient as glucose but generate less oxidative stress (fewer ROS during oxidation). Lactate is less efficient per molecule but preferred neurologically during intense activity where it reflects immediate fuel availability. During fasting >48 h, the brain shifts from ~100% glucose to ~70% ketones, reducing glucose need from 120 to ~40 g/day.

---

### Case Study 10.2: Cerebral Blood Flow Response to CO₂ (Hyperventilation vs Hypercapnia)

**Scenario**: A patient hyperventilates during a panic attack (PaCO₂ drops to 30 mmHg) vs breathes into a bag during calm recovery (PaCO₂ rises to 50 mmHg). Calculate CBF changes and symptoms.

**Calculations**:

Using Section 5.1 equation:
$$\Delta CBF = \text{CBF}_{baseline} \times k_{CO_2} \times (\Delta P_{aCO_2})$$

**Baseline**: $P_{aCO_2} = 40$ mmHg, $CBF = 50$ mL/(min·100g), $k_{CO_2} = 0.04$ per mmHg

1. **Hyperventilation** ($P_{aCO_2}$ drops to 30 mmHg, $\Delta P_{aCO_2} = −10$ mmHg):
   $$\Delta CBF = 50 \times 0.04 \times (−10) = −20\,\text{mL/(min·100g)}$$
   $$CBF = 50 − 20 = 30\,\text{mL/(min·100g)}$$ (40% reduction)
   
   **Symptoms**: Dizziness, tingling (paresthesias), lightheadedness due to cerebral vasoconstriction and reduced oxygen delivery. Paradoxically, *hyperventilation reduces oxygen delivery despite increased respiratory rate* because vasoconstriction overrides ventilation gains.

2. **Recovery (breathing into bag)**: $P_{aCO_2}$ rises to 50 mmHg, $\Delta P_{aCO_2} = +10$ mmHg:
   $$\Delta CBF = 50 \times 0.04 \times (+10) = +20\,\text{mL/(min·100g)}$$
   $$CBF = 50 + 20 = 70\,\text{mL/(min·100g)}$$ (40% increase)
   
   **Symptoms**: Relief of dizziness, increased alertness. Re-breathing exhaled air (high CO₂) restores normocapnia → vasodilation → improved cerebral perfusion.

3. **CO₂ sensitivity range**:
   - PaCO₂ = 30 mmHg → CBF = 30 mL/(min·100g) ✓
   - PaCO₂ = 40 mmHg → CBF = 50 mL/(min·100g) ✓ (baseline)
   - PaCO₂ = 50 mmHg → CBF = 70 mL/(min·100g) ✓
   - PaCO₂ = 60 mmHg → CBF = 90 mL/(min·100g) (saturation effects begin)

**Clinical implication**: Hyperventilation is a rapid, temporary way to reduce intracranial pressure in acute head injury (by reducing CBF → reduced cerebral blood volume → lower ICP). However, the effect lasts only hours as CSF pH gradually normalizes via renal compensation.

---

### Case Study 10.3: Neurovascular Coupling and BOLD Delay

**Scenario**: A visual stimulus triggers neural activity in V1. Model the time course of astrocytic Ca²⁺ rise, vasodilation, and BOLD signal appearance.

**Calculations**:

Using Section 6 equations:

1. **t = 0 s**: Visual stimulus presented; retinal ganglion cells fire, transmitting signal to V1.

2. **t = 0.1–0.5 s**: Glutamate released at V1 synapses; postsynaptic neurons depolarize; calcium influx begins.

3. **t = 0.5–1 s**: Astrocytic mGluR5 activation; intracellular Ca²⁺ begins to rise:
   $$[Ca^{2+}]_{ast}(t) = 0.1 + (0.5 - 0.1) \times (1 - e^{-t/1}) = 0.1 + 0.4(1 - e^{-t})$$
   
   At t = 1 s: $[Ca^{2+}]_{ast} \approx 0.34$ μM (start of vasodilation pathway).

4. **t = 1–2 s**: Arachidonic acid production and prostaglandin E₂ synthesis. Vasodilation begins (~10% diameter increase).

5. **t = 2–5 s**: Cerebral blood flow increases ~30%; arteriolar dilation evident; blood oxygenation begins to rise.

6. **t = 5–6 s**: **BOLD signal reaches maximum** (~1–2% signal increase in active voxel).
   $$S_{BOLD} = S_0 \times (1 + 0.002) = 1.002 \times S_0$$
   (percent change = 0.2%, typical for visual stimulus in fMRI)

7. **t = 6–15 s**: BOLD signal gradually declines but remains elevated.

8. **t = 15–30 s**: Undershoot occurs (BOLD dips slightly below baseline); reflects prolonged vasodilation of draining veins, causing transient increase in deoxyhemoglobin at macro level.

**Timeline summary**:
| Time (s) | Event | Mechanism |
|---|---|---|
| 0 | Stimulus | Retinal input |
| 0–0.5 | Neuronal firing | Action potentials |
| 0.5–1.5 | Astrocyte Ca²⁺ rise | mGluR5 activation |
| 1–2.5 | Prostaglandin production | PLA₂ activation |
| 2–5 | Arteriolar vasodilation | PGE₂ on smooth muscle |
| 3–5 | CBF increase | Hemodynamic response begins |
| 5–6 | **BOLD peak** | Deoxyhemoglobin reduction |
| 6–15 | BOLD decline | Neuronal activity ends |
| 15–30 | Undershoot | Vascular reverberation |

**fMRI implication**: Event-related fMRI studies must separate stimuli by ≥3 s (preferably ≥5 s) for BOLD responses not to overlap. The 5–6 s peak delay is used to model the hemodynamic response function (gamma function).

---

### Case Study 10.4: Ischemic Stroke — Core vs Penumbra Metabolic Thresholds

**Scenario**: A patient suffers occlusion of the middle cerebral artery (MCA). Using MRI perfusion imaging, three regions are identified:
- **Core**: CBF = 8 mL/(min·100g)
- **Penumbra**: CBF = 18 mL/(min·100g)
- **Oligemia**: CBF = 35 mL/(min·100g) (mild reduction)

Estimate ATP depletion and time to irreversible damage.

**Calculations**:

Using Section 8.1 (ATP depletion kinetics):

**Core** (CBF = 8 mL/100g/min; severe ischemia):
- Baseline [ATP] = 5 μmol/g
- $k_{depletion} \approx 0.25$ min⁻¹ (severe ischemia rate)
- $[ATP](t) = 5 \times e^{-0.25t}$
- At t = 5 min: $[ATP] = 5 \times e^{-1.25} = 1.5$ μmol/g
- At t = 10 min: $[ATP] = 5 \times e^{-2.5} = 0.4$ μmol/g (below critical threshold)
- **Time to irreversible damage: ~5–7 minutes**

**Penumbra** (CBF = 18 mL/100g/min; moderate ischemia):
- $k_{depletion} \approx 0.08$ min⁻¹ (moderate ischemia rate)
- $[ATP](t) = 5 \times e^{-0.08t}$
- At t = 30 min: $[ATP] = 5 \times e^{-2.4} = 0.45$ μmol/g
- At t = 60 min: $[ATP] = 5 \times e^{-4.8} = 0.04$ μmol/g (severe)
- **Time to irreversible damage: ~20–45 minutes** (wider therapeutic window)

**Oligemia** (CBF = 35 mL/100g/min; mild reduction):
- $k_{depletion} \approx 0.02$ min⁻¹ (mild ischemia)
- $[ATP](t) = 5 \times e^{-0.02t}$
- At t = 180 min: $[ATP] = 5 \times e^{-3.6} = 0.17$ μmol/g
- **Time to irreversible damage: >180 minutes** (minimal acute risk; can recover spontaneously if collateral circulation opens)

**Clinical timeline**:
- **0–4.5 hours**: tPA (IV thrombolysis) can restore flow → salvage penumbra
- **4.5–24 hours**: Mechanical thrombectomy for large vessel occlusion (MCA, ICA) can restore flow → salvage remaining penumbra (if collateral flow minimal)
- **>24 hours**: Risk/benefit of reperfusion decreases (infarction typically complete by 24 h)

**Volumetric consequences**:
- Core (irreversible by 10 min): ~20 mL of brain tissue → permanent deficit
- Penumbra (salvageable until ~45 min): ~80 mL → potential recovery if reperfused early
- **Odds of good outcome with thrombolysis**: ~80% if CBF restored within 4.5 h and <1/3 MCA territory infarcted

---

### Case Study 10.5: Hypoglycemia Progression and Neuronal Dysfunction

**Scenario**: A 35-year-old patient with type 1 diabetes forgets to eat lunch. Blood glucose drops progressively. Model symptoms and risk.

**Calculations**:

Using Section 9.1 (glucose-dependent cognition):

| Time | Blood Glucose | Symptoms | Pathophysiology |
|---|---|---|---|
| 1 PM | 5 mmol/L | Normal | Normal ATP supply |
| 2 PM | 3.5 mmol/L | Mild hunger, difficulty concentrating | Neuronal glucose uptake reduced; minor ATP deficit (~10–20%) |
| 2:30 PM | 2.5 mmol/L | Confusion, irritability, tremor (sympathetic), tachycardia | Significant neuronal ATP deficit (~40%); counter-regulatory hormones (epinephrine, glucagon) released |
| 3 PM | 1.5 mmol/L | Severe confusion, incoherence, possible slurred speech | Critical ATP shortage in glucose-dependent neurons; impaired consciousness |
| 3:15 PM | <1.0 mmol/L | **Seizure or loss of consciousness** | Severe ATP depletion; neuronal depolarization; potential irreversible damage if not treated |

**Quantitative model** (Section 9.1):

Using Hill equation for cognitive function:
$$f(cognition) = \frac{[Glucose]^{1.5}}{2.5^{1.5} + [Glucose]^{1.5}}$$

| [Glucose] (mmol/L) | f(cognition) | % Normal function | Clinical status |
|---|---|---|---|
| 5.0 | 0.95 | 95% | Alert |
| 3.5 | 0.60 | 60% | Moderately impaired |
| 2.5 | 0.37 | 37% | Confused |
| 1.5 | 0.13 | 13% | Severely impaired; at seizure risk |
| <1.0 | <0.05 | <5% | Coma |

**Time to seizure**: Depends on glucose drop rate. Rapid drops (>0.5 mmol/L per minute) cause symptoms faster than gradual drops.

**Treatment**: 15 g fast carbohydrates (3–4 glucose tablets, 120 mL juice, 1 tablespoon honey) → blood glucose rises ~2–3 mmol/L within 10–15 minutes.

---

### Case Study 10.6: Therapeutic Hypothermia and Metabolic Reduction

**Scenario**: A 58-year-old man suffers cardiac arrest. Spontaneous circulation is restored after 20 minutes (prolonged ischemia). He is cooled to 32°C for neuroprotection. Calculate metabolic rate reduction and extended ischemic tolerance.

**Calculations**:

Using Section 9.2 (Q₁₀ effect):

$$\text{Metabolic rate}(T) = \text{Metabolic rate}(37°C) \times 2.5^{(T-37)/10}$$

1. **Cooling from 37°C to 32°C** ($\Delta T = −5°C$):
   $$\text{Metabolic rate}(32°C) = 100\% \times 2.5^{-0.5} = 100\% \times 0.632 = 63.2\%$$
   **Metabolic reduction: 36.8%**

2. **Extended ischemic tolerance**:
   - At 37°C (normothermia), neuronal damage becomes irreversible within ~5–10 minutes of complete ischemia
   - At 32°C, ischemic tolerance extends by a factor proportional to metabolic reduction
   - Rough estimate: ~5 min (37°C) × (100/63.2) = ~7.9 minutes at 32°C
   - More conservative estimate: 10–15 minutes at 32°C

3. **ATP preservation**:
   - ATP consumption at 37°C: ~6 mmol ATP/min (whole brain)
   - ATP consumption at 32°C: ~6 × 0.632 = ~3.8 mmol ATP/min
   - Baseline [ATP] × 10 mmol/g × 1,400 g (brain) = ~14,000 mmol ATP total
   - Time to ATP depletion:
     - At 37°C: 14,000 / 6 ≈ 2,333 min (40 hours; unrealistic because anaerobic metabolites accumulate)
     - At 32°C with anaerobic metabolism: ~15–20 minutes before severe lactate acidosis impairs function

4. **Cooling protocol** (standard post-cardiac arrest):
   - Target temperature: 32–34°C
   - Duration: 12–24 hours
   - Rewarming: Slow (0.25–0.5°C/hour) to avoid reperfusion injury
   
   **Outcome improvement**: Therapeutic hypothermia → ~50% reduction in mortality/severe disability in comatose post-cardiac arrest survivors (NNT ≈ 6).

5. **Mechanism**:
   - ↓ Metabolic demand → ↓ ATP consumption
   - ↓ Excitotoxicity (glutamate release reduced, NMDA receptor activation reduced)
   - ↓ Inflammation (microglia activation reduced, cytokine production reduced)
   - ↓ Apoptosis (caspase-3 activity reduced)
   - ↓ Cerebral edema (reduced BBB permeability)

---

## References

1. Sokoloff, L. (1991). Relationships between functional activity and energy metabolism in the nervous system. *Journal of Cerebral Blood Flow & Metabolism*, 1(S1), S7–S17.

2. Mergenthaler, P., Lindauer, U., Dienel, G. A., & Meisel, A. (2013). Sugar for the brain: The role of glucose in physiological and pathological brain function. *Trends in Neurosciences*, 36(10), 587–597.

3. Pellerin, L., & Magistretti, P. J. (1994). Glutamate uptake into astrocytes stimulates aerobic glycolysis by a calcium-dependent process. *PNAS*, 91(22), 10625–10629.

4. Magistretti, P. J., & Allaman, I. (2015). A cellular perspective on brain energy metabolism and functional imaging. *Neuron*, 86(4), 883–901.

5. Kang, T. M., Hilal, S., Chai, Y. L., et al. (2018). Cerebral microinfarcts: A review of the literature. *Journal of Stroke*, 19(1), 1–11.

6. Cauli, B., & Hamel, E. (2010). Revisiting the role of neurons in neurovascular coupling. *Frontiers in Neuroenergetics*, 2, 9.

7. Attwell, D., Buchan, A. M., Cherksey, B., Jiang, Q., Kauppinen, R. A., Khaled, A. R., & Ogboru, I. C. (2010). Glial and neuronal control of brain blood flow. *Nature*, 468(7321), 232–243.

8. Logothetis, N. K. (2008). What we can do and what we cannot do with fMRI. *Nature*, 453(7198), 869–878.

9. Hillman, E. M. (2014). Coupling mechanism and significance of the BOLD signal: A status report. *Current Opinion in Neurobiology*, 25, 94–102.

10. Harris, J. J., Jolivet, R., & Attwell, D. (2012). Synaptic energy use and supply. *Neuron*, 75(5), 762–777.

11. Zlokovic, B. V., Begley, D. J., & Chain-Eliason, D. G. (1991). Blood-brain barrier permeability to lactate. *Brain Research*, 706(1), 1–6.

12. Simpson, I. A., Carruthers, A., & Vannucci, S. J. (2007). Supply and demand in cerebral glucose transport: Rheological, metabolic, and neuronal considerations. *Journal of Cerebral Blood Flow & Metabolism*, 27(4), 701–714.

13. Stafstrom, C. E., & Rho, J. M. (2012). The ketogenic diet as a treatment paradigm for diverse neurological disorders. *Frontiers in Pharmacology*, 3, 59.

14. Yudkoff, M., Daikhin, Y., Nissim, I., Horyn, O., Lazarow, A., Luhovyy, B., ... & Nissim, I. (2007). Brain amino acid metabolism and ketosis. *Journal of Neuroscience Research*, 66(2), 272–281.

15. Paulson, O. B., Strandgaard, S., & Edvinsson, L. (1990). Cerebral autoregulation. *Cerebrovascular and Brain Metabolism Reviews*, 1(1), 3–36.

16. Lassen, N. A. (1959). Cerebral blood flow and oxygen consumption in man. *Physiological Reviews*, 39(2), 183–238.

17. Iadecola, C. (2017). The neurovascular unit coming of age: A journey through neurovascular coupling in health and disease. *Neuron*, 96(1), 17–42.

18. Buxton, R. B., Uludag, K., Dubowitz, D. J., & Liu, T. T. (2004). Modeling the hemodynamic response to brain activation. *NeuroImage*, 23, S220–S233.

19. Ogawa, S., Lee, T. M., Kay, A. R., & Tank, D. W. (1990). Brain magnetic resonance imaging with contrast dependent on blood oxygenation. *PNAS*, 87(24), 9868–9872.

20. Liu, S., Pedersen, M., Qin, X., Liebeskind, D. S., & Liebeskind, P. S. (2012). Evidence for penumbral tissue loss in acute ischemic stroke. *Stroke*, 43(5), 1408–1413.

21. Fisher, M., Feuerstein, G., Howells, D. W., Hurn, P. D., Kent, T. A., Savitz, S. I., & Lo, E. H. (2009). Update of the stroke therapy academic industry roundtable preclinical recommendations. *Stroke*, 40(6), 2244–2250.

22. Lipton, P. (1999). Ischemic cell death in brain neurons. *Physiological Reviews*, 79(4), 1431–1568.

23. Zhao, H., Ren, X., & Mazurkiewicz, M. (2016). Protective role of hyperbaric oxygen in stroke. In *Stroke Recovery and Rehabilitation* (pp. 373–399). Woodhead Publishing.

24. Polderman, K. H. (2008). Mechanisms of action, physiological effects, and complications of hypothermia. *Critical Care Medicine*, 37(7), S186–S202.

25. Jacobs, S. E., Hunt, R., Tarnow-Mordi, W. O., Inder, T. E., & Davis, P. G. (2013). Cooling for newborns with hypoxic-ischaemic encephalopathy. *Cochrane Database of Systematic Reviews*, 1, CD003311.

---

**End of Chapter 13 — Brain Metabolism and Blood Supply**
