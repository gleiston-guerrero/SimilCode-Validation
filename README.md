# SimilCode-Validation

[![License: CC BY 4.0](https://img.shields.io/badge/License-CC_BY_4.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.21284183.svg)](https://doi.org/10.5281/zenodo.21284183)

Companion validation repository for the **SimilCode** study, containing the blank data-collection instruments (informed-consent forms and the structured 18-item questionnaire) together with the anonymised responses of the five-expert content-validity panel that evaluated the integrated SimilCode web application.

This repository is a companion to the manuscript submitted to the *International Journal for Educational Integrity* (Springer Nature) and to the following software and dataset artefacts:

| Companion artefact | Repository | DOI |
|---|---|---|
| Benchmark dataset | [`gleiston-guerrero/SimilCode-Benchmark`](https://github.com/gleiston-guerrero/SimilCode-Benchmark) | [10.5281/zenodo.21271491](https://doi.org/10.5281/zenodo.21271491) |
| Backend service   | [`gleiston-guerrero/BackEnd-SimilCode`](https://github.com/gleiston-guerrero/BackEnd-SimilCode) | [10.5281/zenodo.21265177](https://doi.org/10.5281/zenodo.21265177) |
| Frontend client   | [`gleiston-guerrero/FrontEnd-SimilCode`](https://github.com/gleiston-guerrero/FrontEnd-SimilCode) | [10.5281/zenodo.21265976](https://doi.org/10.5281/zenodo.21265976) |

---

## Repository structure

```
SimilCode-Validation/
├── README.md
├── LICENSE                                              # CC BY 4.0
├── CITATION.cff                                         # Citation metadata (CFF v1.2.0)
├── CHANGELOG.md
├── instrument/                                          # Blank data-collection instruments
│   ├── Consentimiento_Entrevista_TEMPLATE_es.pdf              (Spanish, 2025)
│   ├── Consentimiento_Validacion_SimilCode_TEMPLATE_es.pdf    (Spanish, 2026)
│   ├── Encuesta_Utilidad_Precision_TEMPLATE_es.pdf            (Spanish, 18-item questionnaire)
│   ├── Informed_Consent_Interview_TEMPLATE_en.pdf             (English translation)
│   ├── Informed_Consent_Validation_SimilCode_TEMPLATE_en.pdf  (English translation)
│   └── Survey_Usefulness_Accuracy_TEMPLATE_en.pdf             (English translation)
└── responses/                                           # Anonymised expert responses
    ├── respuestas_encuesta_similcode_wide.csv                 (5 rows × 22 columns)
    ├── respuestas_encuesta_similcode_long.csv                 (90 rows: 5 experts × 18 items)
    └── variables_codebook.csv                                 (Bilingual variable dictionary)
```

## Overview

The dataset in this repository supports the **expert-validation phase** of the SimilCode study: a content-validity exercise conducted with five experienced programming instructors from the Faculty of Computer Sciences at Universidad Técnica Estatal de Quevedo (UTEQ), Ecuador. The five-expert sample size aligns with the recommended range for content-validity studies with substantive-domain experts (Galicia Alarcón et al., 2017).

Each expert:

1. Attended a system demonstration (10 min).
2. Interacted hands-on with ten code pairs in C\# and Java covering different similarity categories (20 min).
3. Completed a structured 18-item questionnaire on a 5-point Likert scale (Kusmaryono et al., 2022) covering practical usefulness, accuracy of results, and comprehensibility of justifications.

The 18 items are organised in three sections:

| Section | Focus | Items |
|---|---|---|
| A | Practical usefulness | Q01–Q07 |
| B | Accuracy of results  | Q08–Q13 |
| C | Comprehensibility of justifications | Q14–Q18 |

## Contents

### `instrument/`

Blank templates of every data-collection instrument used with the expert panel, provided in Spanish (the language of administration) and English (translated for international audiences). All personal-data fields (name, national ID, phone, email, signature, date, years of experience, subjects taught, mastered languages, Likert marks) appear empty:

- **`Consentimiento_Entrevista_TEMPLATE_es.pdf`** / **`Informed_Consent_Interview_TEMPLATE_en.pdf`** — Informed consent used in the exploratory-interview phase (2025), during requirements elicitation.
- **`Consentimiento_Validacion_SimilCode_TEMPLATE_es.pdf`** / **`Informed_Consent_Validation_SimilCode_TEMPLATE_en.pdf`** — Informed consent used in the SimilCode validation phase (2026).
- **`Encuesta_Utilidad_Precision_TEMPLATE_es.pdf`** / **`Survey_Usefulness_Accuracy_TEMPLATE_en.pdf`** — The full 18-item validation questionnaire (Likert 1–5).

### `responses/`

- **`respuestas_encuesta_similcode_wide.csv`** — One row per participant (P01–P05); columns for four non-identifying demographic covariates (years of teaching experience — raw and numeric, subjects taught, programming languages mastered) followed by the 18 Likert items. Suitable for direct import into SPSS, R, or `pandas`; convenient format for computing descriptive statistics and Cronbach's alpha.
- **`respuestas_encuesta_similcode_long.csv`** — Tidy long format with 90 rows (5 participants × 18 items); suitable for `dplyr`/`tidyverse` or `pandas` group-by analyses.
- **`variables_codebook.csv`** — Bilingual variable dictionary. Column identifiers (e.g. `A_Q01_utilidad_deteccion_similitudes`, `B_Q08_precision_puntajes_vs_experto`) are preserved in Spanish for traceability with the source data, while descriptions and permitted values are provided in English.

## Privacy and ethics

- The study was conducted in accordance with the institutional ethical research guidelines of Universidad Técnica Estatal de Quevedo. All five participants provided **written informed consent** before the validation session.
- All raw response documents were anonymised prior to inclusion in this repository: names, national ID numbers (cédula), email addresses, phone numbers, handwritten signatures, exact dates of participation, and any other free-text identifiers were removed; participants are represented only by the codes `P01`–`P05`.
- The **blank** consent forms in `instrument/` do not contain personal data.
- No student-submitted code was used in this validation exercise; the code pairs shown to experts were drawn from the SimilCode benchmark corpus (see companion repository `SimilCode-Benchmark`).

## How to cite

If you use this dataset, please cite:

> Guerrero-Ulloa, G.C., Navas Rivera, R.A., Díaz-Macías, E., Hornos, M.J., & Rodríguez-Domínguez, C. (2026). *SimilCode-Validation: Expert-panel instruments and anonymised responses for the content-validity study of the SimilCode tool* (v1.0.0) [Data set]. Zenodo. https://doi.org/10.5281/zenodo.21284183

And the associated paper:

> Guerrero-Ulloa, G.C., Navas Rivera, R.A., Díaz-Macías, E., Hornos, M.J., & Rodríguez-Domínguez, C. (2026). SimilCode: A Web Application for Source Code Similarity Detection and Algorithmic Efficiency Analysis using Generative Artificial Intelligence. *International Journal for Educational Integrity*. [DOI pending]

A machine-readable `CITATION.cff` file is provided in the root of this repository.

## Authors

| # | Author | Affiliation | ORCID |
|---|---|---|---|
| 1 | Gleiston Cicerón Guerrero-Ulloa | Faculty of Computer Sciences, Universidad Técnica Estatal de Quevedo (UTEQ), Quevedo, Los Ríos, Ecuador | [0000-0001-5990-2357](https://orcid.org/0000-0001-5990-2357) |
| 2 | Rafael Alexander Navas Rivera | Faculty of Computer Sciences, Universidad Técnica Estatal de Quevedo (UTEQ), Quevedo, Los Ríos, Ecuador | [0009-0005-7926-2648](https://orcid.org/0009-0005-7926-2648) |
| 3 | Efraín Díaz-Macías | Faculty of Computer Sciences, Universidad Técnica Estatal de Quevedo (UTEQ), Quevedo, Los Ríos, Ecuador | [0000-0003-4087-029X](https://orcid.org/0000-0003-4087-029X) |
| 4 | Miguel J. Hornos | Department of Software Engineering, University of Granada (UGR), Granada, Spain | [0000-0001-5722-9816](https://orcid.org/0000-0001-5722-9816) |
| 5 | Carlos Rodríguez-Domínguez *(corresponding author)* | Department of Software Engineering, and Research Center for Information and Communication Technologies (CITIC), University of Granada (UGR), Granada, Spain | [0000-0001-5626-3115](https://orcid.org/0000-0001-5626-3115) |

**Corresponding author:** Carlos Rodríguez-Domínguez — `carlosrodriguez@ugr.es`

## Acknowledgements

The authors thank the five expert instructors of the Faculty of Computer Sciences at Universidad Técnica Estatal de Quevedo for their time and expertise during the validation phase, and acknowledge the institutional support of UTEQ throughout the development of this work.

## License

This dataset is released under the **Creative Commons Attribution 4.0 International License (CC BY 4.0)**. See [`LICENSE`](./LICENSE) for the full text. You are free to share and adapt the material provided you give appropriate credit as indicated in the "How to cite" section above.

## References

- Galicia Alarcón, L.A., Balderrama Trápaga, J.A., & Edel Navarro, R. (2017). Content validity by experts judgment: Proposal for a virtual tool. *Apertura*, 9(2), 42–53. https://doi.org/10.32870/Ap.v9n2.993
- Kusmaryono, I., Wijayanti, D., & Maharani, H.R. (2022). Number of Response Options, Reliability, Validity, and Potential Bias in the Use of the Likert Scale Education and Social Science Research: A Literature Review. *International Journal of Educational Methodology*, 8(4), 625–637. https://doi.org/10.12973/ijem.8.4.625
