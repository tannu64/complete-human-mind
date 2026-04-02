# Chapter 16: Genetics and the Brain — Mathematical Equations

## Section 1: Heritability and Twin Studies

### 1.1 Falconer's Heritability Formula

The most widely used estimate of heritability from twin studies:

$$h^2 = 2(r_{MZ} - r_{DZ})$$

where:
- $r_{MZ}$ = correlation of trait in monozygotic (identical) twins
- $r_{DZ}$ = correlation of trait in dizygotic (fraternal) twins
- $h^2$ = broad-sense heritability (proportion of phenotypic variance due to genetic variance)

**Derivation**: MZ twins share ~100% of DNA; DZ twins share ~50% on average. Assuming equal environments for both types, the difference in correlation is attributable to genetic factors.

| Variable | Typical Range | Notes |
|---|---|---|
| $r_{MZ}$ | 0.5–1.0 | MZ correlation; higher values indicate stronger genetic influence |
| $r_{DZ}$ | 0.0–0.5 | DZ correlation; typically ~0.25–0.40 for brain traits |
| $h^2$ | 0.0–1.0 | 0 = purely environmental; 1 = purely genetic |

**Example**: For IQ, typical $r_{MZ} \approx 0.86$ and $r_{DZ} \approx 0.60$, yielding $h^2 = 2(0.86 - 0.60) = 0.52$ (52% heritability).

### 1.2 Broad-Sense vs. Narrow-Sense Heritability

Broad-sense heritability:

$$H^2 = \frac{V_G}{V_P} = \frac{V_G}{V_G + V_E}$$

Narrow-sense heritability (additive genetic effects only):

$$h^2 = \frac{V_A}{V_P}$$

where:
- $V_G$ = total genetic variance (includes dominance, epistasis)
- $V_A$ = additive genetic variance
- $V_E$ = environmental variance (shared + unique)
- $V_P$ = total phenotypic variance

| Variable | Definition | Heritability Range |
|---|---|---|
| $V_A$ | Additive effects (alleles summing linearly) | Typically 40–80% for IQ |
| $V_D$ | Dominance (heterozygote effects) | Usually small for complex traits |
| $V_I$ | Epistasis (gene-gene interactions) | Often overlooked; magnitude unclear |
| $V_E^{shared}$ | Shared family environment (nutrition, SES) | Decreases with age from ~30% to ~5% by adulthood |
| $V_E^{unique}$ | Individual-specific environment (peer group, accidents) | Increases with age |

**Clinical significance**: Narrow-sense heritability guides prediction of trait response to selection or environmental intervention.

### 1.3 Shared and Unique Environment Decomposition

Extended twin model partitioning environmental variance:

$$V_P = V_A + V_D + V_E^{shared} + V_E^{unique}$$

Estimating shared environment:

$$c^2 = 2(r_{DZ} - r_{MZ})$$

where $c^2$ is the proportion of variance explained by shared environment.

Unique environment:

$$e^2 = 1 - h^2 - c^2$$

| Component | Typical for IQ | Typical for Schizophrenia |
|---|---|---|
| $h^2$ (narrow heritability) | 0.50 | 0.64 |
| $c^2$ (shared environment) | 0.20 | 0.10 |
| $e^2$ (unique environment + error) | 0.30 | 0.26 |

**Note**: Shared environment contribution decreases with age for cognitive traits, suggesting adult phenotypes are largely determined by genetics and idiosyncratic experiences.

---

## Section 2: Polygenic Architecture and GWAS

### 2.1 Polygenic Risk Score (PRS)

Sum of allelic effects across many genome-wide significant loci:

$$\text{PRS} = \sum_{i=1}^{n} \beta_i \cdot A_i$$

where:
- $\beta_i$ = effect size (log odds ratio or standardized beta) at SNP $i$ from GWAS
- $A_i$ = number of risk alleles (0, 1, or 2) at locus $i$
- $n$ = number of SNPs included in the score

**Clinical application**: Individuals in the top 10% of PRS for schizophrenia have ~3–4× increased lifetime risk vs. population mean. However, PRS remains insufficiently predictive for individual clinical use.

| Parameter | Range | Notes |
|---|---|---|
| $\beta_i$ (per-allele effect) | 0.01–0.50 (log OR) | Typically 0.01–0.05 for complex traits |
| $n$ (number of SNPs) | 100–1,000,000+ | Larger $n$ improves prediction if SNPs are valid |
| Effect size of top 1% of variants | ~0.1–0.3 | Often 10–100× larger than median variant |

### 2.2 Variance Explained by Detected SNPs

Proportion of phenotypic variance explained by GWAS-identified variants:

$$R^2 = 2 \sum_{i=1}^{n} \beta_i^2 \cdot p_i(1 - p_i)$$

where:
- $\beta_i$ = standardized regression coefficient at SNP $i$
- $p_i$ = frequency of the effect allele at locus $i$

**Interpretation**: For schizophrenia, ~300 genome-wide significant loci explain ~7% of variance on the liability scale. For educational attainment, >4,000 loci explain ~15% of variance. The "missing heritability" resides in rare variants, gene-gene interactions, and gene-environment interactions.

| Trait | Variance Explained by SNPs | Twin Heritability | Missing Heritability |
|---|---|---|---|
| IQ | 20–25% | 50–80% | 25–55% |
| Schizophrenia | 7% | 64% | 57% |
| Educational attainment | 15% | 40–60% | 25–45% |
| Autism | 10–15% | 80–90% | 65–75% |

