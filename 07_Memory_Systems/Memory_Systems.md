# Chapter 7: Memory Systems

## 7.1 Taxonomy of Memory

Memory is not a unitary system but a collection of distinct cognitive and neural processes:

### By Duration

**Sensory Memory** (~200 ms–3 s):
- **Iconic memory** (visual): Brief persistence of visual information after stimulus offset; high capacity but rapid decay (~250 ms); held in early visual cortex; demonstrated by Sperling's partial report paradigm (1960)
- **Echoic memory** (auditory): Auditory persistence lasting 2–4 seconds; held in primary and secondary auditory cortex; allows retrospective analysis of sounds

**Short-Term Memory (STM)** (~15–30 s without rehearsal):
- Limited capacity: Miller's "7±2" items (1956); more recent estimates suggest ~4 chunks (Cowan, 2001)
- Maintained by sustained neural firing in PFC and posterior cortical areas
- Decays through temporal degradation and interference

**Working Memory** (active manipulation of STM):
Baddeley's multi-component model (updated):
- **Phonological loop**: Verbal/acoustic information; phonological store (2 s trace duration) + articulatory rehearsal process (subvocalization). Neural basis: left inferior parietal lobule (storage) + Broca's area (rehearsal).
- **Visuospatial sketchpad**: Visual and spatial information. Neural basis: right posterior parietal cortex (spatial), inferior temporal cortex (visual objects).
- **Episodic buffer**: Integrates information from phonological loop, visuospatial sketchpad, and long-term memory into coherent episodes. Neural basis: bilateral frontal lobes, hippocampal binding.
- **Central executive**: Attentional control, task switching, inhibition. Neural basis: dorsolateral PFC, anterior cingulate cortex.

**Neural mechanisms of working memory**:
- **Persistent firing**: PFC neurons maintain elevated firing rates during delay periods (Goldman-Rakic, 1995). This is supported by recurrent excitatory connections and NMDA receptor dynamics.
- **Synaptic mechanisms**: Activity-silent working memory via short-term synaptic facilitation and residual Ca²⁺ — information can be maintained without sustained firing and "reactivated" by a probe stimulus.
- **Oscillatory mechanisms**: Items in working memory may be maintained as distinct gamma-frequency bursts (~30–80 Hz) organized within theta cycles (4–8 Hz) — each theta phase holds one item (theta-gamma coupling; Lisman & Jensen, 2013).

**Long-Term Memory** (hours to lifetime):
Theoretically unlimited capacity; two major divisions based on conscious accessibility.

### By Content

**Explicit (Declarative) Memory** — consciously accessible; hippocampus-dependent for formation:

- **Episodic memory**: Personal experiences bound to specific spatiotemporal context ("what happened, where, and when"). Hippocampus-dependent for encoding and initial retrieval; gradually becomes independent of hippocampus as it consolidates into neocortex (standard consolidation model) — though some evidence suggests hippocampus remains involved in vivid, detail-rich retrieval indefinitely (multiple trace theory/trace transformation theory). Tulving's "mental time travel."
- **Semantic memory**: General world knowledge, facts, concepts, language; independent of personal spatiotemporal context. Initially hippocampus-dependent, but fully consolidated in temporal neocortex (anterior temporal lobe as a "semantic hub" — damage causes semantic dementia). Concept formation involves abstraction across multiple episodes.

**Implicit (Non-Declarative) Memory** — not consciously accessible; hippocampus-independent:

- **Procedural memory**: Motor skills, cognitive skills, habits. Depends on basal ganglia (caudate/putamen for skill acquisition), cerebellum (motor adaptation, error correction), and supplementary motor area. Learned gradually through practice; resistant to interference and forgetting.
- **Priming**: Facilitated processing of previously encountered stimuli; can be perceptual (same modality — visual cortex) or conceptual (semantic — left PFC). Reduced neural response to repeated stimuli (repetition suppression/neural adaptation).
- **Classical conditioning**: Pavlovian associations.
  - **Delay conditioning** (CS and US overlap): Cerebellum (eyeblink conditioning — interpositus nucleus) for motor CRs; amygdala for emotional CRs (fear conditioning — see Chapter 5)
  - **Trace conditioning** (gap between CS and US offset and US onset): Requires hippocampus (bridging the temporal gap) + amygdala/cerebellum
