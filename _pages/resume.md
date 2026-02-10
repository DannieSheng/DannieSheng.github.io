---
layout: archive
title: "Resume"
permalink: /resume/
author_profile: true
redirect_from:
  - /Resume
---
{% include base_path %}

[查看中文简历]({{ site.baseurl }}/resume-cn/)  
[Download My Resume](/files/HudanyunSheng_CV.pdf)

## Professional Summary
Data Scientist with experience building end-to-end machine learning and GenAI systems across healthcare, medical imaging, and applied AI products.
Skilled in translating ambiguous problem statements into production-ready pipelines spanning data ingestion, modeling, retrieval, and human-in-the-loop workflows.
Hands-on experience with LLM-based RAG systems, computer vision for medical and document imaging, and scalable ML infrastructure in regulated environments.
Currently focused on robust GenAI system design, evaluation, and deployment in real-world settings.

--- 

## Core Skills

### Machine Learning & GenAI
- Classical ML: classification, ranking, feature engineering, model evaluation  
- GenAI systems: Retrieval-Augmented Generation (RAG), prompt engineering, LLM evaluation  
- Embedding-based retrieval, cross-encoder reranking, uncertainty handling  
- Human-in-the-loop ML and AI-assisted review workflows  

### Data & System Engineering
- End-to-end ML / GenAI pipeline design with quality gating and fallback strategies  
- Noisy document understanding: PDF parsing, OCR, table extraction, image-based reasoning  
- Failure-aware system design for malformed inputs, encoding issues, and partial outputs  

### Platform & Cloud
- Databricks-based ML workflows and feature pipelines  
- Containerized deployment with Docker  
- Azure-based ML / LLM platforms in regulated environments  
- Cloud-native data workflows and monitoring  

### Tools & Stack
- Python, Pandas, NumPy, scikit-learn  
- FAISS, Hugging Face (E5 embeddings, rerankers)  
- OpenAI / Azure OpenAI APIs  
- Kedro, Streamlit  

---

## Professional Experience

### Johnson & Johnson | Data Scientist (Contractor)  
Center of Excellence, Beijing, China | Apr 2024 – Present

System-oriented Data Scientist working on **ML and GenAI systems** for commercial and medical use cases under strict compliance and data-quality constraints.

#### Commercial ML Systems for Drug Launch & HCP Targeting
- Built and maintained ML models for early adopter identification in new drug launches using historical sales, promotion, and HCP interaction data  
- Designed feature engineering and ranking pipelines to support large-scale HCP prioritization under business and compliance constraints  
- Implemented modular data pipelines using Kedro, improving validation, reproducibility, and cross-team handoff  

#### GenAI / RAG Systems for Medical Content Governance
- Designed RAG workflows to detect off-label or non-compliant content by comparing localized medical FAQs with regulatory drug labels (Japanese market)  
- Led prompt design, retrieval strategy selection, and error analysis for ambiguous translations and partial semantic matches  
- Built quality-gated fallback strategies combining rule-based checks, embedding retrieval, and LLM reasoning  

#### Medical Knowledge Retrieval & Doctor Lookup Platform
- Designed and deployed a Japanese medical RAG system using FAISS + multilingual E5 embeddings, history-aware retrieval, and cross-encoder reranking  
- Built robust JP/CN name normalization and fuzzy matching pipelines across writing systems  
- Developed a Streamlit-based UI for retrieval tuning, evidence tracing, and multi-turn dialogue logging  

#### Document Understanding & PDF Table Extraction Systems
- Designed a robust pipeline for extracting hospital schedule tables from heterogeneous PDFs (digital, scanned, malformed)  
- Integrated Camelot, OCR-based table detection, and LLM-based image reasoning with quality gating and fallback logic  
- Built reviewer-facing UI for inspection, annotation, and batch validation  
- Implemented failure-aware handling for encoding issues, broken PDFs, OCR degradation, and oversized images  

#### Data Platform & Infrastructure Contributions
- Participated in migration of ML workflows to Databricks, supporting feature storage and transformation redesign  
- Ensured alignment with platform constraints and compliance requirements  

---

### Zenni Optical | Data Scientist, AI/ML Department  
Beijing, China | Jun 2023 – Jan 2024

#### Prescription Understanding & Recognition System
- Designed and deployed a prescription (Rx) recognition service extracting structured optical parameters from user-uploaded images  
- Built a FastAPI-based inference service integrating OCR outputs with rule-based and heuristic post-processing  
- Adapted parsing logic for Japanese prescription formats, improving accuracy across multilingual and layout-diverse inputs  
- Integrated CloudSQL and BigQuery for usage tracking and monitoring  

