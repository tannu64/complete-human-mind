# Chapter 5: Neural Circuits and Networks

## 5.1 Principles of Neural Circuit Organization

The brain's computational power arises not from individual neurons but from the architecture of interconnected circuits. Key organizational principles include:

- **Convergence**: Many inputs synapse onto a single neuron (a cortical pyramidal cell receives ~5,000–30,000 synaptic inputs)
- **Divergence**: A single neuron projects to many targets (a single CA3 pyramidal cell has ~30,000 Schaffer collateral synapses onto CA1 neurons)
- **Recurrence**: Feedback loops within circuits enable sustained activity (working memory), oscillations, and attractor dynamics
- **Lateral inhibition**: Enhances contrast and sharpens representations (e.g., surround inhibition in sensory cortex)
- **Feedforward inhibition**: Interneurons activated by incoming excitatory input provide rapid, precisely timed inhibition that narrows the temporal window for integration
- **Top-down modulation**: Higher-order areas regulate processing in lower areas via feedback projections

### Cortical Microcircuit: The Canonical Column

The neocortex is organized into functional columns (~300–600 µm diameter) with a stereotyped internal circuit:

1. **Thalamocortical input** arrives primarily in **Layer IV** (onto excitatory stellate cells and inhibitory interneurons)
2. Layer IV excites **Layer II/III** pyramidal neurons (corticocortical output — association and commissural connections)
3. Layer II/III excites **Layer V** pyramidal neurons (subcortical output — corticospinal, corticostriatal, corticopontine)
4. Layer V excites **Layer VI** pyramidal neurons (corticothalamic feedback)
5. At each stage, local GABAergic interneurons (PV+, SST+, VIP+) provide feedforward inhibition, feedback inhibition, and disinhibition

**Inhibitory interneuron subtypes form a disinhibitory motif**: VIP+ interneurons (primarily targeting SST+ interneurons) → disinhibition of pyramidal cell dendrites. This VIP → SST → pyramidal cell circuit is a major mechanism for top-down attentional gain modulation.

---

## 5.2 Large-Scale Brain Networks

Resting-state and task-based functional neuroimaging have revealed a set of reproducible large-scale networks defined by correlated activity patterns.

### Default Mode Network (DMN)

**Core nodes**: Medial prefrontal cortex (mPFC), posterior cingulate cortex (PCC)/precuneus, angular gyrus, lateral temporal cortex, hippocampal formation.

