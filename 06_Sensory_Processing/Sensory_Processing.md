# Chapter 6: Sensory Processing

## 6.1 General Principles

All sensory systems share fundamental organizational features:

- **Transduction**: Conversion of physical energy into electrical signals by specialized receptor cells
- **Labeled lines**: Each sensory modality travels through dedicated pathways; the perceived quality depends on which pathway is activated, not the nature of the stimulus
- **Topographic mapping**: Orderly spatial representation of the sensory surface in the brain (retinotopy, tonotopy, somatotopy)
- **Hierarchical processing**: Simple features extracted at early stages are combined into increasingly complex representations at higher levels
- **Adaptation**: Reduced response to sustained stimuli, enhancing sensitivity to change
- **Lateral inhibition**: Sharpens boundaries and enhances contrast through inhibitory surround circuits
- **Multisensory integration**: Higher-order areas combine information across modalities (superior temporal sulcus, posterior parietal cortex, superior colliculus)

---

## 6.2 Vision

Vision is the dominant human sense, with approximately 30% of the cortex devoted to visual processing.

### Retinal Processing

The retina is a layered neural tissue (embryologically an outgrowth of the diencephalon) performing significant preprocessing before signals reach the brain.

**Photoreceptors** (outer retina):
- **Rods** (~120 million): High sensitivity (single-photon detection), low acuity; scotopic (dim light) vision; peak absorption ~498 nm; concentrated in periphery; signal through rod bipolar cells → AII amacrine cells
- **Cones** (~6 million): Lower sensitivity, high acuity; photopic (daylight) and color vision; three types:
  - S-cones ("blue"): ~420 nm peak; ~5% of cones
  - M-cones ("green"): ~530 nm peak; ~30% of cones
  - L-cones ("red"): ~560 nm peak; ~65% of cones
  - Fovea: Dense cone packing (~200,000/mm²), no rods; provides highest acuity; each foveal cone has a nearly 1:1 pathway to the brain

**Phototransduction cascade** (in rods; cones analogous):
1. Photon absorption → retinal isomerizes from 11-cis to all-trans form within rhodopsin
2. Activated rhodopsin (metarhodopsin II) → activates transducin (Gαt)
3. Transducin activates phosphodiesterase (PDE6) → hydrolyzes cGMP
4. Decreased cGMP → CNG channels close → reduced Na⁺/Ca²⁺ influx → photoreceptor **hyperpolarizes** (unique among sensory receptors — light reduces activity)
5. Reduced glutamate release from photoreceptor terminals

**Retinal circuit**: Photoreceptors → bipolar cells (ON-type: depolarize to light via mGluR6 sign-inverting synapse; OFF-type: depolarize to darkness via ionotropic glutamate receptors) → retinal ganglion cells (RGCs). Horizontal cells provide lateral inhibition at the photoreceptor-bipolar synapse; amacrine cells modulate bipolar-RGC transmission.

**Retinal ganglion cell types** (~30+ types in primates):
- **Midget (parvocellular, P) cells**: ~80% of RGCs; small receptive fields; color opponency; fine detail
- **Parasol (magnocellular, M) cells**: ~10%; large receptive fields; motion, contrast sensitivity
- **Bistratified (koniocellular) cells**: Blue-yellow color opponency
- **Intrinsically photosensitive RGCs (ipRGCs)**: Express melanopsin; project to SCN (circadian photoentrainment) and olivary pretectal nucleus (pupillary reflex); non-image-forming vision

### Central Visual Processing

**Lateral geniculate nucleus (LGN)**: Six-layered thalamic relay; maintains M/P/K stream separation. Receives massive feedback from V1 (~10× more cortical→LGN than LGN→cortical fibers), suggesting the LGN actively gates visual information based on attentional state and expectations.