#### Image Quality Analysis & Human-in-the-Loop Tooling
- Investigated image quality issues affecting OCR and extraction reliability  
- Analyzed API logs and user behavior to identify degradation patterns  
- Built an internal Streamlit-based review tool to support error analysis and manual validation  

### University of Texas Southwestern Medical Center | Data Scientist  
Quantitative Biomedical Research Center  
Dallas, TX, USA | Sep 2021 – May 2023

#### Integrated Imaging & Biomedical Data Systems
- Designed and implemented an image analysis system integrating spatial imaging data with single-cell CyTOF expression profiles  
- Built a Flask-based service with parallelized processing and Dockerized deployment  
- Achieved ~10× runtime speed-up over baseline pipelines  

#### Cell Segmentation & Classification in Digital Pathology
- Developed a Mask R-CNN pipeline for nuclei segmentation and 6-class classification in H&E pathology slides  
- Customized loss functions to handle partially labeled datasets, recovering ~20% of training data  
- Achieved 82.5% detection and 82.0% classification accuracy  

#### Clinical Text Processing Support (Supporting Role)
- Assisted with integrating existing EHR de-identification and preprocessing tools into research workflows  


### Donald Danforth Plant Science Center | Data Science Researcher  
Data Science Facility  
St. Louis, MO, USA | Feb 2020 – Sep 2021

- Built automated pipelines for RGB, thermal, and hyperspectral plant imaging data  
- Developed instance-level segmentation and temporal tracking workflows for leaf growth analysis  
- Contributed to the open-source PlantCV project (modules, tests, documentation, training)  
- Supported interdisciplinary teams with reproducible analysis and visualization  

### University of Florida Academic Health Center | Data Science Intern  
Precision and Intelligent Systems in Medicine Partnership Lab  
Gainesville, FL, USA | May 2019 – Aug 2019

- Processed patient vital-sign time-series data for early risk modeling  
- Engineered 24-hour post-admission feature sets  
- Reproduced interpolation-based models for irregular clinical time-series  

---

## Personal Projects

### AI News Agent – LLM-based News Summarization & QA
- Designed and developed an LLM-based AI news agent for daily aggregation, summarization, and question answering  
- Built a lightweight RAG pipeline combining web-scraped sources, local embedding models, and OpenAI APIs  
- Implemented scheduled crawling, automatic topic tagging, and category-based summarization  
- Enabled user question answering over the news corpus via hybrid retrieval  
- Developed Streamlit front-end; deployed on Hugging Face Spaces; explored Docker-based deployment  

---

## Education

**University of Florida**  
- M.S. Electrical & Computer Engineering (GPA: 3.86/4), 2019  
  *Thesis: Switchgrass Genotype Classification using Hyperspectral Imagery*  

- M.S. Industrial & Systems Engineering (GPA: 3.87/4), 2017  

**Tongji University**  
- B.S. Physics (GPA: 4.45/5), 2015  
  *Thesis: Correction of Intensity Unevenness in X-Ray KB Imaging*  

---

## Professional Strengths

- **System Thinker:** Focus on robustness, failure handling, and end-to-end design  
- **Fast Learner:** Rapidly onboard to new domains and technologies  
- **Communicator:** Translate complex systems for technical and non-technical audiences  
- **Cross-cultural Collaboration:** Bilingual in English and Chinese with US–China experience  

---

<!-- Publications
======
  <ul>{% for post in site.publications reversed %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul> -->
## Publications
*(Selected publications related to machine learning, imaging, and data systems)*

<ul>
  {% for post in site.publications reversed %}
    {% include archive-single-cv.html %}
  {% endfor %}
</ul>
---

## Service and leadership
* Co-Chair of the Committee for Scientific Training and Mentoring at Donald Danforth Plant Science Center

---

## Certificates, Honors, and Rewards 
* 1st Place of the “Swarm Behavior on the Grid” track in the Siemens "Tech for Sustainability Campaign 2023” (2023)
* Google Data Analytics Certificate– a rigorous, hands-on program that covers the entire scope of the data analysis process
* 2nd Prize Tongji University Undergraduate Innovation Program (2014)
* National Endeavor Scholarship (2014)
* 2nd Prize, Tongji University Scholarship of Excellence (2014)