### 2.3 SNP Heritability Estimation (GCTA/LDSC)

Genome-wide Complex Trait Analysis estimates heritability explained by common SNPs:

$$h^2_{SNP} = \frac{\text{Var}(\text{PRS})}{V_P}$$

where $\text{Var}(\text{PRS})$ is the variance in polygenic risk scores across the population.

Linkage Disequilibrium Score Regression (LDSC) accounts for LD structure:

$$\chi^2_j = \sum_k r_{jk}^2 \cdot h^2 \cdot N$$

where:
- $\chi^2_j$ = chi-square statistic for SNP $j$
- $r_{jk}^2$ = LD between SNPs $j$ and $k$
- $N$ = sample size
- $h^2$ = heritability (estimated from slope)

| Metric | Typical Value | Interpretation |
|---|---|---|
| $h^2_{SNP}$ for schizophrenia | 0.21 | Common variants explain 21% of variance |
| Genetic correlation (schizophrenia–bipolar) | 0.60 | 60% of genetic risk is shared |
| Genetic correlation (schizophrenia–education) | -0.30 | Genetic variants increasing schizophrenia risk tend to decrease education |

---

## Section 3: Population Genetics (Hardy-Weinberg Equilibrium)

### 3.1 Hardy-Weinberg Equilibrium

At genetic equilibrium with random mating and no selection:

$$p^2 + 2pq + q^2 = 1$$

where:
- $p$ = frequency of allele A
- $q$ = frequency of allele a (with $p + q = 1$)
- $p^2$ = frequency of genotype AA
- $2pq$ = frequency of heterozygote Aa
- $q^2$ = frequency of homozygote aa

**Assumptions**: Large population, random mating, no mutation, no selection, no migration.

| Scenario | Equation | Example |
|---|---|---|
| Allele frequency from genotype | $p = f(AA) + 0.5 \cdot f(Aa)$ | If $f(AA)=0.25$, $f(Aa)=0.50$, then $p=0.625$ |
| Expected genotype frequencies | $f(AA)=p^2$, $f(Aa)=2pq$, $f(aa)=q^2$ | If $p=0.7$, then $f(AA)=0.49$, $f(Aa)=0.42$, $f(aa)=0.09$ |
| Rare allele assumption | If $q \ll 1$, then $f(Aa) \approx 2q$ | For $q=0.01$, heterozygotes comprise ~2% of population |

**Clinical relevance**: Deviations from HWE suggest population stratification, assortative mating, or selection — common issues in association studies.

### 3.2 Allele Frequency Change Under Selection

Change in allele frequency with directional selection:

$$p(t) = \frac{p(0)}{p(0) + q(0) \cdot e^{-st}}$$

or for weak selection:

$$\Delta p = \frac{s \cdot p \cdot q \cdot (p - q)}{1 - 2pqs}$$

where:
- $s$ = selection coefficient (0 = no selection; 1 = lethal)
- $t$ = generations
- $p(0)$ = initial allele frequency

**Example**: A disease allele with $s=0.1$ (10% reduction in reproductive fitness) and initial $p=0.5$ decreases to $p=0.48$ in one generation.

| Selection Scenario | Selection Coefficient | Change per Generation | Time to Reduce by 50% |
|---|---|---|---|
| Neutral (no selection) | 0 | 0 | ∞ |
| Mild selection against rare allele | 0.01 | ~0.00001 | ~7000 generations |
| Moderate selection | 0.10 | ~0.001–0.005 | ~100–700 generations |
| Strong selection (lethal) | 1.0 | ~0.5 (if heterozygous lethal) | 1–2 generations |

---

## Section 4: Linkage Disequilibrium and Association

### 4.1 Linkage Disequilibrium (LD) r² Measure

Standardized measure of non-random association between two SNPs:

$$r^2 = \frac{D^2}{p_A(1-p_A) \cdot p_B(1-p_B)}$$

where:
- $D = p_{AB} - p_A \cdot p_B$ (deviation from random association)
- $p_A$, $p_B$ = allele frequencies of SNPs A and B
- $p_{AB}$ = frequency of haplotype carrying both A and B alleles
- $r^2$ ranges from 0 (no LD) to 1 (complete LD)

**Interpretation**: $r^2 = 0.8$ indicates that 80% of information at locus B is captured by locus A.

| $r^2$ Value | LD Strength | Haplotype Information | GWAS Implication |
|---|---|---|---|
| 0.0–0.1 | None | <10% | Independent signal |
| 0.1–0.3 | Weak | 10–30% | Possibly independent |
| 0.3–0.8 | Moderate | 30–80% | May tag same causal variant |
| 0.8–1.0 | Strong | >80% | Likely same causal variant |

### 4.2 LD Decay with Genomic Distance

Exponential decay of LD as a function of physical distance:

$$r^2(d) = r^2(0) \cdot e^{-\alpha d}$$

or simplified inverse relationship:

$$r^2(d) \approx \frac{0.1}{d/1000 \text{ bp}}$$

where:
- $d$ = physical distance between SNPs (in base pairs)
- $\alpha$ = decay rate parameter (~0.001–0.01 per kb depending on recombination rate)

**Empirical observation**: LD halves approximately every 1–2 kb in Europeans (varies by ancestry).

