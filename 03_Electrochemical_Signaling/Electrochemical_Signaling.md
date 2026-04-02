# Chapter 3: Electrochemical Signaling

## 3.1 Resting Membrane Potential

All neurons maintain a resting membrane potential of approximately **-65 to -70 mV** (intracellular negative relative to extracellular). This potential energy gradient is the foundation of all electrical signaling in the nervous system.

### Ionic Basis

Four major ions establish the resting potential:

| Ion | Intracellular (mM) | Extracellular (mM) | Equilibrium Potential (Eion) |
|---|---|---|---|
| K⁺ | ~140 | ~5 | -90 mV |
| Na⁺ | ~15 | ~145 | +60 mV |
| Cl⁻ | ~10 | ~110 | -70 mV |
| Ca²⁺ | ~0.0001 | ~2 | +130 mV |

These concentration gradients are maintained by the **Na⁺/K⁺-ATPase** (sodium-potassium pump), which hydrolyzes one ATP molecule to export 3 Na⁺ ions and import 2 K⁺ ions per cycle. This pump consumes ~40–70% of the brain's total ATP budget. The electrogenic nature of the pump (3 out, 2 in) contributes approximately -3 to -5 mV to the resting potential directly.

### Goldman-Hodgkin-Katz Equation

The resting membrane potential is determined by the Goldman equation, which accounts for relative permeabilities:

**Vm = (RT/F) × ln[(PK[K⁺]out + PNa[Na⁺]out + PCl[Cl⁻]in) / (PK[K⁺]in + PNa[Na⁺]in + PCl[Cl⁻]out)]**

At rest, the membrane is ~40× more permeable to K⁺ than Na⁺ (due to leak K⁺ channels, primarily KCNK two-pore domain channels), which is why the resting potential (-70 mV) sits close to EK (-90 mV) rather than ENa (+60 mV).

---

## 3.2 The Action Potential

The action potential is an all-or-none, regenerative electrical event that propagates along the axon without decrement.

### Phases

1. **Resting state (-70 mV)**: Voltage-gated Na⁺ channels (Nav) are in the closed/resting state. Voltage-gated K⁺ channels (Kv) are closed.

2. **Threshold (~-55 mV)**: When depolarization reaches threshold, a critical number of Nav channels open, creating a positive feedback loop — Na⁺ influx causes further depolarization, which opens more Nav channels. This is the point of no return.

3. **Depolarization/Rising phase (-55 → +30 mV)**: Massive Na⁺ influx through open Nav1.1/1.2/1.6 channels. Na⁺ conductance increases ~500-fold in <0.5 ms. The membrane approaches ENa (+60 mV) but doesn't reach it because K⁺ channels begin opening.

4. **Repolarization (+30 → -70 mV)**: Two simultaneous events:
   - Nav channels **inactivate** (the inactivation gate — an intracellular loop between domains III and IV — swings into the channel pore; the "ball-and-chain" mechanism)
   - Voltage-gated K⁺ channels (Kv, primarily Kv1–Kv4 families) open with a slight delay (delayed rectifier currents), driving K⁺ efflux

5. **Hyperpolarization/Undershoot (~-80 mV)**: K⁺ channels remain open briefly after Na⁺ channels have inactivated, driving the membrane past the resting potential toward EK.

6. **Return to rest (-70 mV)**: K⁺ channels close; Na⁺/K⁺-ATPase restores ionic gradients (though a single action potential moves very few ions — the pump works to maintain long-term balance).

### Refractory Periods

- **Absolute refractory period** (~1–2 ms): Nav channels are inactivated and cannot be reopened regardless of stimulus strength. Ensures unidirectional propagation of the action potential.
- **Relative refractory period** (~3–4 ms): Some Nav channels have recovered, but elevated K⁺ conductance means a stronger-than-normal stimulus is needed. Limits maximum firing rate (~500–1000 Hz theoretical; most neurons fire at 1–100 Hz in practice).

### Action Potential Propagation

**In unmyelinated axons**: Continuous conduction — local current flow from depolarized membrane activates Nav channels in adjacent membrane, propagating the action potential at 0.5–2 m/s. Velocity depends on axon diameter (∝ √diameter) due to lower internal resistance in larger axons.

**In myelinated axons**: **Saltatory conduction** — action potentials "jump" between nodes of Ranvier, where Nav1.6 channels are clustered at ~1,200/µm². The myelin sheath between nodes acts as an insulator with high membrane resistance and low capacitance, allowing rapid passive current spread between nodes. This increases velocity to 3–120 m/s while reducing metabolic cost (Na⁺/K⁺-ATPase activity is concentrated at nodes).

