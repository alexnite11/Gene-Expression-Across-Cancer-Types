# Gene Expression Across Cancer Types: Variability, Co‑Expression, and Network Behavior  
**Author:** Alex Nite  
**Dataset:** TCGA Pan‑Cancer (via Kaggle subset)

---

##  Project Overview
This project analyzes gene expression patterns across five cancer types—BRCA, COAD, KIRC, LUAD, and PRAD—using a randomly sampled subset of genes from the TCGA Pan‑Cancer dataset. The goal was to understand:

- Which genes are consistently **highly expressed**  
- Which genes show **high variability**  
- Which genes act as **network‑central regulators**  
- How gene relationships differ **across cancer types**  

By examining expression levels, variability, and correlation‑based gene networks, the project highlights genes that may play important biological roles in cancer behavior.

---

##  Dataset
- Source: TCGA Pan‑Cancer RNA‑Seq (via Nyantudre, 2025 on Kaggle)  
- 801 tumor samples  
- 5 cancer types: **BRCA, COAD, KIRC, LUAD, PRAD**  
- 20,000+ genes originally → reduced to 15 randomly sampled genes for visualization clarity  

---

##  Methods & Analysis

### **1. Sample‑Wide Gene Expression**
- G2452, G2362, G3427 → **highest expression**  
- G2359, G2361, G2421 → **lowest expression**  
- G61 → **most variable gene** across all samples  
- G1, G2452 → **most stable genes**  

### **2. Expression by Cancer Type**
- G2452 consistently highly expressed in **BRCA, COAD, LUAD, PRAD**  
- KIRC differs slightly: **G2362 > G2452**  
- G61 remains the **most variable** gene in every cancer  
- PRAD shows **low expression + low variability**  
- LUAD and BRCA show **high expression + high variability**  

### **3. Sample‑Wide Gene Correlation**
- Strong positive pairs:  
  - **G1–G2** (r ≈ 0.53)  
  - **G3–G3427** (r ≈ 0.42)  
- Strong negative pairs:  
  - **G2362–G3427** (r ≈ –0.38)  
  - **G2–G61** (r ≈ –0.25)  
- **G3** emerges as a **central hub gene**  
- **G2359** remains largely independent  

### **4. Correlation Networks by Cancer Type**
- **BRCA:** G1–G2 strongest pair; G3427 most central  
- **COAD:** G2452–G61 strongest pair; G3 most connected  
- **KIRC:** G59–G60 strongest pair; G59 most central  
- **LUAD:** G1–G2 strongest pair; G3427 strongest negative regulator  
- **PRAD:** G1–G2 strongest pair; G1 most central  

---

##  Key Findings
- **G2452 and G2362** are consistently high‑expression genes across cancers  
- **G61** is the most variable gene, suggesting sensitivity to tumor environment  
- **G1–G2** form a stable co‑expression module across all cancer types  
- **G3 and G3427** frequently act as network hubs or regulatory nodes  
- Some genes (e.g., **G2359**) remain independent, showing minimal co‑expression  

These patterns align with known cancer biology: highly expressed or highly connected genes often play essential roles in tumor growth, signaling, or metabolic pathways.

---

## Challenges
- Small gene subset limits detection of broader network structure  
- Outliers (e.g., G2361) influence correlation strength  
- Tableau required reshaping and pre‑computing correlations in Python  
- Wide‑to‑long transformations were necessary for cancer‑specific visualizations  

---

##  Future Work
- Expand analysis to full 20,000+ gene set  
- Apply clustering (k‑means, hierarchical) to identify gene modules  
- Use network centrality metrics (degree, betweenness, eigenvector)  
- Integrate pathway enrichment analysis (KEGG, GO)  
- Explore differential expression between cancer types  

---

