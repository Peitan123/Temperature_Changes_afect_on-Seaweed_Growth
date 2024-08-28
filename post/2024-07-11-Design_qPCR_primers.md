# Investigating the Effects of Climate Change on Fucus vesiculosus Using qPCR Analysis

## Introduction

Climate change is profoundly impacting marine ecosystems, with rising temperatures, changing salinity levels, and increasing concentrations of atmospheric CO2 leading to ocean acidification. These environmental stressors can significantly affect the physiological and biochemical processes of marine organisms, including seaweeds. In this study, we aim to investigate the molecular responses of *Fucus vesiculosus* to these stressors by focusing on the expression of the **rbcL** gene.

### Why Choose rbcL as a Target Gene?

The **rbcL** gene encodes the large subunit of Rubisco (ribulose-1,5-bisphosphate carboxylase/oxygenase), a critical enzyme in the Calvin cycle of photosynthesis. Rubisco is responsible for carbon fixation, making it essential for the growth and survival of photosynthetic organisms. Given its central role in photosynthesis, **rbcL** expression is likely to be sensitive to environmental changes that affect the photosynthetic efficiency of *Fucus vesiculosus*.

### Reference Genes

For accurate normalization of qPCR data, it is essential to select stable reference genes. In this study, we chose the following reference genes:

- **EF1α (Elongation Factor 1-alpha):** Involved in the elongation phase of protein synthesis, EF1α is frequently used as a reference gene due to its consistent expression under different conditions.
- **ACT (Actin):** A structural protein involved in cell motility, structure, and integrity, known for its stable expression, making it a reliable reference gene for normalization.

## Experiment

### Stress/Conditions to Test Against

To assess the impact of climate change-related stressors on **rbcL** expression, we will expose *Fucus vesiculosus* to the following conditions:

1. **Control Conditions:**
   - Temperature: 15°C
   - Salinity: 23 psu
   - pCO2: 400 µatm

2. **Increased Temperature:**
   - Temperature: 20°C
   - Salinity: 23 psu
   - pCO2: 400 µatm

3. **Decreased Salinity:**
   - Temperature: 15°C
   - Salinity: 19 psu
   - pCO2: 400 µatm

4. **Elevated pCO2:**
   - Temperature: 15°C
   - Salinity: 23 psu
   - pCO2: 1100 µatm

5. **Combined Stressors:**
   - Temperature: 20°C
   - Salinity: 19 psu
   - pCO2: 1100 µatm

### Methodology

1. **Sample Collection and RNA Extraction:**
   - Collect seaweed samples at the end of the growth experiment.
   - Isolate total RNA from newly grown seaweed tissue using a suitable RNA extraction kit.

2. **cDNA Synthesis:**
   - Synthesize cDNA from the isolated RNA using a reverse transcription kit.

3. **Primer Design:**
   - Design specific primers for **rbcL** and the selected reference genes (EF1α, ACT).

4. **qPCR Analysis:**
   - Perform qPCR using a reliable qPCR machine.
   - Normalize the expression levels of **rbcL** to the selected reference genes.

5. **Data Analysis:**
   - Calculate the relative expression levels of **rbcL** using the ΔΔCt method.
   - Analyze the data using appropriate statistical methods to determine the effects of the different treatments on gene expression.

### primer design process

1. Identify the Gene sequence: 

    the gen sequence we want to PCR is
     