**Function**: Active during internally directed cognition — self-referential thought, autobiographical memory retrieval, future simulation/prospection, mind-wandering, theory of mind (mentalizing about others' mental states). The DMN is suppressed (deactivated) during externally focused attention-demanding tasks.

**Subsystems**:
- **Medial temporal subsystem** (hippocampus, parahippocampal cortex, retrosplenial cortex): Memory-based simulation, scene construction
- **Dorsomedial PFC subsystem** (dmPFC, temporoparietal junction, lateral temporal cortex): Social cognition, mentalizing

**Clinical relevance**: DMN hyperconnectivity is associated with rumination in depression; failure to suppress DMN during task performance is linked to attention deficits in ADHD; DMN disruption occurs early in Alzheimer's disease (amyloid deposits preferentially accumulate in DMN nodes).

### Salience Network (SN)

**Core nodes**: Anterior insula (AI), dorsal anterior cingulate cortex (dACC), with connections to amygdala, ventral striatum, hypothalamus, and brainstem autonomic nuclei.

**Function**: Detects behaviorally relevant (salient) stimuli — whether threatening, rewarding, or novel — and initiates appropriate switching between DMN and CEN. The anterior insula is proposed as a "switch operator" that toggles between internally directed (DMN) and externally directed (CEN) processing based on salience signals.

**The anterior insula** integrates interoceptive signals (visceral, autonomic) with emotional and cognitive processing, generating a moment-to-moment representation of "how I feel now." This is fundamental to subjective awareness, emotional experience, and empathy (Craig's interoceptive model of consciousness).

### Central Executive Network (CEN) / Frontoparietal Network

**Core nodes**: Dorsolateral prefrontal cortex (dlPFC), posterior parietal cortex (PPC, especially intraparietal sulcus), frontal eye fields.

**Function**: Goal-directed behavior, working memory maintenance and manipulation, attentional control, cognitive flexibility, problem-solving. The CEN is anti-correlated with the DMN — when one is active, the other tends to be suppressed (though this dynamic is more nuanced than simple opposition).

### Attention Networks

**Dorsal attention network (DAN)**: Frontal eye fields + superior parietal lobule/intraparietal sulcus. Top-down, voluntary directed attention — selects stimuli based on goals and expectations. Generates attentional "templates" that bias processing in sensory cortex.

**Ventral attention network (VAN)**: Right temporoparietal junction (TPJ) + right ventral frontal cortex (inferior/middle frontal gyrus). Bottom-up, stimulus-driven reorienting — interrupts focused attention when an unexpected but behaviorally relevant stimulus appears (a "circuit breaker"). Right-lateralized, explaining why spatial neglect most commonly follows right hemisphere lesions.

---

## 5.3 Sensory Processing Circuits

### Visual Pathway (Summary; see Chapter 6 for detail)

Retinal ganglion cells → optic nerve → optic chiasm (nasal fibers cross) → optic tract → **lateral geniculate nucleus (LGN)** of thalamus → optic radiations → **primary visual cortex (V1)**.

The LGN has 6 layers:
- Layers 1–2: **Magnocellular** (M pathway) — large receptive fields, motion, luminance contrast, rapid temporal processing
- Layers 3–6: **Parvocellular** (P pathway) — small receptive fields, color, fine detail, sustained responses
- **Koniocellular** layers (interlaminar): Color (blue-yellow), contribute to both dorsal and ventral streams

From V1, information splits into:
- **Dorsal stream** ("where/how"): V1 → V2 → V3 → V5/MT (motion) → posterior parietal cortex. Guides action, spatial processing.
- **Ventral stream** ("what"): V1 → V2 → V4 (color, form) → inferior temporal cortex. Object recognition, face processing.

### Motor Circuit: Cortico-Basal Ganglia-Thalamo-Cortical Loops

Five parallel loops process different types of information through the same circuit architecture:

1. **Motor loop**: Supplementary motor area/premotor → putamen → GPi/SNr → VL thalamus → SMA/premotor. Action execution.
2. **Oculomotor loop**: Frontal/supplementary eye fields → caudate body → GPi/SNr → VA/MD thalamus → FEF. Eye movements.
3. **Dorsolateral prefrontal loop**: dlPFC → caudate head → GPi/SNr → VA/MD thalamus → dlPFC. Working memory, planning.
4. **Lateral orbitofrontal loop**: OFC → ventromedial caudate → GPi/SNr → MD thalamus → OFC. Behavioral flexibility, inhibition.
5. **Anterior cingulate/limbic loop**: ACC → ventral striatum (NAc) → ventral pallidum → MD thalamus → ACC. Motivation, reward.

### Cerebellar Circuits

The cerebellum operates through a comparator/error-correction mechanism:

1. **Mossy fibers** (from pontine nuclei, spinal cord) → **granule cells** → parallel fibers → Purkinje cell dendrites (excitatory)
2. **Climbing fibers** (from inferior olive) → Purkinje cells (powerful 1:1 excitatory; "teaching signal" — signals motor errors)
3. **Purkinje cells** (GABAergic) → deep cerebellar nuclei (inhibitory output)
4. **Deep cerebellar nuclei** → thalamus → cortex; also → red nucleus, brainstem

Learning occurs through **climbing fiber-driven LTD** at the parallel fiber-Purkinje cell synapse: when a climbing fiber signals an error simultaneously with parallel fiber input, the parallel fiber synapse is weakened, adjusting the motor output. This is the Marr-Albus-Ito model of cerebellar learning.

---

## 5.4 Reward Circuitry

The mesolimbic dopamine system forms the core of the brain's reward circuit:

### Key Components

**Ventral tegmental area (VTA)**: ~60% dopaminergic neurons, ~35% GABAergic, ~5% glutamatergic. DA neurons project to nucleus accumbens, PFC, amygdala, hippocampus.

**Nucleus accumbens (NAc)**: Ventral striatum; divided into:
- **Shell**: Receives DA from medial VTA; encodes hedonic value ("liking"), novelty; projects to lateral hypothalamus and ventral pallidum. The hedonic hotspot within the NAc shell (and ventral pallidum) mediates opioid/endocannabinoid-driven pleasure enhancement.
- **Core**: Receives DA from lateral VTA; encodes motivational salience ("wanting"), action initiation; projects to dorsal pallidum and SNr.

**Prefrontal cortex**: Value representation, decision-making, top-down regulation of impulsive behavior.

**Amygdala**: Associates stimuli with reward/threat value; sends glutamatergic projections to NAc.

**Lateral habenula**: Encodes "anti-reward" signals — activated by punishment and reward omission; inhibits VTA DA neurons (via GABAergic interneurons in the rostromedial tegmental nucleus, RMTg). Hyperactivity in the lateral habenula is implicated in anhedonia and depression.

### Dopamine and Reward Learning

**Reward prediction error (RPE)** signaling by VTA DA neurons:
- Unexpected reward → phasic DA burst (positive RPE) → strengthens preceding actions (via D1 receptor → cAMP/PKA → DARPP-32 → LTP at corticostriatal synapses)
- Expected reward → no DA change (zero RPE)
- Expected reward omitted → phasic DA dip (negative RPE) → weakens preceding actions (via D2 receptor → LTD at corticostriatal synapses)

This signal drives **reinforcement learning**, updating stimulus-action-outcome associations. Over learning, DA responses shift from the reward itself to the earliest predictive cue — explaining conditioned responses.

### Addiction Neurobiology

All drugs of abuse increase DA in the NAc, but through different mechanisms:
- **Stimulants** (cocaine, amphetamine): Block or reverse DAT
- **Opioids**: Disinhibit VTA DA neurons (inhibit GABAergic interneurons via μ-opioid receptors)
- **Nicotine**: Directly activates α4β2 nAChRs on VTA DA neurons
- **Alcohol**: Multiple mechanisms — enhances GABA-A, inhibits NMDA, releases opioids in VTA
- **Cannabis**: CB1 activation → disinhibition of VTA DA neurons

Chronic drug use induces:
1. **Tolerance**: Receptor downregulation/desensitization
2. **Sensitization**: Enhanced DA response to drug-associated cues (incentive salience; "wanting" without "liking")
3. **Allostatic shift**: Recruitment of anti-reward systems (CRH, dynorphin/KOR, norepinephrine) → negative emotional state during withdrawal → compulsive drug seeking to relieve dysphoria
4. **Prefrontal hypofrontality**: Reduced PFC gray matter and function → impaired inhibitory control

---

## 5.5 Fear and Threat Circuits

The defensive response circuit centers on the amygdala:

**Threat detection pathway (fast/low road)**: Sensory thalamus → basolateral amygdala (BLA) → central amygdala (CeA) → outputs. This bypass of cortical processing enables rapid (~12 ms in rodents) defensive responses.

**Cortical evaluation pathway (slow/high road)**: Sensory cortex → BLA → CeA → outputs. Provides detailed threat assessment.

**CeA outputs drive:**
- Lateral hypothalamus → sympathetic activation (tachycardia, blood pressure increase)
- Paraventricular nucleus → HPA axis activation → cortisol release
- Periaqueductal gray (PAG) → freezing (ventrolateral PAG) or fight/flight (dorsolateral PAG)
- Locus coeruleus → norepinephrine release → arousal, vigilance
- Parabrachial nucleus → respiratory changes
- Facial motor nucleus → fear expression

**Fear conditioning**: Pairing a neutral conditioned stimulus (CS, e.g., tone) with an aversive unconditioned stimulus (US, e.g., shock) strengthens CS-responsive synapses in the BLA via **NMDA-dependent LTP**. After conditioning, the CS alone activates BLA → CeA → defensive responses.

**Fear extinction**: Not erasure but new learning. Repeated CS presentation without US → ventromedial PFC (infralimbic cortex in rodents) activates **intercalated cell masses** (GABAergic neurons between BLA and CeA) → inhibition of CeA output. Extinction is context-dependent and can relapse (renewal, reinstatement, spontaneous recovery).

---

## 5.6 Hippocampal-Cortical Memory Circuits

Memory encoding and consolidation involve interactions between hippocampus and neocortex (see Chapter 7 for detailed memory mechanisms):

**Encoding**: Novel experiences activate hippocampal circuits; the trisynaptic pathway (EC → DG → CA3 → CA1) creates sparse, orthogonal representations (pattern separation in DG) while enabling retrieval from partial cues (pattern completion in CA3).

**Consolidation**: During sleep (particularly NREM slow-wave sleep), hippocampal **sharp-wave ripples** (100–250 Hz) replay recent experiences in compressed time. Coordinated with cortical **slow oscillations** (0.5–1 Hz) and thalamocortical **sleep spindles** (12–16 Hz), this hippocampal-cortical dialogue gradually transfers memory traces to neocortical long-term storage (systems consolidation).

**Retrieval**: Recall involves hippocampal pattern completion (for episodic/recent memories) or direct cortical retrieval (for consolidated/semantic memories). The anterior PFC mediates retrieval monitoring and source memory.

---

*Next: [Chapter 6 — Sensory Processing](../06_Sensory_Processing/Sensory_Processing.md)*
