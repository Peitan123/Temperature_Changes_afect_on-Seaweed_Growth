# Report on GNPS Analysis of Antimycin A Molecular Network

## 1. Introduction
Global Natural Products Social Molecular Networking or GNPS is an open-access platform that enables researchers to analyze mass spectrometry data, particularly for natural products. The platform allows users to create molecular networks based on the similarity of MS/MS fragmentation patterns, which helps in identifying and characterizing compounds in complex mixtures. GNPS is widely used in fields such as metabolomics, natural product discovery, and environmental chemistry.

to get a fath and hands on anderstanding of the platform we generate a molecular network according to the website tutorial and explored it

## 2. Methodology and Workflow
- **Job Link:** [Hyperlink to the GNPS job](https://gnps.ucsd.edu/ProteoSAFe/status.jsp?task=e755dfc6a6024997b96b8cb1b13413df).
- **Workflow Used:** We explore the molecular family of [Antimycin A](https://gnps.ucsd.edu/ProteoSAFe/result.jsp?view=network_displayer&componentindex=24&highlight_node=2250&task=e755dfc6a6024997b96b8cb1b13413df#%7B%7D)
    - Analyze the neutral losses between the two compounds
    - Compare the spectra of the two compounds

## 3. Results and Analysis
### 3.1 Molecular Network Generation
this is the brad look of are network
![coverage in relation to site and depth](/images/antimycin_famely.png)

### 3.2 Neutral Losses Exploration
We explored the loss between Antimycin A3-CDM-BAW and its clos compared ass seen below 
![loss](/resolts/gnps/neutral_loss.png)
the loss is 42.046. this loss was anilised with UNIMOD ![UNIMOD RESOLTS](/resolts/gnps/unimod_neutral_loss.png) the resolts show that a positive difference of 42.046 can acer from tri-Methylation, Gly->Val substitution, Propyl or Ala->Leu/Ile substitution.

### 3.3 Spectra of Two Compounds Compered
We father on wen and compered thos two compards spectra 
![sectram comperesen](/resolts/gnps/spectra_dif.png) Both spectra show peaks in the low to mid-mass range (50-300 m/z), which are indicative of fragment ions produced during MS/MS analysis.
The top spectrum has several prominent peaks, especially around 100, 150, 200, and 250 m/z, which are likely key fragment ions for Antimycin A3.
The bottom spectrum also has peaks around the same m/z values but differs in intensity and distribution. The retention time for the top compound is 603.79 seconds, while the bottom compound has a retention time of 586.69 seconds. The slight difference in retention time suggests that these compounds are similar but they are likely a different molecule, even if related


## 4. Conclusion
This study successfully used the GNPS platform to generate a molecular network and explore the Antimycin A family. We identified a significant mass difference of 42.046 Da between Antimycin A3-CDM-BAW and a related compound, suggesting possible biochemical modifications like tri-Methylation or amino acid substitutions.

The spectral comparison showed similar fragmentation patterns, but differences in intensity and retention time suggest that the compounds, while related, are distinct. This exercise provided valuable insights into using GNPS for distinguishing closely related molecules and sets the stage for further research on the molecular impacts of environmental changes on marine organisms.

## 5. Future Work
- **Next Steps:** In our research proposal, we aim to investigate the effects of climate change on the growth of seaweed. Utilizing this tool, we can also identify how climate change impacts the molecular composition of seaweed. This analysis will help us understand the biochemical changes that occur in response to environmental stressors, such as temperature fluctuations and ocean acidification. Additionally, we plan to extend this research to explore the potential implications for marine ecosystems and the broader implications for natural product discovery from marine sources