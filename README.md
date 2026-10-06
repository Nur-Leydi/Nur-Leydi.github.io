# Nur-Lady.github.io

# Nurhan Arslan

Guest Researcher, Methods in Medical Informatics, Department of Computer Science, University of Tübingen

PhD in Computer Science, University of Tübingen, 2026

📧 nurhan.arslan@uni-tuebingen.de

---

I build machine learning and statistical models on real-world biomedical data — patient-level clinical records, viral sequences, and next-generation sequencing data. My doctoral work covered three projects in infectious disease: predicting multidrug resistance in HIV before it emerges, to support earlier detection and treatment adjustment; detecting a hepatitis C recombinant variant that standard genotyping misclassifies; and modelling HLA-driven immune escape in HIV.

These projects were carried out in collaboration with the University Clinic of Cologne, the EuResist Network, and Medizinisches Infektiologiezentrum Berlin, and supported by DZIF, ViiV Healthcare, and the Cluster of Excellence.

## Research

Across three doctoral projects, the central challenge was learning from limited data. High-dimensional, low-sample-size (HDLSS) settings, class imbalance, heterogeneous multi-source data, irregularly sampled longitudinal data, and biological variability require careful choices in data representation, model selection, and evaluation. My thesis, *Machine Learning Solutions for Small Data Prediction Problems in Virology*, addresses these constraints with a focus on generalisation and interpretability.

### Predicting multidrug resistance in HIV

Resistance to all four major antiretroviral drug classes is rare, but when it occurs it sharply narrows treatment options and can be life-threatening, particularly where access to resistance testing and newer drugs is limited. Anticipating it before it emerges could support earlier treatment decisions. We built classifiers that predict its future emergence from patient viral sequences, using the EuResist Integrated Database — one of the largest repositories of HIV genotypes and treatment responses, drawing on data from multiple European database providers.

Like most clinical data, these records are irregular in time: patients are sequenced at different frequencies and intervals, yet training requires one sequence per patient, so there is no consistent way to select an "earlier" sample. To address this, we introduced a sliding time anchor: for an anchor placed a fixed time before the first observation of four-class resistance, each patient contributes the sequence closest to that anchor. Moving the anchor further back retains every patient while increasing the average time between sample and outcome, so we can assess how far in advance four-class resistance can be reliably predicted.

Besides prediction time, we also varied the resistance level of the comparison group, from no resistance up to resistance against three classes. Prediction remained feasible even in the hardest setting — distinguishing patients who would go on to develop four-class resistance from those already resistant to three — though accuracy decreased as the anchor moved further back. Feature-importance analysis showed that the models relied on known drug resistance mutations in the easier settings, but on new mutations in the hardest one — suggesting that previously unrecognised mutations may play a role in the development of four-class resistance.

*With the University Clinic of Cologne, ViiV Healthcare, and the EuResist Network.*

### Detecting a misclassified hepatitis C variant

The hepatitis C 2k/1b variant is a recombinant of genotypes 2k and 1b. Most commercial genotyping assays examine the 5′ untranslated region or core of the HCV genome. In the 2k/1b recombinant the breakpoint lies in NS2, so these regions come from genotype 2 and the variant is typically reported as genotype 2. However, the targets of direct-acting antivirals — NS3, NS5A, and NS5B — descend from genotype 1b, so the variant should be treated as genotype 1b, which matters especially when non-pan-genotypic drug combinations are used. Whole-genome sequencing would resolve this but is costly and less accessible, while standard genotyping remains widely used, particularly in resource-limited settings. Accurate detection also matters for tracking transmission and migration-associated spread, including migration from Ukraine.

We trained machine learning models to identify the 2k/1b variant from partial sequences of the routinely sequenced NS3 and NS5A regions, showing that misclassification can be reduced without whole-genome sequencing. The models are available in [geno2pheno[HCV]](https://hcv.geno2pheno.org/), a freely accessible web tool, and could support treatment decisions where sequencing resources are limited, as well as epidemiological studies. Because confirmed 2k/1b sequences are still scarce, the models were trained on limited data, and their performance is expected to improve as more sequences become available.

*With the University Clinic of Cologne and Medizinisches Infektiologiezentrum Berlin.*

### HLA-driven immune escape in HIV

HLA class I genes are the strongest known host genetic factor in HIV-1 control. The immune pressure they exert leaves recurrent escape mutations in the virus — HLA footprints — which are linked to viral replication and disease progression and are relevant to vaccine development and clinical interpretation. Detecting them reliably in population-level sequence data is difficult because of extensive HLA polymorphism, high viral sequence diversity, and shared ancestry among viral isolates.

This ongoing project develops statistical methods for more reliable HLA footprint detection, with the aim of extending the set of known HLA footprints.

### Beyond virology

I have also worked with multi-omics data in oncology, co-supervising a Master's project applying TabPFN to integrative prognostication in low-grade glioma. During my MSc in electrical and electronics engineering, I worked on multicolour flow cytometry, where fluorescent dyes emit overlapping spectra, so each detector also records signal from neighbouring dyes. Compensation algorithms correct for this spillover, but evaluating them requires data in which the true signal is known — something real measurements cannot provide. I built a simulation of the full measurement chain, from cells and fluorescence emission through the optics to the detector electronics, to generate realistic two-colour reference datasets with known ground truth for evaluating linear compensation algorithms.

## Publications

**HIV multidrug class resistance prediction with a time sliding anchor approach**
Arslan N., Eggeling R., Reuter B., Van Laethem K., Pingarilho M., Gomes P., Sönnerborg A., Kaiser R., Zazzi M., Pfeifer N.
*Bioinformatics Advances* 5(1), vbaf099, 2025. [doi:10.1093/bioadv/vbaf099](https://doi.org/10.1093/bioadv/vbaf099)

**Hepatitis C virus Saint Petersburg variant detection with machine learning methods**
Arslan N., Reuter B., Buech J., Lengauer T., Obermeier M., Kaiser R., Pfeifer N.
*Journal of Medical Virology* 97(2), e70169, 2025. [doi:10.1002/jmv.70169](https://doi.org/10.1002/jmv.70169)

## Talks and teaching

- HIV multidrug class resistance prediction — TüBMI, 2024
- HCV Saint Petersburg variant prediction with machine learning methods — AREVIR Meeting, 2023
- Co-supervision of a Master's research project, University of Tübingen, 2025–2026
- Research and Teaching Assistant, Izmir Institute of Technology, 2013–2016

## Skills

Python, scikit-learn, PyTorch, TensorFlow, pandas, SQL, MATLAB, C/C++, HPC with Slurm and Bash

## Code and data

These studies were conducted on restricted clinical datasets, most notably the EuResist Integrated Database, which cannot be redistributed under the terms of the relevant data use agreements and ethics approvals. Access to the EIDB may be requested through the EuResist Network.