| Distance (kb) | Expected $r^2$ (Europeans) | Notes |
|---|---|---|
| 1 | 0.50–0.70 | Strong LD in tight regions |
| 5 | 0.15–0.30 | LD weakening |
| 10 | 0.05–0.15 | Weak LD; mostly independent information |
| 100+ | <0.02 | Essentially no LD for most variants |

**GWAS design**: SNP arrays typically capture ~80% of common variants via LD tagging, using ~500,000–2.5 million SNPs.

---

## Section 5: GWAS Effect Sizes and Significance

### 5.1 Log Odds Ratio from Beta Coefficients

Conversion of linear regression coefficient to odds ratio for disease association:

$$\log(\text{OR}) = \beta \cdot 2 \cdot p(1-p)$$

where:
- $\beta$ = standardized regression coefficient (case-control logistic regression)
- $p$ = effect allele frequency
- $\text{OR}$ = odds ratio per copy of effect allele

**Alternative**: Direct logistic regression yields $\beta$ as the log-odds change per allele; $\text{OR} = e^\beta$.

| Effect Size | Interpretation | Typical GWAS Finding |
|---|---|---|
| $\text{OR}=1.05$ | 5% increase in odds per allele | Most discovered variants (~99%) |
| $\text{OR}=1.10$ | 10% increase | Top 1% of variants |
| $\text{OR}=1.20$ | 20% increase | Rare variants; very large studies |
| $\text{OR}=2.0$ | 100% increase (doubling) | Familial mutations (e.g., PSEN1 in AD) |

### 5.2 Genome-Wide Significance Threshold

Standard multiple-testing correction for GWAS:

$$-\log_{10}(p_{\text{threshold}}) = 7.3$$

or equivalently:

$$p_{\text{threshold}} = 5 \times 10^{-8}$$

**Derivation**: Bonferroni correction across ~1 million independent tests; $0.05 / 1,000,000 = 5 \times 10^{-8}$.

**Justification**: Approximately 1 million independent common variants in the human genome. Assumes weak LD; in practice, LD structure reduces independent tests but the threshold has proven empirically robust across populations.

| Test Statistic | Interpretation |
|---|---|
| $-\log_{10}(p) < 5.0$ | Suggestive association; follow-up needed |
| $5.0 < -\log_{10}(p) < 7.3$ | Significant in discovery but below genome-wide threshold |
| $-\log_{10}(p) \geq 7.3$ | Genome-wide significant; strong replication probability |
| $-\log_{10}(p) \geq 8.0$ | Very strong association; rare |

---

## Section 6: Epigenetic Methylation Dynamics

### 6.1 DNA Methylation Level Changes During Learning and Stress

Exponential approach to equilibrium methylation state:

$$m(t) = m_{eq} + (m_0 - m_{eq}) \cdot e^{-kt}$$

where:
- $m(t)$ = methylation level (proportion of sites methylated) at time $t$
- $m_{eq}$ = equilibrium methylation level (final state)
- $m_0$ = initial methylation level
- $k$ = rate constant for methylation/demethylation (typically 0.01–0.1 per hour)
- $t$ = time (hours)

**Context**: Learning activates immediate methylation changes at BDNF, reelin, and PP1 promoters within 1–4 hours. Stress (early adversity) increases glucocorticoid receptor (Nr3c1) promoter methylation, reducing gene expression and impairing stress resilience.

| Gene | Baseline Methylation | After Learning/Stress | Time Course |
|---|---|---|---|
| BDNF exon IV promoter | 40–60% | ↓ 15–25% demethylation | 1–4 hours |
| Nr3c1 (GR promoter) | 10–20% (normal reared) | ↑ 40–50% (abused) | Persists into adulthood |
| Reelin promoter | 60% (naïve) | ↓ 30–40% (learning) | 2–6 hours |

**Clinical significance**: Epigenetic marks in key neuroplasticity genes serve as molecular memory of experience; potentially reversible with therapeutic intervention.

### 6.2 Histone Acetylation and Gene Expression

Hill-type relationship between histone acetylation and transcriptional activation:

$$\text{Expression} = E_{max} \cdot \frac{[\text{Ac-Histone}]^n}{K_d^n + [\text{Ac-Histone}]^n}$$

or linearized as:

$$\Delta \text{Expression} = g \cdot \log\left(\frac{[\text{Ac-H3}]}{[\text{H3}]}\right)$$

where:
- $[\text{Ac-Histone}]$ = concentration of acetylated histone (proportion of total histone)
- $K_d$ = half-maximal activation histone acetylation level
- $n$ = cooperativity (typically 1–2 for histone acetylation)
- $g$ = slope (effect of acetylation on expression in log scale)

**Mechanism**: Histone deacetylase (HDAC) inhibitors enhance acetylation → increased chromatin accessibility → enhanced transcription of memory genes (BDNF, c-fos, cfos, Arc).

| Histone Modification | Gene Target | Effect on Expression | HDAC Inhibitor Response |
|---|---|---|---|
| H3K9 acetylation | BDNF, c-fos | ~2–4× increase | Enhanced with HDAC inhibitor |
| H3K27 trimethylation | Repressive chromatin | Silenced | Blocked by HDAC inhibitors |
| H4 acetylation broadly | Active genes | ~1.5–3× baseline | Strong; improves memory consolidation |

---

## Section 7: Pharmacogenomics and CYP450 Drug Metabolism

