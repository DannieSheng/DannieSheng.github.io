# Hudanyun (Dannie) Sheng

Beijing, China | [LinkedIn](https://cn.linkedin.com/in/hudanyunsheng) | [Portfolio](https://danniesheng.github.io/)

## Research Profile

Data scientist with research experience in computer vision and machine learning for digital pathology and plant phenotyping. Developed and evaluated models for partially labeled histology data, contributed to open-source scientific software, and built deployable systems for biomedical imaging and document understanding.

## Research Experience

### UT Southwestern Medical Center · Data Scientist
Quantitative Biomedical Research Center | Dallas, TX | Sep 2021 – May 2023

- Developed a Mask R-CNN pipeline to segment nuclei and classify them into six cell types in H&E-stained tissue. Modified the loss function and training strategy to use partially annotated samples, recovering approximately 20% of the training data.
- Evaluated the weakly supervised pipeline, achieving an 82.5% detection rate and 82.0% classification accuracy. Co-authored the resulting study in *Modern Pathology*.
- Designed a system that combined spatial imaging with single-cell CyTOF expression profiles. Implemented parallel processing in a Dockerized Flask service, achieving roughly 10× faster processing than the baseline workflow.

### Donald Danforth Plant Science Center · Data Science Researcher
Data Science Facility | St. Louis, MO | Feb 2020 – Sep 2021

- Developed leaf instance segmentation and time-series tracking workflows to quantify plant growth.
- Automated processing and visualization of RGB, thermal, and hyperspectral images to support reproducible analyses with plant scientists.
- Contributed Python modules, tests, documentation, and community training to [PlantCV](https://plantcv.org/), an open-source toolkit for plant image analysis.

## Selected Publications

### Published

- Rong R, **Sheng H**, Jin KW, et al. [A Deep Learning Approach for Histology-Based Nucleus Segmentation and Tumor Microenvironment Characterization](https://utsouthwestern.elsevierpure.com/en/publications/a-deep-learning-approach-for-histology-based-nucleus-segmentation/). *Modern Pathology*. 2023;36(8):100196.
- Schuhl H, Brown KE, **Sheng H**, et al. [PlantCV v4: Image analysis software for high-throughput plant phenotyping](https://doi.org/10.1002/ppj2.70065). *The Plant Phenome Journal*. 2026;9:e70065.
- Yu G, Zare A, **Sheng H**, et al. Root identification in minirhizotron imagery with multiple instance learning. *Machine Vision and Applications*. 2020;31.

### Preprint

- **Sheng H**, Gutierrez J, Schuhl H, et al. Increasing the Throughput of Annotation Tasks Across Scales of Plant Phenotyping Experiments. *Authorea Preprints*. 2023.

### Submitted Manuscript

- “MultiTAP: Multiplexed Tissue Analysis Platform, an open-sourced and Python-based software for analyzing multiplexed tissue images.” Manuscript submitted to *Briefings in Bioinformatics*, 2026.

## Applied Machine Learning Experience

### Johnson & Johnson · Data Scientist
Center of Excellence | Beijing, China | Apr 2024 – Present

- **Document AI.** Designed a pipeline to extract hospital schedules from digital, scanned, and malformed PDFs. Combined Camelot, OCR-based table detection, and LLM-based image reasoning with quality checks and fallback logic. Built a reviewer interface for batch validation and annotation.
- **Healthcare professional (HCP) segmentation and prioritization.** Built models to identify likely early adopters for new drug launches using historical sales, promotion, and HCP interaction data. Developed feature engineering and ranking workflows in Kedro to support reproducible validation and handoff.

### Zenni Optical · Data Scientist, AI/ML Department
Beijing, China | Jun 2023 – Jan 2024

- Deployed a FastAPI service that extracted structured optical parameters from prescription images using OCR and rule-based parsing. Adapted the parser to Japanese prescription formats.
- Analyzed OCR failures using service logs and built an internal Streamlit tool for manual validation and error review.

## Education

- **University of Florida** · M.S., Electrical and Computer Engineering, 2019. Thesis on switchgrass genotype classification using hyperspectral imagery.
- **University of Florida** · M.S., Industrial and Systems Engineering, 2017.
- **Tongji University** · B.S., Science and Technology of Optical Information, 2015.

## Technical Skills

- **Research methods** · Weak supervision, instance segmentation, image classification, feature engineering, model evaluation, error analysis
- **Programming and tools** · Python, NumPy, pandas, scikit-learn, Flask, FastAPI, Docker, Kedro, Databricks, Streamlit
