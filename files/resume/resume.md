# Hudanyun Sheng

Email: hudanyun.sheng@outlook.com  
Phone: (+86) 13683132915  
Website: https://danniesheng.github.io/  
Location: Beijing, China

<!-- ## Summary

Data Scientist and Applied AI Engineer with experience building machine learning, computer vision, and LLM-powered systems across healthcare, life sciences, and enterprise applications. Skilled in retrieval-augmented generation, information retrieval, multilingual NLP pipelines, data engineering, and end-to-end AI application development from data ingestion to deployment. -->

## Technical Skills
- **Machine Learning & GenAI:**   
classical ML (classification, ranking, feature engineering), Retrieval-Augmented Generation
(RAG), prompt engineering, LLM evaluation, embedding-based retrieval, cross-encoder reranking, uncertainty handling

- **Data & System Engineering:**   
end-to-end ML / GenAI pipeline design with quality gating and fallback strategies, noisy
document understanding (PDF parsing, OCR, table extraction), human-in-the-loop systems for review, validation, and
error correction

- **Platform & Cloud:**   
Databricks-based ML workflows and feature pipelines, containerized deployment with Docker,
Azure-based ML / LLM platforms in regulated environments, cloud-native data workflows

- **Tools & Stack:**   
Python, Pandas, NumPy, scikit-learn, FAISS, Hugging Face (E5 embeddings, rerankers), OpenAI / Azure
OpenAI APIs. Kedro, Streamlit

## Professional Experience

### Johnson & Johnson
**Data Scientist, Contractor** | Center of Excellence
Beijing, China | April 2024 – Present

#### Commercial ML System for Drug Launch & HCP Targeting 
- Developed machine learning models to identify high-potential healthcare professionals likely to adopt newly launched products.
- Designed feature engineering and scoring pipelines to support large-scale prioritization under business constraints.
- Implemented modular Kedro-based data pipelines with validation and reproducibility controls.
- Collaborated with commercial stakeholders to translate predictive outputs into targeting strategies.


#### Doctor Lookup & Q&A System (Japanese Medical RAG)
- Designed and deployed a Japanese medical RAG system integrating FAISS, E5 embeddings, history-aware retrieval chains, cross-encoder reranking, and uncertainty gating.
- Built multilingual name normalization and fuzzy-matching pipelines.
- Developed an interactive UI for retrieval tuning and evidence tracing.
- Modularized retriever and LLM components with Dockerized deployment.

#### Doctor Search & Medical RAG Assistant

- Designed and deployed a multilingual medical retrieval system supporting physician search and evidence-grounded question answering across Japanese healthcare data.
- Built a retrieval pipeline integrating dense embeddings, FAISS vector search, history-aware retrieval, cross-encoder reranking, and confidence-based response gating.
- Developed multilingual entity normalization workflows for Japanese, Chinese, and English physician names to improve retrieval robustness across heterogeneous data sources.
- Created interactive interfaces for retrieval parameter tuning, evidence tracing, and multi-turn dialogue evaluation.

#### Regulatory FAQ Compliance Review System

- Developed an LLM-assisted workflow to identify inconsistencies between localized Japanese medical FAQs and approved regulatory labels.
- Built retrieval and comparison pipelines combining document chunking, semantic search, and GPT-based reasoning to support scalable compliance review.
- Generated evidence-backed outputs to support human validation and reduce manual review burden.


#### Feature Store Migration and Optimization

- Participated in migration from legacy ML pipelines to Databricks-based feature management workflows.
- Supported feature standardization and reusable feature architecture to improve maintainability and model development efficiency.

### Zenni Optical

**Data Scientist, AI/ML Department**  
Beijing, China  
Jun 2023 – Jan 2024

#### Prescription Recognition API
- Built FastAPI services for extracting structured prescription information from images.
- Adapted parsing logic for Japanese prescription formats.

#### Blur Detection and Quality Monitoring
- Analyzed API usage logs and image quality metrics.

### Interactive Evaluation Interface
- Built Streamlit-based tools for OCR result visualization and validation.

### University of Texas Southwestern Medical Center
**Data Scientist, Quantitative Biomedical Research Center**  
Dallas, TX, USA  
Sep 2021 – May 2023

#### CyTOF Image Analysis Toolkit
- Designed and developed a Flask-based image analysis package integrating spatial and single-cell expression data.
- Achieved 10× processing speed improvements through parallelization and Docker deployment.

#### Cell Segmentation in H&E Pathology Slides
- Implemented Mask R-CNN for nuclei segmentation and classification.
- Customized loss functions to recover partially labeled training samples.

#### EHR De-identification and NLP Pipeline
- Built workflows for anonymizing and preprocessing EHR data.

### Donald Danforth Plant Science Center
**Data Science Researcher, Data Science Facility**  
St. Louis, MO, USA  
Feb 2020 – Sep 2021

#### Multimodal Plant Image Analysis Pipeline
- Built automated pipelines for RGB, thermal, and hyperspectral data processing.

#### Instance Segmentation and Growth Tracking
- Developed instance-level segmentation and tracking systems.

#### Open-source Development (PlantCV)
- Contributed image analysis modules, tests, documentation, and training materials.

### University of Florida Academic Health Center
**Data Science Intern**  
Gainesville, FL, USA  
May 2019 – Aug 2019
- Processed and cleaned patient vital-sign time-series data.
- Extracted predictive features and evaluated clustering methods.
- Reproduced interpolation-based models for irregular clinical data.

## Selected AI Projects

### AI News Agent

* Built a lightweight AI news assistant for daily AI news aggregation, summarization, semantic search, and question answering.
* Implemented a retrieval-augmented generation pipeline combining scraped news, local embedding models, and OpenAI LLMs.
* Developed scheduled scraping, auto-tagging, category filtering, and interactive QA through a Streamlit interface.

## Education

### University of Florida
M.S. in Electrical and Computer Engineering, GPA: 3.86/4
December 2019.  
**Master Thesis**: Switchgrass Genotype Classification using Hyperspectral Imagery

### University of Florida
M.S. in Industrial and Systems Engineering, GPA: 3.87/4
December 2017

### Tongji University
B.S. in Physics, GPA: 4.45/5
June 2015.  
**Bachelor Thesis**: The Correction of the Intensity Unevenness of X-Ray KB Imaging

## Publications
- Sheng, H., Wang S., et al. “MTIA: An open-source python package for systematic multiplexed tissue image analysis” (in preparation)
- Sheng, H., Gutierrez, J., Schuhl, H., Murphy, K. M., Acosta-Gamboa, L., Gehan, M., & Fahlgren, N. (2023). Increasing the Throughput of Annotation Tasks Across Scales of Plant Phenotyping Experiments.
- Rong, R., Sheng, H., Jin, K.W., Wu, F., Luo, D., Wen, Z., Tang, C., Yang, D.M., Jia, L., Amgad, M., & Cooper, L.A. (2023). A deep learning approach for histology-based nucleus segmentation and tumor microenvironment characterization. Modern Pathology.

## Awards & Leadership
- 1st Place, Siemens Tech for Sustainability Campaign (2023)
- Google Data Analytics Certificate
- Co-Chair, Committee for Scientific Training and Mentoring, Donald Danforth Plant Science Center