**Conduction velocity classification:**
| Fiber Type | Diameter | Myelination | Velocity | Example |
|---|---|---|---|---|
| Aα | 13–20 µm | Heavy | 80–120 m/s | Motor neurons, proprioception |
| Aβ | 6–12 µm | Moderate | 35–75 m/s | Touch, pressure |
| Aδ | 1–5 µm | Light | 5–30 m/s | Sharp pain, temperature |
| C | 0.2–1.5 µm | None | 0.5–2 m/s | Dull pain, itch, autonomic |

---

## 3.3 Synaptic Transmission

Synapses are specialized junctions where signals pass between neurons (or between neurons and effector cells). Approximately 100–150 trillion synapses exist in the human brain.

### Chemical Synapses

The vast majority (~99%) of synapses in the human brain are chemical, involving neurotransmitter release. The sequence of events:

**1. Action potential arrives at presynaptic terminal**
The depolarization opens **voltage-gated Ca²⁺ channels** (primarily Cav2.1 P/Q-type and Cav2.2 N-type) clustered in the **active zone** — a specialized presynaptic membrane region positioned directly opposite postsynaptic receptor clusters.

**2. Calcium influx triggers vesicle fusion**
Ca²⁺ entry (~10–100 µM locally, lasting <1 ms) activates **synaptotagmin-1** (the Ca²⁺ sensor on synaptic vesicles). The SNARE complex — composed of **synaptobrevin/VAMP2** (vesicle), **syntaxin-1** and **SNAP-25** (presynaptic membrane) — mediates membrane fusion. The energy for fusion comes from SNARE complex zippering (a largely irreversible process; the complex is subsequently disassembled by **NSF** and **α-SNAP** ATPases for vesicle recycling).

**Vesicle pools:**
- **Readily releasable pool (RRP)**: ~5–10 vesicles docked at the active zone; depleted in ~10 ms of intense activity
- **Recycling pool**: ~5–20% of total; replenishes the RRP
- **Reserve pool**: ~80–90% of total (~200+ vesicles); mobilized during sustained activity (requires actin-dependent transport)

**3. Neurotransmitter release into the synaptic cleft**
Each vesicle contains ~5,000 transmitter molecules (a "quantum"). At most CNS synapses, a single action potential releases 0–2 vesicles probabilistically (release probability p = 0.1–0.9 depending on synapse type). The synaptic cleft is ~20–40 nm wide.

**4. Postsynaptic receptor binding**
Neurotransmitter binds to:
- **Ionotropic receptors (ligand-gated ion channels)**: Fast response (1–5 ms). Examples: AMPA, NMDA, kainate (glutamate); GABA-A; nicotinic ACh; 5-HT3; glycine receptors.
- **Metabotropic receptors (G-protein-coupled receptors, GPCRs)**: Slower (100 ms–seconds) but longer-lasting effects via second messenger cascades (cAMP, IP3/DAG, Ca²⁺). Examples: mGluRs, GABA-B, muscarinic ACh, most serotonin receptors, dopamine receptors (D1–D5), adrenergic receptors.

**5. Postsynaptic potentials**
- **Excitatory postsynaptic potential (EPSP)**: Depolarization (e.g., Na⁺/K⁺ influx through AMPA receptors). Typical amplitude: 0.5–1 mV at the soma. Single EPSPs are subthreshold; **spatial summation** (multiple synapses) and **temporal summation** (rapid successive inputs) are needed to reach threshold.
- **Inhibitory postsynaptic potential (IPSP)**: Hyperpolarization or shunting inhibition (e.g., Cl⁻ influx through GABA-A receptors, or K⁺ efflux through GABA-B-activated GIRK channels).

**6. Signal termination**
- **Reuptake**: Presynaptic or astrocytic transporters remove transmitter from the cleft (e.g., SERT for serotonin, DAT for dopamine, NET for norepinephrine, EAAT1/2 for glutamate)
- **Enzymatic degradation**: Acetylcholinesterase (AChE) cleaves acetylcholine in the cleft; monoamine oxidase (MAO) and catechol-O-methyltransferase (COMT) degrade monoamines
- **Diffusion**: Transmitter diffuses away from the cleft

### Electrical Synapses (Gap Junctions)

Formed by **connexon** hemichannels (each composed of 6 connexin protein subunits) on adjacent cells, which dock to form a **gap junction** channel. These channels allow direct passage of ions and small molecules (<1 kDa) between cells, enabling:

- **Extremely fast transmission** (<0.1 ms; no synaptic delay)
- **Bidirectional current flow** (though some gap junctions show rectification)
- **Electrical coupling and synchronization**: Critical for synchronized oscillations in cortical interneuron networks (e.g., gamma oscillations via PV+ interneuron gap junctions), cardiac muscle, and smooth muscle
- **Metabolic coupling**: Transfer of second messengers (IP3, cAMP) and metabolites (glucose, lactate)