- **Non-associative learning**: Habituation (decreased response to repeated innocuous stimuli) and sensitization (increased response after noxious stimulus). Primarily spinal/brainstem circuits; modulated by monoaminergic systems.

---

## 7.2 Memory Formation: Encoding

Encoding transforms sensory experience into neural representations that can persist.

### Levels of Processing
Deep semantic processing (thinking about meaning) produces stronger memories than shallow processing (focusing on surface features) — the levels-of-processing framework (Craik & Lockhart, 1972). Neural basis: left inferior frontal gyrus (semantic elaboration) and medial temporal lobe activation during encoding predict subsequent memory (the "subsequent memory effect" in fMRI).

### Encoding Mechanisms

**Synaptic tagging and capture**: Strong stimulation of a synapse creates a transient "tag" (lasting ~1–2 hours) that captures plasticity-related proteins (PRPs) synthesized in response to strong stimulation (even at other synapses on the same neuron). This explains how weakly encoded memories can be strengthened if a strong experience occurs within a temporal window.

**Pattern separation (dentate gyrus)**: Transforms similar inputs into distinct, non-overlapping representations. The DG has ~1 million granule cells (vs. ~250,000 CA3 pyramidal cells in humans); sparse firing (~2–5% active at any time) ensures minimal overlap. Impaired pattern separation → memory interference; decline with aging correlates with memory difficulties in older adults.

**Pattern completion (CA3)**: The extensive recurrent collateral network in CA3 (~30,000 synapses per neuron) forms an autoassociative network — partial or degraded input cues can reactivate the full stored pattern. This enables recall from incomplete information.

### Emotional Enhancement of Memory
Emotionally arousing events are remembered more vividly and persistently. Mechanisms:
1. **Amygdala-hippocampal interaction**: BLA activation during encoding enhances hippocampal consolidation via:
   - Direct glutamatergic projections to hippocampus
   - Modulation of hippocampal norepinephrine (via LC activation) and acetylcholine (via basal forebrain)
2. **Stress hormones**: Cortisol and norepinephrine (acting on β-adrenergic receptors in BLA) → enhanced consolidation for moderate stress; impaired PFC-dependent working memory and retrieval for severe/chronic stress (Yerkes-Dodson inverted-U curve)
3. **Flashbulb memories**: Highly vivid, confident memories for emotionally significant public events. Despite subjective vividness, accuracy degrades over time — the amygdala enhances subjective confidence more than objective accuracy.

---

## 7.3 Synaptic Plasticity: LTP and LTD

### Long-Term Potentiation (LTP)

LTP is a long-lasting increase in synaptic strength following high-frequency stimulation. First described by Bliss & Lømo (1973) at the perforant path-dentate gyrus synapse. It is the primary cellular model for learning and memory.

**NMDA receptor-dependent LTP** (most studied; Schaffer collateral → CA1 synapse):

1. **Induction**: High-frequency presynaptic stimulation releases glutamate → AMPA receptor activation → depolarization. Simultaneously, postsynaptic depolarization (from temporal summation or backpropagating action potential) relieves the Mg²⁺ block of NMDA receptors → Ca²⁺ influx through NMDA channels. The NMDA receptor acts as a **coincidence detector** (requires simultaneous presynaptic glutamate AND postsynaptic depolarization) — Hebb's rule: "neurons that fire together, wire together."

2. **Early-phase LTP (E-LTP; 1–3 hours)**: Ca²⁺ activates CaMKII (autophosphorylation makes it constitutively active) and PKC → phosphorylation of existing AMPA receptors (increased single-channel conductance) + insertion of additional AMPA receptors into the postsynaptic membrane from intracellular pools (exocytosis from recycling endosomes). No new protein synthesis required.