### 7.1 CYP450-Mediated Drug Clearance

First-order pharmacokinetics with CYP-dependent clearance:

$$\frac{dC}{dt} = -\frac{CL}{V_d} \cdot C(t)$$

Solution (single dose):

$$C(t) = \frac{D}{V_d} \cdot e^{-\frac{CL}{V_d} \cdot t} = C_0 \cdot e^{-k \cdot t}$$

where:
- $C(t)$ = plasma drug concentration at time $t$
- $CL$ = clearance (ml/min/kg) — depends on CYP450 activity
- $V_d$ = volume of distribution
- $k$ = elimination rate constant ($k = CL/V_d$)
- $t_{1/2} = \frac{\ln(2)}{k} = 0.693/k$ (half-life)

**Metabolizer phenotypes and CYP activity**:

| Phenotype | CYP Activity | Drug Concentration | Clinical Outcome |
|---|---|---|---|
| Ultra-rapid metabolizer (UM) | >125% normal | ↓↓ (very low) | Subtherapeutic; treatment failure |
| Rapid metabolizer (RM) | 75–125% normal | ↓ (slightly low) | Possible underdosing |
| Normal/extensive metabolizer (EM) | 75–125% normal | Normal | Standard dosing appropriate |
| Intermediate metabolizer (IM) | 50–75% normal | ↑ (slightly high) | May require dose adjustment |
| Poor metabolizer (PM) | <25% normal | ↑↑ (very high) | Risk of toxicity; reduce dose by 25–75% |

**Example**: CYP2D6 poor metabolizers metabolize SSRIs ~3× slower; therapeutic levels achieved at standard dose within 2 days (vs. 2 weeks normally).

### 7.2 Phenotype-Dependent Steady-State Concentrations

At steady state with repeated dosing:

$$C_{ss} = \frac{F \cdot D}{CL \cdot \tau}$$

where:
- $C_{ss}$ = steady-state concentration
- $F$ = bioavailability
- $D$ = dose
- $CL$ = clearance (metabolizer phenotype–dependent)
- $\tau$ = dosing interval

For poor metabolizers with $CL_{PM} = 0.25 \cdot CL_{normal}$:

$$C_{ss,PM} = 4 \times C_{ss,normal}$$

**Therapeutic window implications**:

| Drug (CYP Enzyme) | Therapeutic Window | PM Concentration | Toxicity Risk |
|---|---|---|---|
| Citalopram (CYP2C19) | 20–110 ng/ml | ↑ 3–5× if PM | Arrhythmia, QT prolongation |
| Escitalopram (CYP2C19) | 15–80 ng/ml | ↑ 3–5× if PM | Similar to citalopram |
| Tricyclic antidepressants (CYP2D6) | 50–150 ng/ml | ↑ 3–4× if PM | Cardiac arrhythmia, anticholinergic effects |
| Codeine (CYP2D6→morphine) | Active parent+metabolite | No analgesic if PM | Pain relief failure (codeine inactive) |

---

## Section 8: Gene-Environment Interaction (GxE)

### 8.1 GxE Variance Decomposition

Phenotypic variance partitioning in presence of gene-environment interaction:

$$V_P = V_G + V_E + V_{GxE} + 2\text{Cov}(G,E)$$

where:
- $V_G$ = genetic variance (independent of environment)
- $V_E$ = environmental variance (independent of genes)
- $V_{GxE}$ = variance due to genotype-by-environment interaction
- $\text{Cov}(G,E)$ = covariance between genetic and environmental factors (gene-environment correlation; often ~0 if environments are randomly distributed)

**Simplified (assuming $\text{Cov}(G,E) \approx 0$)**:

$$V_P = V_G + V_E + V_{GxE}$$

$$h^2 = \frac{V_G}{V_P}, \quad e^2 = \frac{V_E}{V_P}, \quad (g \times e)^2 = \frac{V_{GxE}}{V_P}$$

**Example**: Depression risk with 5-HTTLPR genotype and childhood adversity:

| Genotype | No Adversity | Moderate Adversity | Severe Adversity |
|---|---|---|---|
| S/S (short/short, low SERT) | 5% depression risk | 15% depression risk | 40% depression risk |
| S/L (heterozygote) | 3% depression risk | 10% depression risk | 25% depression risk |
| L/L (long/long, high SERT) | 2% depression risk | 5% depression risk | 15% depression risk |

The difference in slopes across genotypes indicates $V_{GxE}$.

### 8.2 Differential Susceptibility Model

Vulnerability/benefit allocation based on genetic sensitivity to environment:

$$\text{Outcome} = \mu + \beta_G \cdot G + \beta_E \cdot E + \beta_{GxE} \cdot G \cdot E$$

where:
- $\mu$ = population mean outcome
- $\beta_G$ = main effect of genotype
- $\beta_E$ = main effect of environment
- $\beta_{GxE}$ = interaction (same sign suggests "orchid" susceptibility; opposite signs suggest diathesis-stress)

**Orchid vs. Dandelion interpretation**:
- **Orchid genotype**: Performs worse in adverse environments but *better* in supportive environments (synergistic interaction, $\beta_{GxE}$ same sign as main effects).
- **Dandelion genotype**: Resilient across environments; less affected by adversity.