**Primary visual cortex (V1)**: Layer IV receives LGN input. V1 neurons extract oriented edges (Hubel & Wiesel's simple and complex cells), spatial frequency, direction of motion, and binocular disparity (stereopsis). V1 is organized into:
- **Orientation columns**: Neurons with similar preferred orientations are grouped vertically
- **Ocular dominance columns**: Alternating bands of left-eye and right-eye preference
- **Blobs**: Cytochrome oxidase-rich regions processing color (P and K pathway)
- **Hypercolumns**: A complete set of orientation columns for both eyes and a blob pair (~1 mm²); represents one point in visual space

**Extrastriate areas**: V2 (border ownership, illusory contours) → V3 (dynamic form) → V4 (color constancy, intermediate form) → V5/MT (motion, speed, direction) → MST (optic flow, self-motion).

**Ventral stream ("what")**: V1 → V2 → V4 → posterior inferotemporal (PIT) → anterior inferotemporal (AIT). Progressive increase in receptive field size, invariance to position/size/viewpoint, and representation complexity. Key areas:
- **Fusiform face area (FFA)**: Face identity processing; prosopagnosia results from FFA damage
- **Parahippocampal place area (PPA)**: Scene/place processing
- **Visual word form area (VWFA)**: Left fusiform gyrus; reading

**Dorsal stream ("where/how")**: V1 → V3 → V5/MT → posterior parietal cortex (PPC). Spatial location, motion processing, visuomotor transformation for reaching/grasping. Damage → optic ataxia (misreaching), akinetopsia (motion blindness).

---

## 6.3 Audition

### Peripheral Processing

**Outer ear**: Pinna collects sound, providing spectral cues for vertical localization; ear canal resonance amplifies frequencies ~2–5 kHz (human speech range).

**Middle ear**: Tympanic membrane → ossicles (malleus → incus → stapes) → oval window of cochlea. The ossicular chain provides impedance matching between air and cochlear fluid (~22× pressure amplification), overcoming the ~99.9% sound energy reflection that would occur at an air-fluid interface. The **stapedius** and **tensor tympani** muscles contract reflexively to attenuate loud sounds (acoustic reflex, latency ~25–150 ms).

**Inner ear (cochlea)**: A fluid-filled spiral (2.5 turns) divided into three chambers:
- **Scala vestibuli** (perilymph, high Na⁺)
- **Scala media / cochlear duct** (endolymph, high K⁺ — maintained by stria vascularis; endocochlear potential +80 mV)
- **Scala tympani** (perilymph)

**Organ of Corti** (on basilar membrane in scala media): Contains ~3,500 inner hair cells (IHCs; sensory) and ~12,000 outer hair cells (OHCs; amplifiers) arranged in rows.

**Transduction**:
1. Sound pressure → basilar membrane vibration. The basilar membrane is tonotopically organized: base (narrow, stiff) → high frequencies; apex (wide, flexible) → low frequencies (von Békésy's traveling wave).
2. Basilar membrane movement → shearing between tectorial membrane and hair cell stereocilia
3. Tip links connecting stereocilia open mechanically-gated K⁺ channels (TMC1/TMC2)
4. K⁺ influx (driven by +80 mV endocochlear potential + -45 mV hair cell resting potential = 125 mV driving force) → depolarization → Ca²⁺ influx → glutamate release onto auditory nerve fibers

**OHC electromotility**: Outer hair cells contain **prestin** (SLC26A5) in their lateral membrane — a motor protein that changes cell length with voltage. OHC contraction/elongation on a cycle-by-cycle basis amplifies basilar membrane vibration by ~40–60 dB (the "cochlear amplifier"), enabling detection of sounds as faint as 0 dB SPL. Damage to OHCs (noise, ototoxic drugs) → sensorineural hearing loss, reduced frequency selectivity, recruitment.

### Central Auditory Pathway

Spiral ganglion neurons (auditory nerve) → **cochlear nucleus** (dorsal and ventral — divergence into parallel processing streams) → **superior olivary complex** (first site of binaural integration — interaural time differences in MSO, interaural level differences in LSO) → **lateral lemniscus** → **inferior colliculus** (integration hub; tonotopic; audiomotor reflexes) → **medial geniculate nucleus (MGN)** of thalamus → **primary auditory cortex (A1)** in Heschl's gyrus (superior temporal plane).

**Cortical processing**: A1 is tonotopically organized. "What" and "where" dual streams exist:
- **Ventral stream** (anterior temporal): Sound identification, speech comprehension
- **Dorsal stream** (parietal): Sound localization, sensorimotor integration for speech production

---

## 6.4 Somatosensation

### Receptor Types

**Mechanoreceptors** (touch, pressure, vibration):
| Receptor | Location | Adaptation | Receptive Field | Modality |
|---|---|---|---|---|
| Meissner's corpuscle | Dermal papillae (glabrous skin) | Rapid | Small | Light touch, texture |
| Merkel cell | Epidermis | Slow | Small | Sustained pressure, form |
| Pacinian corpuscle | Deep dermis, periosteum | Very rapid | Large | Vibration, deep pressure |
| Ruffini ending | Dermis | Slow | Large | Skin stretch |

**Nociceptors** (pain):
- **Aδ nociceptors**: Myelinated; fast, sharp, well-localized "first pain" (~5–30 m/s)
- **C-fiber nociceptors**: Unmyelinated; slow, burning, diffuse "second pain" (~0.5–2 m/s)
  - **Polymodal C-nociceptors**: Respond to mechanical, thermal, and chemical stimuli
  - **Silent/sleeping nociceptors**: Become active only after inflammation → sensitization
- Key molecular sensors: **TRPV1** (capsaicin, heat >43°C), **TRPM8** (menthol, cold <25°C), **TRPA1** (irritants, inflammatory mediators), **Piezo2** (mechanical)

**Thermoreceptors**: Warm fibers (C-fibers, ~30–45°C range), cold fibers (Aδ fibers, ~10–35°C range); express TRP channels (TRPV3/V4 for warmth, TRPM8 for cool, TRPA1 for noxious cold).

**Proprioceptors**: Muscle spindles (detect muscle stretch — Ia and II afferents), Golgi tendon organs (detect muscle tension — Ib afferents), joint receptors.

### Central Somatosensory Pathways

**Dorsal column-medial lemniscal (DCML) pathway** — fine touch, proprioception, vibration:
Aβ/Ia afferents → dorsal root ganglion → dorsal columns (fasciculus gracilis/cuneatus) → nucleus gracilis/cuneatus (medulla) → **decussation** (internal arcuate fibers) → medial lemniscus → **VPL thalamus** → primary somatosensory cortex (S1, BA 3,1,2)

**Anterolateral (spinothalamic) pathway** — pain, temperature, crude touch:
Aδ/C afferents → dorsal horn (laminae I, II, V) → **decussation** (anterior commissure, within 1–2 segments) → spinothalamic tract → **VPL thalamus** → S1 and insular cortex

**Pain modulation — descending inhibition**: Periaqueductal gray (PAG) → nucleus raphe magnus (serotonergic) and locus coeruleus (noradrenergic) → dorsal horn → inhibit pain transmission via:
- Direct inhibition of spinothalamic neurons
- Activation of enkephalin-containing interneurons in dorsal horn (gate control theory, Melzack & Wall, 1965 — Aβ fiber input "closes the gate" on C-fiber pain transmission)
- Endogenous opioid release (endorphins, enkephalins, dynorphins)

**Cortical somatosensory areas**: S1 has four subregions (BA 3a — proprioception; 3b — cutaneous; 1 — texture; 2 — size, shape). Each contains a complete somatotopic map (sensory homunculus — body regions represented proportional to innervation density, not physical size; hands, lips, and tongue are enormously overrepresented). S1 → **S2** (secondary somatosensory cortex, lateral sulcus) → posterior parietal cortex (integration with vision for object recognition by touch — stereognosis).

---

## 6.5 Olfaction

Olfaction is unique among senses: it does not relay through the thalamus before reaching cortex (though the thalamic mediodorsal nucleus receives secondary olfactory input).

### Peripheral Processing

**Olfactory epithelium** (superior nasal cavity, ~5 cm²): Contains ~6 million olfactory sensory neurons (OSNs), each expressing a single olfactory receptor (OR) gene out of ~400 functional OR genes in humans (from the original ~1,000 — largest gene family in the genome; ~60% are pseudogenes in humans vs. ~20% in mice).

**Transduction**: Odorant molecule → binds OR (GPCR) → Gαolf → adenylyl cyclase III → cAMP → opens cyclic nucleotide-gated (CNG) channels → Na⁺/Ca²⁺ influx → depolarization. Ca²⁺ also opens Ca²⁺-activated Cl⁻ channels → Cl⁻ efflux (unusual because OSN intracellular Cl⁻ is high) → further depolarization and amplification.

**Combinatorial coding**: Each odorant activates a unique combination of ORs; each OR responds to multiple odorants. This combinatorial scheme enables discrimination of potentially >1 trillion distinct odors.

### Central Olfactory Pathway

OSN axons → **olfactory bulb** (axons from neurons expressing the same OR converge onto the same glomerulus — ~2 per OR, ~800 glomeruli total). Glomerular layer: OSN axons synapse onto mitral and tufted cells (principal neurons). Periglomerular cells and granule cells (both GABAergic) provide lateral inhibition — sharpening odor representations.

Mitral/tufted cell axons → **lateral olfactory tract** → primary olfactory cortex:
- **Piriform cortex**: Largest olfactory cortical area; odor identity encoding; autoassociative network for odor pattern completion
- **Amygdala (cortical nuclei)**: Emotional valence of odors
- **Entorhinal cortex**: Gateway to hippocampus — explains strong olfactory-memory associations ("Proustian memory")
- **Orbitofrontal cortex** (via thalamic MD nucleus): Conscious odor perception, hedonic evaluation

**Olfactory neurogenesis**: The olfactory epithelium and olfactory bulb are sites of lifelong neurogenesis. OSNs have a lifespan of ~30–60 days and are continuously replaced from basal stem cells. SVZ-generated neuroblasts migrate via the rostral migratory stream to become olfactory bulb interneurons.

---

## 6.6 Gustation (Taste)

### Taste Receptor Cells

**Taste buds** (~5,000–10,000 in humans) are located on papillae of the tongue, soft palate, epiglottis, pharynx, and esophagus. Each bud contains 50–100 taste receptor cells (TRCs) of 3 types:

- **Type I (glial-like)**: Support cells; may mediate salt taste (via ENaC channels)
- **Type II (receptor cells)**: Express T1R or T2R GPCRs; detect sweet, umami, or bitter (each cell detects one modality)
  - **Sweet**: T1R2 + T1R3 heterodimer → Gαgustducin → PLCβ2 → IP3 → Ca²⁺ release → TRPM5 channel → depolarization → ATP release (via CALHM1 channels)
  - **Umami**: T1R1 + T1R3 heterodimer (same cascade as sweet)
  - **Bitter**: ~25 T2R receptors (each cell expresses multiple T2Rs — same cascade; bitter perception is a generalized "avoid" signal)
- **Type III (presynaptic cells)**: Detect sour (via Otop1 proton channel) and possibly some salt stimuli; form conventional synapses with afferent nerve fibers

**Salt taste**: Amiloride-sensitive salt taste via ENaC (epithelial sodium channels) in Type I cells; amiloride-insensitive component via unknown mechanism.

### Central Gustatory Pathway

Cranial nerves carry taste from different regions: VII (facial — chorda tympani branch: anterior 2/3 of tongue); IX (glossopharyngeal: posterior 1/3 of tongue); X (vagus: epiglottis, pharynx).

All converge on → **nucleus of the solitary tract (NTS)** (rostral gustatory portion) → **parabrachial nucleus** (in rodents; may be bypassed in primates) → **ventral posteromedial nucleus (VPMpc)** of thalamus → **primary gustatory cortex** (anterior insula and frontal operculum) → **secondary gustatory cortex** (orbitofrontal cortex — integrates taste with smell for flavor perception, and with hunger/satiety signals for palatability).

---

## 6.7 Vestibular System

### Peripheral Apparatus

The vestibular labyrinth within the inner ear contains:

**Three semicircular canals** (horizontal, anterior, posterior): Detect angular acceleration (head rotation). Each canal contains a swelling (**ampulla**) housing the **crista ampullaris** — a ridge of hair cells with stereocilia embedded in a gelatinous **cupula**. Endolymph flow during head rotation deflects the cupula → bends stereocilia → depolarization (toward kinocilium) or hyperpolarization (away from kinocilium). The three canals are oriented in orthogonal planes, encoding rotation in any direction. Canals are organized in complementary pairs (left horizontal ↔ right horizontal; left anterior ↔ right posterior).

**Otolith organs** — detect linear acceleration and head tilt (gravity):
- **Utricle**: Horizontal plane; detects forward/backward and lateral acceleration
- **Saccule**: Vertical plane; detects up/down acceleration
- Hair cells on the **macula**; stereocilia embedded in a gelatinous layer covered with **otoliths** (calcium carbonate crystals) that shift with linear acceleration/gravity → stereocilia deflection

### Central Vestibular Processing

Vestibular nerve (VIII) → **vestibular nuclei** (medulla/pons; 4 nuclei: superior, inferior, medial, lateral) → multiple outputs:
- **Vestibulo-ocular reflex (VOR)**: Vestibular nuclei → oculomotor nuclei (III, IV, VI) — stabilizes gaze during head movement; operates at ~10 ms latency; gain ~1.0
- **Vestibulospinal reflexes**: Lateral vestibulospinal tract → antigravity extensor muscles (postural stability); medial vestibulospinal tract → neck muscles (head stabilization)
- **Vestibular cortex**: Parieto-insular vestibular cortex (PIVC) — conscious perception of body orientation and self-motion
- **Cerebellum** (flocculonodular lobe): Calibrates VOR gain; damage → nystagmus, ataxia

---

## 6.8 Proprioception and Interoception

### Proprioception

The "sixth sense" — awareness of body position and movement without vision.

**Muscle spindles**: Intrafusal fibers (nuclear bag and nuclear chain fibers) encapsulated within muscle. **Type Ia afferents** wrap around the central region — detect dynamic stretch (velocity-sensitive). **Type II afferents** on nuclear chain fibers — detect static stretch (length-sensitive). **Gamma motor neurons** adjust spindle sensitivity by contracting intrafusal fiber ends (alpha-gamma coactivation maintains spindle sensitivity during voluntary contraction).

**Golgi tendon organs**: Located at muscle-tendon junctions; **Type Ib afferents** — detect muscle tension/force. During active contraction, they mediate the inverse myotatic reflex (autogenic inhibition — protective against excessive force).

Central pathway: Ia/II afferents → dorsal columns → dorsal column nuclei → medial lemniscus → VPL thalamus → S1 (BA 3a) → posterior parietal cortex (spatial body representation; body schema).

### Interoception

Perception of internal bodily states — heartbeat, breathing, hunger, thirst, visceral pain, temperature, itch, sensual touch. Signals travel via:
- **Lamina I spinothalamic neurons** → VMpo and VMb thalamic nuclei → **posterior insular cortex** → **anterior insular cortex** (where interoceptive signals are integrated into a unified sense of body ownership and subjective feeling states)
- **Vagus nerve** (major visceral afferent) → NTS → parabrachial nucleus → thalamus/hypothalamus → insula

Interoceptive accuracy (ability to detect heartbeats, for example) varies across individuals and correlates with emotional awareness, empathy, anxiety (heightened interoception), and altered function in anxiety disorders, eating disorders, and depersonalization.

---

*Next: [Chapter 7 — Memory Systems](../07_Memory_Systems/Memory_Systems.md)*
