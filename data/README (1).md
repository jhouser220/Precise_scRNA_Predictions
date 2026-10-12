# Data

**No data is hosted in this repository.** All datasets come from published studies and are
available from the repositories listed below. Download each one and place it in the folder
shown. The `data/` folder is listed in `.gitignore`, so nothing here is tracked by git.

Please cite the original studies if you use these datasets, and check each repository's terms
of use.



## Summary

| Dataset | Cancer type | Treatment | Comparison used for "response" | Source | Access |
|---|---|---|---|---|---|
| GSE120575 | Melanoma | Checkpoint inhibitors (anti-PD-1 / anti-CTLA-4) | Responders vs non-responders | GEO | Public |
| Bassez et al. 2021 | Breast cancer | Anti-PD-1 (pembrolizumab) | Responders vs non-responders | GEO | Public |
| GSE235923 | Pediatric AML | Chemotherapy | Relapse vs continuous complete remission (CCR) | GEO | Public (processed data only) |

---

## 1. GSE120575: melanoma, checkpoint immunotherapy

- **Study:** Sade-Feldman M, et al. "Defining T cell states associated with response to
  checkpoint immunotherapy in melanoma." *Cell* (2018). DOI: `10.1016/j.cell.2018.10.038`
- **Accession:** GEO [GSE120575](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE120575)
  (also listed on [OmicsDI](https://www.omicsdi.org/dataset/geo/GSE120575))
- **Access:** Public
- **Description:** 16,291 immune cells from 48 tumor samples of melanoma patients treated with
  checkpoint inhibitors, profiled by single-cell transcriptomics.
- **Files used:** TODO (e.g. the expression matrix and the patient/sample annotation file
  from the GEO supplementary files)
- **Timepoint used:** All/pretreatment only
- **Preprocessing:** see `notebooks/01_run_precise_GSE120575.ipynb`

## 2. Bassez et al.: breast cancer, anti-PD-1

- **Study:** Bassez A, et al. "A single-cell map of intratumoral changes during anti-PD1
  treatment of patients with breast cancer." *Nature Medicine* 27, 820-832 (2021).
  DOI: `10.1038/s41591-021-01323-8`. PubMed: <https://pubmed.ncbi.nlm.nih.gov/33958794/>
- **Accession / download:** https://cellxgene.cziscience.com/collections/61e422dd-c9cd-460e-9b91-72d9517348ef
- **Access:** public
- **Description:** Patients with early breast cancer (hormone receptor-positive or
  triple-negative) received one dose of anti-PD-1 (pembrolizumab; n = 29), or neoadjuvant
  chemotherapy followed by anti-PD-1 (n = 11), approximately 10 days before surgery. Paired
  pre-treatment and on-treatment biopsies were profiled with single-cell transcriptome and TCR
  sequencing.
- **Cohort used:** pre-treatment
- **Preprocessing:** see `notebooks/02_run_precise_Bassez_BC.ipynb`

## 3. GSE235923: pediatric acute myeloid leukemia

- **Study:** Thomas BE, et al. "Single-cell analysis reveals altered tumor microenvironments of
  relapse- and remission-associated pediatric acute myeloid leukemia." (2023).
  GEO lists the associated publications as PubMed
  [37798266](https://www.ncbi.nlm.nih.gov/pubmed/37798266),
  [39703843](https://www.ncbi.nlm.nih.gov/pubmed/39703843) and
  [40316535](https://www.ncbi.nlm.nih.gov/pubmed/40316535).
- **Accession:** GEO
  [GSE235923](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE235923) (BioProject
  PRJNA988040)
- **Access:** Public. Only processed data are provided (`GSE235923_RAW.tar`, MTX/TSV files);
  the authors state that raw sequencing data are not included because of patient privacy
  concerns.
- **Description:** Cryopreserved bone marrow samples from pediatric AML patients at diagnosis
  (Dx), end of induction (EOI), and relapse, profiled with 10x Genomics 3' scRNA-seq on an
  Illumina NovaSeq 6000. 31 samples from 20 patients.
- **Timepoint used:** diagnosis only
- **Preprocessing:** see `notebooks/03_run_precise_GSE235923.ipynb`

---

## Reproducing the data setup

1. Download each dataset from the sources above into `data/raw/<dataset>/`.
2. Run the notebooks in `notebooks/` in order. Each `01`-`03` notebook reads from
   `data/raw/` and writes a processed `.h5ad` file to `data/processed/`.


## Notes on reuse

- Processed per-cell or per-patient outputs from controlled-access data may not be
  redistributable. Check the terms for each dataset before committing anything derived from
  it to `results/`. Summary statistics, AUCs and figures are generally fine.