| Scenario | $\beta_E$ | $\beta_{GxE}$ | Interpretation |
|---|---|---|---|
| Diathesis-stress | Negative (adversity harms) | Negative (genetic risk increases harm) | Traditional vulnerability model |
| Differential susceptibility | Positive (support benefits) | Positive (genetic sensitivity amplifies benefit) | "Orchid" model — genes confer dual edge |
| Buffering | Any | Near zero | Genotype buffers against environment |

**Example**: DRD4 7-repeat VNTR allele shows worse outcomes in poor environments but better outcomes in enriched environments (classic orchid pattern).

---

## Section 9: Genetic Risk, Liability-Threshold, and CNV Dosage

### 9.1 Liability-Threshold Model for Complex Diseases

Disease risk modeled as crossing a threshold on a latent liability distribution:

$$\text{Disease Risk} = P(L > \theta)$$

where:
- $L$ = latent liability (normally distributed)
- $\theta$ = disease threshold
- $L = \mu_G + \mu_E + \epsilon$ (genetic + environmental + residual components)

For a trait with heritability $h^2$ and population prevalence $K$:

$$\text{Lifetime risk in relative} = \Phi^{-1}(\sqrt{2 \cdot h^2} \cdot \Phi^{-1}(1-K) + \Phi^{-1}(1-K_r))$$

where:
- $\Phi$ = cumulative normal distribution
- $K$ = population prevalence
- $K_r$ = relative's expected prevalence based on genetic relationship (0.5 for first-degree relatives, 0.25 for second-degree, etc.)

**Simplified for family risk**:

$$\text{Risk}_{\text{sibling}} = \frac{\sqrt{2 \cdot h^2} \cdot \Phi^{-1}(1-K) - \Phi^{-1}(1-K)}{1.414}$$

| Disorder | Population Prevalence | Heritability | First-Degree Relative Lifetime Risk |
|---|---|---|---|
| Schizophrenia | 1% | 0.64 | ~10–13% |
| Bipolar disorder | 1–2% | 0.70–0.80 | ~10–15% |
| Major depression | 10–15% | 0.35 | ~15–20% |
| Autism spectrum | 1–2% | 0.80–0.90 | ~10–20% |

### 9.2 Copy Number Variant Dosage Effects

Copy number variants (CNVs) increase risk through copy-number dosage imbalance:

$$\text{Risk} = r_0^{n_{copies}} \cdot \text{(baseline risk)}$$

where:
- $n_{copies}$ = number of copies of risk CNV (normal: 2; deletion: 1; duplication: 3)
- $r_0$ = risk increase per copy

**For recessive/haploinsufficient CNVs**:
- 0 copies: Lethal or severe phenotype (homozygous deletion)
- 1 copy: Disease risk increased (haploinsufficiency; ~5–20× elevated)
- 2 copies: Normal/baseline
- 3 copies: May cause disease (triplosensitivity; e.g., 16p11.2 dup in autism)

| CNV | Location | Frequency | Associated Disorder | Risk Elevation |
|---|---|---|---|---|
| 22q11.2 deletion | q11.2 | 1:2,000–4,000 | Schizophrenia | 20–25× |
| 16p11.2 deletion | p11.2 | 1:10,000 | Autism, developmental delay | 15–20× |
| 16p11.2 duplication | p11.2 | 1:10,000 | Autism, developmental delay | 10–15× |
| SHANK3 deletion | 22q13 | Rare (1:50,000) | Phelan-McDermid syndrome | >100× |
| 2q37.3 deletion | q37.3 | Rare | Intellectual disability | High |

**Phenotypic consequence**: Dosage-sensitive haploinsufficiency (gene-dosage imbalance) → disrupted gene expression → neuronal network dysfunction.

---

## Section 10: Case Studies

### Case Study 1: Twin-Based Heritability Estimation for Personality

**Scenario**: A twin study of neuroticism (anxiety-proneness) reports:
- MZ twin correlation: $r_{MZ} = 0.48$
- DZ twin correlation: $r_{DZ} = 0.24$

**Calculate**: Heritability using Falconer's formula and interpret.

**Solution**:

$$h^2 = 2(r_{MZ} - r_{DZ}) = 2(0.48 - 0.24) = 2 \times 0.24 = 0.48$$

Approximately **48% of neuroticism variance is due to genetic differences**.

Estimate shared environment:

$$c^2 = 2(r_{DZ} - r_{MZ}) = 2(0.24 - 0.48) = -0.48$$

(Negative; indicates no shared environment effect — consistent with literature showing family environment has weak effects on adult personality once genetic similarity is accounted for.)

Unique environment + error:

$$e^2 = 1 - 0.48 - 0 = 0.52$$

**Interpretation**: About half of individual differences in neuroticism are genetic; the other half reflects unique individual experiences (friendships, life events, random developmental noise). Shared family environment (SES, parenting style) contributes minimally, suggesting developmental canalization or that by adulthood, individual-specific experiences dominate.

---

### Case Study 2: Polygenic Score Calculation and Risk Stratification

**Scenario**: A GWAS of major depressive disorder identified 10 significant SNPs. Effect sizes (log OR per risk allele) and allele frequencies in a target individual are:

| SNP | $\beta_i$ (log OR) | Risk Allele Frequency | Individual's Genotype | Allele Count |
|---|---|---|---|---|
| rs1 | 0.05 | 0.30 | Heterozygous | 1 |
| rs2 | 0.08 | 0.15 | Homozygous risk | 2 |
| rs3 | 0.03 | 0.50 | Heterozygous | 1 |
| rs4 | 0.06 | 0.20 | Homozygous risk | 2 |
| rs5 | 0.04 | 0.40 | Homozygous non-risk | 0 |
| rs6 | 0.07 | 0.25 | Heterozygous | 1 |
| rs7 | 0.02 | 0.60 | Heterozygous | 1 |
| rs8 | 0.09 | 0.10 | Homozygous risk | 2 |
| rs9 | 0.05 | 0.35 | Homozygous non-risk | 0 |
| rs10 | 0.04 | 0.45 | Heterozygous | 1 |

**Calculate**: Polygenic risk score; translate to odds ratio for MDD.

**Solution**:

$$\text{PRS} = \sum_{i=1}^{10} \beta_i \cdot A_i$$

$$\text{PRS} = 0.05 \cdot 1 + 0.08 \cdot 2 + 0.03 \cdot 1 + 0.06 \cdot 2 + 0.04 \cdot 0 + 0.07 \cdot 1 + 0.02 \cdot 1 + 0.09 \cdot 2 + 0.05 \cdot 0 + 0.04 \cdot 1$$

$$\text{PRS} = 0.05 + 0.16 + 0.03 + 0.12 + 0 + 0.07 + 0.02 + 0.18 + 0 + 0.04 = 0.67$$

Total log odds for this individual: $\log(\text{OR}) = 0.67$

Odds ratio: $\text{OR} = e^{0.67} = 1.95$

**Interpretation**: This individual has **~2× elevated odds** of developing MDD compared to population mean. If population prevalence of MDD is 15%, this individual's age-adjusted lifetime risk would be approximately 25–30% (vs. 15% in the population). However, this is probabilistic: the score does not determine whether the person will develop MDD, only that genetic variants associated with increased risk are concentrated in their genome.

---

### Case Study 3: Linkage Disequilibrium Decay and SNP Selection for GWAS

**Scenario**: Two SNPs are separated by 5 kb of genomic distance. SNP-A has allele frequency $p_A = 0.30$; SNP-B has allele frequency $p_B = 0.25$. The observed haplotype frequency is $p_{AB} = 0.10$ (both risk alleles together).

**Calculate**: LD ($r^2$) between the SNPs; interpret whether SNP-B adds independent information beyond SNP-A for association testing.

**Solution**:

First, compute $D$:

$$D = p_{AB} - p_A \cdot p_B = 0.10 - (0.30 \times 0.25) = 0.10 - 0.075 = 0.025$$

Then compute $r^2$:

$$r^2 = \frac{D^2}{p_A(1-p_A) \cdot p_B(1-p_B)} = \frac{(0.025)^2}{0.30 \times 0.70 \times 0.25 \times 0.75}$$

$$r^2 = \frac{0.000625}{0.21 \times 0.1875} = \frac{0.000625}{0.039375} = 0.0159 \approx 0.016$$

**Interpretation**: $r^2 = 0.016$ indicates **essentially no LD** between these SNPs — they are in linkage equilibrium. SNP-B captures <2% of the haplotypic information at SNP-A. For GWAS design, both SNPs should be included independently, as they likely tag different causal variants (or one is on an independent haplotype background).

**Note on 5 kb distance**: 5 kb is relatively close, yet LD is minimal. This is consistent with recombination hotspots or ancient recombination events in Europeans, highlighting that LD extent is highly variable genome-wide and ancestry-dependent.

---

### Case Study 4: DNA Methylation Dynamics During Memory Formation

**Scenario**: Contextual fear conditioning induces rapid demethylation of the BDNF promoter in hippocampal neurons. Baseline methylation $m_0 = 55\%$; equilibrium (post-learning) methylation $m_{eq} = 35\%$; demethylation rate constant $k = 0.15$ per hour.

**Calculate**: BDNF methylation at 2 hours and 6 hours post-learning; interpret significance for memory consolidation.

**Solution**:

$$m(t) = m_{eq} + (m_0 - m_{eq}) \cdot e^{-kt}$$

**At $t = 2$ hours**:

$$m(2) = 35 + (55 - 35) \cdot e^{-0.15 \times 2} = 35 + 20 \cdot e^{-0.30}$$

$$m(2) = 35 + 20 \times 0.741 = 35 + 14.82 = 49.82\%$$

**At $t = 6$ hours**:

$$m(6) = 35 + (55 - 35) \cdot e^{-0.15 \times 6} = 35 + 20 \cdot e^{-0.90}$$

$$m(6) = 35 + 20 \times 0.407 = 35 + 8.14 = 43.14\%$$

**Interpretation**: Within 2 hours, methylation drops from 55% to ~50% (net 5% demethylation); by 6 hours, it reaches ~43% (net 12% demethylation). The equilibrium (35%) is approached asymptotically by ~18 hours ($t = 1/k \cdot \ln(2) \approx 4.6$ hours is the half-life of demethylation).

BDNF demethylation is necessary for robust histone acetylation and increased BDNF transcription → enhanced dendritic spine stability and memory consolidation. Blocking this epigenetic process (e.g., with HDAC inhibitors that prevent acetylation) impairs memory formation, demonstrating causal necessity.

---

### Case Study 5: CYP2C19 Polymorphism and SSRI Dosing in Escitalopram Treatment