3. **Late-phase LTP (L-LTP; >3 hours, potentially lifelong)**: Higher Ca²⁺ levels activate:
   - PKA → CREB phosphorylation → gene transcription of plasticity-related proteins (Arc, BDNF, Homer1a, CaMKII, new AMPA receptor subunits)
   - mTOR → local dendritic protein synthesis
   - Structural changes: spine enlargement, new spine growth, increased PSD area, insertion of new AMPA receptor slots
   - BDNF-TrkB signaling: BDNF released activity-dependently → TrkB receptor → MAPK/ERK and PI3K/Akt cascades → sustained synaptic strengthening and structural remodeling

**Spike-timing dependent plasticity (STDP)**: The precise temporal order of pre- and postsynaptic spikes determines the direction of plasticity:
- Pre BEFORE post (within ~10–20 ms): LTP (causal relationship)
- Post BEFORE pre (within ~20–50 ms): LTD (anti-causal)
- This provides a biologically realistic learning rule more precise than rate-based Hebbian plasticity.

### Long-Term Depression (LTD)

A long-lasting decrease in synaptic strength. Mechanisms:

- **NMDA receptor-dependent LTD**: Low-frequency stimulation (1 Hz, 15 min) → modest Ca²⁺ rise → activates calcineurin (protein phosphatase 2B) and PP1 → dephosphorylation of AMPA receptors → endocytosis of AMPA receptors from the synapse. LTD may encode "forgetting," refinement of memories, or reversal learning.

- **mGluR-LTD**: Group I mGluR activation (mGluR5 in hippocampus, mGluR1 in cerebellum) → PLC → DAG/IP3 → local protein synthesis via FMRP-regulated translation → AMPA receptor endocytosis. FMRP (fragile X mental retardation protein) normally represses translation; loss → excessive mGluR-LTD → basis of Fragile X syndrome phenotype (intellectual disability, autism features).

- **Cerebellar LTD**: Climbing fiber + parallel fiber coactivation on Purkinje cells → coincident mGluR1 and Ca²⁺ signals → PKC activation → AMPA receptor internalization at the parallel fiber synapse. This is the mechanism underlying cerebellar motor learning (see Chapter 5).

---

## 7.4 Memory Consolidation

### Synaptic Consolidation (minutes to hours)
The molecular stabilization of synaptic changes — transition from labile E-LTP to stable L-LTP via new protein synthesis, structural remodeling, and epigenetic changes (DNA methylation, histone acetylation) at individual synapses.

### Systems Consolidation (weeks to years)
The gradual transfer of memory traces from hippocampus to distributed neocortical networks.

**Standard Consolidation Theory** (Squire, Alvarez): New episodic memories depend on hippocampus for initial storage and retrieval. Over time, cortical-cortical connections strengthen through repeated hippocampal-cortical dialogue (primarily during sleep), and the memory becomes hippocampus-independent. Supporting evidence: temporally graded retrograde amnesia (recent memories more affected than remote ones after hippocampal damage).

**Multiple Trace Theory / Trace Transformation Theory** (Nadel, Moscovitch): Hippocampus creates a new memory trace each time an episodic memory is retrieved. Older memories have more hippocampal traces and are thus more resistant to damage. Semantic/gist-like versions of memories consolidate to cortex, but vivid episodic detail always requires hippocampus. Supporting evidence: flat (non-graded) retrograde amnesia for episodic details in many amnesia cases; hippocampal activation during remote episodic recall in neuroimaging.

### Sleep and Memory Consolidation

Sleep is critical for memory consolidation. The **active systems consolidation** model proposes:

1. During **NREM slow-wave sleep**: Cortical slow oscillations (SO, <1 Hz) orchestrate the temporal coordination of:
   - **Hippocampal sharp-wave ripples (SWRs, 100–250 Hz)**: Compressed replay of recently encoded experiences (~20× real-time speed). Disrupting SWRs impairs consolidation; enhancing them improves memory.
   - **Thalamocortical sleep spindles (12–16 Hz)**: Bursts of 0.5–2 seconds; generated by thalamic reticular nucleus. Spindles are temporally coupled to slow oscillation up-states and SWRs, creating a three-way temporal coordination: SO up-state → spindle → nested SWR.