- \>DQ307680.1 Fucus vesiculosus ribulose 1,5-bisphosphate carboxylase/oxygenase large subunit (rbcL) gene, complete cds; chloroplast
ATGCCTGAGAACGTACAGGAAAGAACTCGATTAAAAAGTGAGCGTTATGAATCTGGTGTAATCCCATATG
CTAAAATGGGATATTGGGATGCAGATTACAACGTTAAAGATACTGATATTCTAGCTCTATTTCGTATAAC
TCCACAACCAGGTGTAGATCCTGTGGAAGCTGCTGCTGCTGTTGCTGGTGAATCTTCAACTGCAACGTGG
ACAGTAGTATGGACAGATTTACTAACTGCTTGTGACATCTACCGAGCGAAAGCATATCGTGTGGATCCTG
TTCCAGGAACAAATGATCAATATTTTGCATACATTGCTTATGAATGTGATTTATTTGAAGAAGGTTCTCT
TGCTAACTTAACCGCATCTATCATTGGTAATGTATTTGGTTTTAAAGCTGTTAAAGCATTACGTTTAGAA
GATATGAGGATTCCTTACGCTTACCTAAAAACTTTCCAGGGTCCTGCTACAGGTGTAATTGTAGAACGAG
AAAGATTAGATAAATTTGGACGTCCTTTATTAGGAGCTACTGTAAAACCTAAATTAGGTCTTTCAGGTAA
AAACTATGGGCGTGTTGTTTATGAAGGTTTAACAGGTGGTCTTGATTTTCTTAAAGATGATGAAAATATT
AATTCACAACCTTTCATGCGTTGGAAAGAACGTTTCTTATATTGTATGGAAGGTGTTAACCGTGCTGCTG
CTGCAACTGGTGAAGTTAAAGGTTCTTATCTTAATGTTACCGCAGCAACAATGGAAAATATGTATGAACG
TGCTGAATACTCTCATGCTATCGGTAGTGTAATTTGTATGATTGATTTAGTTGTTGGTTATACAGCAATT
CAAAGTATGGCTATTTGGGCACGAAAAGCTGAAATGATTTTGCATTTACATCGTGCAGGAAATTCTACAT
ATGCCCGTCAAAAAAACCATGGTATTAATTTCCGAGTTATTTGTAAATGGATGCGTATGTGTGGTGTAGA
TCATATTCATGCTGGTACAGTTGTTGGAAAATTAGAAGGTGATCCTTTAATGGTTAAAGGTTTCTATAAC
ACACTATTATTAACAGAGCTAAAAATTAATTTAGCAGAAGGTTTGTTCTTCGATATGGATTGGGCATCTC
TTAGAAAATGTGTTCCTGTAGCTTCTGGTGGTATTCATTGTGGTCAAATGCATCAACTTCTTTACTATTT
AGGTGATGATGTAGTTCTACAATTTGGTGGTGGTACAATCGGTCACCCTGATGGTATACAAGCAGGCGCT
ACAGCGAATCGTGTTGCGTTAGAAGCTATGGTTTTAGCTCGTAATGAAGGTCGTGATTATGTTGGTGAAG
GTCCTGAAATTTTACGTACAGCTGCTAGTACTTGTGGACCATTAAAAGCAGCTTTAGATTTATGGAAAGA
TATTACTTTTGAATATACTTCAACAGATACACCTGATTTCACTGAAGTGGCAACTGAAAGTAACTAA

2. Set Parameters and Identify the Target Region:
    - **Primer Length:** 18-24 nucleotides
    - **GC Content:** 40-60%
    - **Melting Temperature (Tm):** 58-62°C
    - **Amplicon Length:** ~150 bp
        
        Select a region within the provided rbcL sequence that is suitable for qPCR amplification, typically ~150 base pairs (bp) long.
3. Run Primer3:
    - The software will generate a list of potential primer pairs

    **Forward Primer:**
        5'-AGCTGTTAAAGCATTACGTTT-3' 

    **Reverse Primer:**
        5'-GATGAAGGTCGTGATTATGTTG-3'

## Hypothesis

We hypothesize that the expression levels of **rbcL** will vary significantly under different environmental stressors:

1. **Increased Temperature:**
   - **Downregulation:** Elevated temperatures may impair the photosynthetic machinery, leading to a decrease in **rbcL** expression due to reduced Rubisco efficiency.

2. **Decreased Salinity:**
   - **Variable Response:** Osmotic stress from lower salinity could lead to oxidative stress, potentially downregulating **rbcL** expression if photosynthetic efficiency is compromised. Conversely, some seaweeds may upregulate **rbcL** to maintain photosynthesis under mild osmotic stress.

3. **Elevated pCO2:**
   - **Upregulation:** Increased pCO2 levels can enhance carbon availability for photosynthesis, potentially leading to an upregulation of **rbcL** as the plant increases its photosynthetic activity.

4. **Combined Stressors:**
   - **Complex Interactions:** The combined effects of increased temperature, decreased salinity, and elevated pCO2 can lead to complex interactions affecting **rbcL** expression. While elevated pCO2 may upregulate **rbcL**, the simultaneous stress from increased temperature and decreased salinity might mitigate this effect, resulting in a net decrease or no significant change in expression.