Gap junctions are also prevalent in astrocytic networks, forming a functional syncytium for spatial K⁺ buffering and metabolite distribution.

---

## 3.4 Synaptic Integration

Neurons integrate thousands of synaptic inputs through multiple mechanisms:

### Passive Properties
- **Length constant (λ)**: Distance over which a passive signal decays to 37% of its original value. Larger-diameter dendrites and higher membrane resistance increase λ, allowing distal synapses to influence the soma more effectively.
- **Time constant (τ = Rm × Cm)**: Determines how quickly the membrane potential changes. Typical values: 10–50 ms.
- **Cable properties**: Dendrites act as leaky cables; distal synapses produce smaller somatic potentials than proximal ones (unless actively amplified).

### Active Dendritic Properties
- **Dendritic Na⁺ spikes**: Backpropagating action potentials (bAPs) from soma into dendrites serve as a coincidence detector — when a bAP arrives at a spine simultaneously receiving synaptic input, it strongly promotes LTP.
- **Dendritic Ca²⁺ spikes**: Generated in apical dendrite tuft of layer V pyramidal neurons; can trigger burst firing; gated by top-down feedback from higher cortical areas.
- **NMDA spikes**: Voltage- and ligand-gated; provide supralinear summation in thin dendrites.

### Integration Modes
- **Linear summation**: Inputs at different dendritic locations sum approximately linearly at the soma
- **Sublinear summation**: Activation of nearby synapses reduces driving force (due to local depolarization), producing less than expected combined effect
- **Supralinear summation**: Clustered inputs on a dendritic branch can trigger local dendritic spikes, producing disproportionately large somatic depolarization — "dendritic computation"

---

## 3.5 Neuromodulation

Beyond fast point-to-point synaptic transmission, the brain employs **volume transmission** — diffuse release of neuromodulators that affect large populations of neurons via extrasynaptic receptors. Major neuromodulatory systems (see Chapter 4 for detailed neurotransmitter profiles):

- **Dopamine** (VTA, substantia nigra): Reward prediction, motivation, motor control
- **Serotonin** (raphe nuclei): Mood, impulse control, satiety
- **Norepinephrine** (locus coeruleus): Arousal, attention, stress response
- **Acetylcholine** (basal forebrain, pedunculopontine nucleus): Attention, learning, REM sleep
- **Histamine** (tuberomammillary nucleus): Wakefulness

These systems modulate neural circuit function by altering:
- Intrinsic excitability (shifting resting potential, modifying ion channel kinetics)
- Synaptic transmission strength (presynaptic release probability, postsynaptic receptor sensitivity)
- Synaptic plasticity thresholds (gating LTP/LTD induction)
- Network oscillation patterns (shifting between brain states)

---

## 3.6 Neural Oscillations

Rhythmic electrical activity reflects coordinated population dynamics and is critical for information processing:

| Band | Frequency | Associated Function |
|---|---|---|
| Delta (δ) | 0.5–4 Hz | Deep (N3) sleep, unconsciousness |
| Theta (θ) | 4–8 Hz | Hippocampal memory encoding, navigation, REM sleep |
| Alpha (α) | 8–13 Hz | Relaxed wakefulness, sensory gating (Berger rhythm) |
| Beta (β) | 13–30 Hz | Active thinking, motor planning, status quo maintenance |
| Gamma (γ) | 30–100 Hz | Conscious perception, feature binding, working memory, attention |
| High gamma | 100–200 Hz | Local cortical computation |
| Sharp-wave ripples | 100–250 Hz | Hippocampal memory replay/consolidation during sleep and quiet wakefulness |

**Mechanism of oscillation generation**: Oscillations emerge from interactions between excitatory and inhibitory populations. Gamma oscillations, for example, depend critically on PV+ fast-spiking interneurons providing rhythmic perisomatic inhibition to pyramidal cells (the "PING" — Pyramidal-Interneuron Network Gamma — model). Thalamocortical oscillations (sleep spindles, alpha rhythm) arise from intrinsic properties of thalamic relay neurons (T-type Ca²⁺ channels) interacting with the reticular nucleus.

**Cross-frequency coupling**: Theta-gamma coupling (gamma amplitude modulated by theta phase) in the hippocampus may represent a mechanism for organizing information: each theta cycle "packages" distinct gamma-frequency cell assemblies representing different items in working memory.

---

*Next: [Chapter 4 — Neurotransmitter Systems](../04_Neurotransmitter_Systems/Neurotransmitter_Systems.md)*