2. This coordination **reactivates** hippocampal memories during cortical up-states, enabling **synaptic potentiation** in cortical networks (via spindle-associated Ca²⁺ influx through voltage-gated channels during spindle oscillation).

3. **REM sleep** may contribute to memory integration, emotional memory processing (amygdala reactivation without noradrenergic tone from LC — potentially "de-coupling" emotional charge from memory content), and creative insight.

---

## 7.5 Memory Retrieval and Reconsolidation

### Retrieval

**Retrieval cues** activate hippocampal pattern completion → reactivation of the cortical ensemble that was active during encoding (**reinstatement/cortical reactivation** — demonstrated by multivariate fMRI pattern analysis). Successful retrieval depends on the overlap between encoding and retrieval conditions (encoding specificity principle, Tulving).

**Retrieval-induced forgetting**: Selectively retrieving some memories can suppress related but non-retrieved memories (inhibitory mechanism mediated by lateral PFC).

### Reconsolidation

When a consolidated memory is reactivated (retrieved), it transiently becomes **labile** and requires reconsolidation (restabilization through new protein synthesis) to persist. This reconsolidation window (~5–6 hours) opens a potential therapeutic avenue:

- **Disrupting reconsolidation** (e.g., with protein synthesis inhibitors like anisomycin in animal models, or β-adrenergic blockers like propranolol for emotional memories in humans) can weaken or erase the emotional charge of traumatic memories
- **Updating reconsolidation**: New information presented during the reconsolidation window can modify the original memory trace — basis for reconsolidation-based extinction therapy for PTSD and phobias

**Boundary conditions**: Not all retrieval triggers reconsolidation. A prediction error (mismatch between expected and actual experience during retrieval) appears necessary to "destabilize" the trace — if retrieval perfectly matches expectations, the memory remains consolidated.

---

## 7.6 Specialized Memory Phenomena

### Spatial Memory and Navigation

**Hippocampal place cells** (O'Keefe, 1971): CA1/CA3 pyramidal cells that fire when the animal is in a specific location in the environment (the "place field"). Different environments activate different subsets ("remapping"). Nobel Prize 2014 (O'Keefe, shared with Mosers).

**Entorhinal grid cells** (Hafting, Moser & Moser, 2005): Fire at multiple locations arranged in a regular hexagonal grid pattern. Different grid cells have different spatial scales (small grids in dorsal entorhinal cortex, larger grids ventrally) and orientations. Grid cells provide a metric coordinate system for spatial navigation.

**Head direction cells**: Fire when the head faces a particular direction (independent of location). Found in pre/parasubiculum, anterior thalamic nuclei, lateral mammillary nucleus.

**Border cells**: Fire along environmental boundaries. Found in medial entorhinal cortex and subiculum.

Together, these cell types form a **cognitive map** — an internal representation of the environment enabling flexible navigation (O'Keefe & Nadel, 1978). In humans, hippocampal/entorhinal analogs have been demonstrated with single-unit recordings in epilepsy patients and fMRI adaptation paradigms. London taxi drivers (with extensive navigation experience) have enlarged posterior hippocampi.

### Memory and Aging

Age-related memory decline primarily affects:
- Episodic memory (hippocampal-dependent; hippocampal volume declines ~1–2% per year after age 50)
- Source memory (PFC-dependent; frontal atrophy)
- Processing speed (white matter integrity decline)

Relatively preserved with aging: semantic memory, procedural memory, priming.

**Compensatory mechanisms**: Older adults recruit bilateral PFC during memory tasks (HAROLD model — Hemispheric Asymmetry Reduction in Older Adults), potentially compensating for unilateral decline.

---

*Next: [Chapter 8 — Consciousness and Awareness](../08_Consciousness_And_Awareness/Consciousness_And_Awareness.md)*
