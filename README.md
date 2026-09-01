# LC-MS/MS Comparative Metabolomics Portfolio Report
**Metabolic Reprogramming of HCT-116 Colorectal Carcinoma Cells Under Hypoxic & Anoxic Microenvironments**  
*Study Reference: Metabolomics Workbench ST004105 (Analysis AN006807)*

---

## 1. Executive Summary
This study investigates the phenotypic and metabolic adaptations of human HCT-116 colorectal carcinoma cells exposed to gradient oxygen deprivation: **Normoxia**, **Hypoxia**, and **Anoxia**. Using dual-fraction (aqueous/polar and organic/lipophilic) LC-MS/MS profiling across 60 biological runs (105 annotated metabolites), this project defines key bioenergetic, redox, and lipidomic alterations driving cell survival under oxygen restriction.

---

## 2. Dataset Architecture & Preprocessing
* **Sample Stratification:** 60 total LC-MS/MS runs across 2 extraction phases (30 Aqueous, 30 Organic; $n=10$ biological replicates per condition).
* **Metabolite Coverage:** 105 annotated metabolites spanning central carbon pathways, nucleosides/nucleotides, amino acids, acylcarnitines, sphingolipids, and fatty acids.
* **Preprocessing Pipeline:** Half-minimum non-detect imputation, generalized $\log_{10}$ variance stabilization, and Pareto scaling ($(\bar{x} - \mu)/\sqrt{\sigma}$).

---

## 3. Quantitative Aqueous Biomarkers (One-Way ANOVA & FDR)

| Metabolite | Normoxia (Mean ± SD) | Hypoxia (Mean ± SD) | Anoxia (Mean ± SD) | $F$-statistic | $p$-value (FDR) |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Reduced Glutathione (GSH)** | $593,849 \pm 246,802$ | $60,661 \pm 38,065$ | $91,143 \pm 14,354$ | 44.82 | $< 0.0001$ (***) |
| **$5'$-Methylthioadenosine (MTA)** | $40,820 \pm 30,782$ | $241,595 \pm 234,449$ | $587,349 \pm 129,552$ | 33.15 | $< 0.0001$ (***) |
| **$\gamma$-Glutamylcysteine** | $12,912 \pm 4,360$ | $3,640 \pm 2,986$ | $1,972 \pm 360$ | 39.41 | $< 0.0001$ (***) |
| **L-Acetylcarnitine** | $161,283 \pm 65,064$ | $134,163 \pm 52,260$ | $319,290 \pm 73,439$ | 27.94 | $< 0.0001$ (***) |
| **Adenosine Triphosphate (ATP)** | $10,487 \pm 7,370$ | $2,940 \pm 1,372$ | $3,914 \pm 345$ | 6.83 | $0.0041$ (**) |
| **Adenosine Monophosphate (AMP)** | $20,818 \pm 9,569$ | $9,108 \pm 4,008$ | $15,936 \pm 1,940$ | 7.41 | $0.0028$ (**) |
| **Pantothenic Acid** | $74,709 \pm 31,988$ | $48,817 \pm 30,474$ | $67,737 \pm 12,058$ | 1.80 | $0.1870$ (NS) |

---

## 4. Organic Fraction & Lipid Remodeling

| Metabolite | Normoxia (Mean ± SD) | Hypoxia (Mean ± SD) | Anoxia (Mean ± SD) | $F$-statistic | $p$-value (FDR) |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Sphinganine** | $81,392 \pm 123,016$ | $9,985 \pm 14,038$ | $74,544 \pm 19,002$ | 3.58 | $0.0423$ (*) |
| **Nutriacholic acid** | $108,829 \pm 113,446$ | $23,732 \pm 22,868$ | $206,897 \pm 114,357$ | 11.14 | $0.0003$ (***) |
| **Traumatic acid** | $5,128 \pm 1,324$ | $5,673 \pm 849$ | $4,589 \pm 958$ | 2.59 | $0.0938$ (NS) |
| **17-Hydroxyprogesterone** | $1,719 \pm 175$ | $1,699 \pm 222$ | $1,809 \pm 187$ | 0.98 | $0.3882$ (NS) |

---

## 5. Mechanistic Biological Findings
* **Glutathione Redox Collapse:** Reduced glutathione (GSH) and $\gamma$-glutamylcysteine drop by $>6.5\times$ under oxygen deprivation ($p < 0.0001$), indicating severe thiol exhaustion and $\gamma$-glutamyl resynthesis cycle failure.
* **MTA Salvage Arrest:** $5'$-Methylthioadenosine surges $14.4\times$ in complete anoxia, reflecting strong downstream inhibition of MTA phosphorylase (MTAP) and polyamine salvage.
* **Mitochondrial Acyl Shunting:** L-Acetylcarnitine accumulates significantly under anoxia ($+1.98\times$), marking export of excess acetyl units due to electron transport chain arrest.
* **Adenylate Energy Depletion:** Active ATP pools collapse by $>60\%$, accompanied by purine degradation turnover.

---

## 6. Supervised Machine Learning & VIP Ranking
Partial Least Squares Discriminant Analysis (PLS-DA) performed on the aqueous metabolome ($R^2Y = 0.94, Q^2 = 0.88$) identified the top Variable Importance in Projection (VIP) candidate biomarkers:
1. **$5'$-MTA** ($\text{VIP} = 2.18$)
2. **Reduced Glutathione** ($\text{VIP} = 1.94$)
3. **$\gamma$-Glutamylcysteine** ($\text{VIP} = 1.86$)
4. **L-Acetylcarnitine** ($\text{VIP} = 1.72$)
5. **Adenosine Triphosphate** ($\text{VIP} = 1.58$)

---

## 7. Repository Files
* `MSdata_ST004105_AN006807.txt`: Full raw experimental LC-MS/MS dataset (60 sample runs).
* `ST004105_Metabolomics_Portfolio_Report.pdf`: Downloadable full compiled PDF report.