**Scenario**: A patient prescribed escitalopram (CYP2C19 substrate) is genotyped as a poor metabolizer (PM) with CYP2C19 activity ~25% of normal metabolizers (EM). Standard escitalopram dosing is 10–20 mg daily (typical steady-state concentration ~30–80 ng/ml in EMs). Therapeutic window: 15–80 ng/ml; toxicity risk above 100 ng/ml.

**Calculate**: Steady-state concentration in this PM patient at standard dose vs. adjusted dose.

**Solution**:

Using the steady-state equation:

$$C_{ss} = \frac{F \cdot D}{CL \cdot \tau}$$

For an EM at standard 20 mg daily:

$$C_{ss,EM} = \frac{1.0 \times 20 \text{ mg}}{CL_{\text{normal}} \times 24 \text{ hours}} \approx 50 \text{ ng/ml (assumed typical)}$$

For a PM with $CL_{PM} = 0.25 \times CL_{EM}$:

$$C_{ss,PM} = \frac{1.0 \times 20 \text{ mg}}{0.25 \times CL_{\text{normal}} \times 24 \text{ hours}} = \frac{50 \text{ ng/ml}}{0.25} = 200 \text{ ng/ml}$$

**This exceeds the toxicity threshold** (>100 ng/ml).

**Adjusted dosing**: To target $C_{ss} \approx 50$ ng/ml (therapeutic):

$$D_{PM} = D_{EM} \times \frac{CL_{PM}}{CL_{EM}} = 20 \text{ mg} \times 0.25 = 5 \text{ mg daily}$$

**Interpretation**: A CYP2C19 PM should receive **5 mg daily** (instead of 20 mg) to achieve therapeutic concentrations without toxicity risk. Clinical outcomes: Non-genotyped PMs on standard doses may experience:
- Excessive sedation, nausea
- QT prolongation (escitalopram can prolong QTc interval at high concentrations)
- Serotonergic side effects (tremor, akathisia)

Pharmacogenomic testing and dose adjustment significantly improve tolerability and treatment adherence.

---

### Case Study 6: Gene-Environment Interaction in Schizophrenia Risk — Cannabis Use and COMT Genotype

**Scenario**: A large epidemiological study found that cannabis use during adolescence combined with COMT Val/Met genotype predicts schizophrenia risk:

| Genotype | No Cannabis Use | Regular Cannabis Use |
|---|---|---|
| Val/Val (high COMT, low PFC DA) | 1% lifetime risk | 4% lifetime risk |
| Val/Met (intermediate) | 1% lifetime risk | 7% lifetime risk |
| Met/Met (low COMT, high PFC DA) | 1.2% lifetime risk | 15% lifetime risk |

**Calculate**: The genetic main effect, environmental main effect, and interaction effect; interpret whether this represents diathesis-stress or differential susceptibility.

**Solution**:

Express as log-odds to simplify algebra. Use Val/Val + no cannabis as baseline ($\log(\text{OR}) = 0$).

| Genotype | No Cannabis | Cannabis | Difference (GxE?) |
|---|---|---|---|
| Val/Val | 0 | log(4) ≈ 0.60 | 0.60 |
| Val/Met | 0 | log(7) ≈ 0.95 | 0.95 |
| Met/Met | log(1.2) ≈ 0.18 | log(15) ≈ 2.71 | 2.53 |

Main effect of Met/Met genotype (no cannabis): 0.18

Main effect of cannabis (Val/Val baseline): 0.60

Interaction for Met/Met + Cannabis: 
- Additive prediction: 0.18 + 0.60 = 0.78
- Observed: 2.71
- Excess interaction: 2.71 − 0.78 = 1.93 (multiplicative/synergistic)

$$\text{Interaction ratio} = \frac{\text{Observed}}{\text{Additive}} = \frac{2.71}{0.78} \approx 3.5$$

**Interpretation**: The Met/Met genotype shows a **3.5× amplified risk** when combined with cannabis use — much greater than simple addition. This is a **diathesis-stress GxE**: the Met/Met genotype (genetic diathesis: elevated PFC dopamine from low COMT) becomes pathological only in the context of adolescent cannabis use (environmental stressor: further dopaminergic dysregulation via THC-CB1 signaling).

Mechanistically: Met/Met individuals have constitutively elevated PFC DA. Adolescent THC exposure:
1. Acutely increases dopamine release (especially in reward circuitry, less in PFC)
2. Causes chronic changes in CB1 signaling → altered DA regulation
3. In Met/Met individuals with already-elevated baseline DA, this creates excessive dopaminergic tone → psychotic symptoms

**Prevention implication**: Met/Met carriers counseled to avoid cannabis during adolescence; Val/Val carriers have much lower risk even with cannabis use, suggesting genotype-tailored prevention strategies.

---

## References

1. Falconer, D. S. (1965). The inheritance of liability to disease, with variable age of onset, with particular reference to diabetes mellitus. *Ann. Hum. Genet.*, 29, 51–76.

2. Bulik-Sullivan, B., Finucane, H. K., Anttila, V., Gusev, A., Day, F. R., Loh, P. R., ... & Neale, B. M. (2015). An atlas of genetic correlations across human diseases and traits. *Nat. Genet.*, 47(11), 1236–1241.

3. Hardy, G. H. (1908). Mendelian proportions in a mixed population. *Science*, 28(706), 49–50.

4. Lewontin, R. C., & Krakauer, J. (1973). Distribution of gene frequency as a test of the theory of the selective neutrality of polymorphisms. *Genetics*, 74, 175–195.

5. Sullivan, P. F., Neale, M. C., & Kendler, K. S. (2000). Genetic epidemiology of major depression: Review and meta-analysis. *Am. J. Psychiatry*, 157(10), 1552–1562.

6. International Schizophrenia Consortium (2009). Common polygenic variation and risk of schizophrenia. *Nature*, 460(7256), 748–752.

7. Reich, T. H., & Clayton, P. J. (1978). Family history studies: V. the genetics of mania. *Am. J. Psychiatry*, 125, 1358–1369.

8. Reich, D. E., & Lander, E. S. (2001). On the allelic spectrum of human disease. *Trends Genet.*, 17(9), 502–510.

9. Okbay, A., Beauchamp, J. P., Fontana, M. A., Lee, J. J., Pers, T. H., Rietveld, C. A., ... & Benjamin, D. J. (2016). Genome-wide association study identifies 74 loci associated with educational attainment. *Nature*, 533(7604), 539–542.

10. Autism Spectrum Disorders Working Group of The Psychiatric Genomics Consortium (2017). Meta-analysis of GWAS of over 16,000 individuals with autism spectrum disorder highlights a novel locus at 10q24.32. *Mol. Autism*, 8(1), 21.

11. Lee, S. H., Wray, N. R., Goddard, M. E., & Visscher, P. M. (2011). Estimating missing heritability for disease from genome-wide association studies. *Am. J. Hum. Genet.*, 88(3), 294–305.

12. Meaney, M. J., & Szyf, M. (2005). Environmental programming of stress responses through DNA methylation: life at the interface between a dynamic environment and a fixed genome. *Dialogues Clin. Neurosci.*, 7(2), 103.

13. Caspi, A., Sugden, K., Moffitt, T. E., Taylor, A., Craig, I. W., Harrington, H., ... & Poulton, R. (2003). Influence of life stress on depression: moderation by a polymorphism in the 5-HTT gene. *Science*, 301(5631), 386–389.

14. Caspi, A., McClay, J., Moffitt, T. E., Mill, J., Martin, J., Craig, I. W., ... & Poulton, R. (2002). Role of genotype in the cycle of violence in maltreated children. *Science*, 297(5582), 851–854.

15. Egan, M. F., Kojima, M., Callicott, J. H., Goldberg, T. E., Kolachana, B. S., Bertolino, A., ... & Weinberger, D. R. (2003). The BDNF val66met polymorphism affects activity-dependent secretion of BDNF and human memory and hippocampal function. *Cell*, 112(2), 257–269.

16. Friston, K. J., Holmes, A. P., Worsley, K. J., Poline, J. P., Frith, C. D., & Frackowiak, R. S. (1994). Statistical parametric maps in functional imaging: a general linear approach. *Hum. Brain Mapp.*, 2(4), 189–210.

17. Gershon, E. S., Hamovit, J., Guroff, J. J., Dibble, E., Leckman, J. F., Sceery, W., ... & Bunney, W. E. (1982). A family study of schizoaffective, bipolar I, bipolar II, unipolar, and normal control probands. *Arch. Gen. Psychiatry*, 39(10), 1157–1167.

18. Sullivan, P. F., Kendler, K. S., & Neale, M. C. (2000). Schizophrenia as a complex trait: evidence from a meta-analysis. *Arch. Gen. Psychiatry*, 57(12), 1141–1150.

19. Evans, D. M., Visscher, P. M., & Wray, N. R. (2009). Harnessing the power of large numbers of siblings in genetic research. *Nat. Rev. Genet.*, 10(11), 735–750.

20. Belsky, J., Bakermans-Kranenburg, M. J., & van IJzendoorn, M. H. (2007). For better and for worse: differential susceptibility to environmental influences. *Curr. Dir. Psychol. Sci.*, 16(6), 300–304.

21. Arseneault, L., Cannon, M., Poulton, R., Murray, R., Caspi, A., & Moffitt, T. E. (2002). Cannabis use in adolescence and risk for adult psychosis: longitudinal prospective study. *BMJ*, 325(7374), 1212–1213.

22. Fowler, J. S., Logan, J., Volkow, N. D., & Wang, G. J. (2003). Functional imaging and neurochemical markers of adolescent-onset schizophrenia. *Proc. Natl. Acad. Sci. USA*, 100(23), 13582–13587.

23. CPIC (Clinical Pharmacogenetics Implementation Consortium). (2021). Guideline for CYP2C19 genotype and citalopram/escitalopram dosing. *Clin. Pharmacol. Ther.*, 109(1), 42–47.

24. Weinshilboum, R. M., Otterness, D. M., & Szpirt, W. M. (1999). Methylation pharmacogenetics: catechol O-methyltransferase, thiopurine methyltransferase, and histamine N-methyltransferase. *Annu. Rev. Pharmacol. Toxicol.*, 39, 19–52.

25. Levran, O., Awolesi, O., Linzy, S., Adelson, M., Kreek, M. J., & Bart, G. (2013). DCTN4, GRK6, OPRD1, and OPRM1 gene variants in opioid addiction. *Drug Alcohol Depend.*, 112(1–2), 95–101.

---

*Next: [Chapter 17 — Frontier Neuroscience](../17_Frontier_Neuroscience/Frontier_Neuroscience.md)*
