# Hudanyun Sheng

Email: hudanyun.sheng@outlook.com  
Phone: (+86) 13683132915  
Website: https://danniesheng.github.io/  
Location: Beijing, China

## Summary

Applied AI Engineer and Data Scientist with experience designing and deploying product-oriented AI systems across healthcare, life sciences, and enterprise applications. Specialized in retrieval-augmented generation (RAG), document understanding, information retrieval, and machine learning pipelines, with a strong focus on building reliable, explainable, and maintainable AI solutions. Experienced in translating business and research problems into end-to-end AI products by integrating LLMs, classical machine learning, software engineering, and cloud-native data platforms. 

<!-- building machine learning, computer vision, and LLM-powered systems across healthcare, life sciences, and enterprise applications. Skilled in retrieval-augmented generation, information retrieval, multilingual NLP pipelines, data engineering, and end-to-end AI application development from data ingestion to deployment. -->

## Core Skills
- **Applied AI & LLM Systems**   
- Retrieval-Augmented Generation (RAG)
- Information Retrieval
- Embedding-based Search
- Cross-Encoder Reranking
- Prompt Engineering
- LLM Evaluation
- Document Understanding
- Human-in-the-loop AI Systems

- **Machine Learning:**   
- Classification
- Ranking
- Feature Engineering
- Computer Vision
- Weakly Supervised Learning

- **Data & Software Engineering:**   
- End-to-end AI Pipeline Design
- API Development
- Workflow Orchestration
- Data Validation
- Docker
- FastAPI
- Flask
- Git

- **Data Platforms & Cloud:**   
- Databricks
- Kedro
- Azure OpenAI
- OpenAI APIs
- SQL
- BigQuery
- Cloud-native ML Workflows

- ** Programming:**
- Python
- Pandas
- NumPy
- scikit-learn
- FAISS
- Hugging Face
- Streamlit

## Professional Experience

### Johnson & Johnson
**Data Scientist (Contractor)** | Center of Excellence
Beijing, China | April 2024 – Present

#### HCP–HCO Affiliation Verification | Document AI & Review System

- Developed a document understanding pipeline to extract physician information from hospital schedules in PDF and image formats, supporting HCP–HCO affiliation verification.
- Designed a cost-aware, multi-stage extraction pipeline using Camelot, OCR, and vision-based LLMs, with quality-based fallback to handle heterogeneous document formats.
- Implemented fault-tolerant batch processing to handle malformed PDFs, encoding errors, OCR failures, and oversized images without interrupting the pipeline.
- Built a Streamlit-based interface for reviewing and annotating consolidated extraction results.

#### HCP Knowledge Retrieval & Q&A | RAG Prototype

- Developed a RAG-based prototype for querying unstructured HCP-related information using E5 embeddings, FAISS vector search, and cross-encoder reranking.
- Implemented multilingual name normalization and fuzzy matching to support physician lookup across Japanese and Chinese naming conventions.
- Built a Streamlit interface for retrieval evaluation and evidence tracing, with modularized retrieval and LLM components.

<!-- #### Doctor Search & Medical RAG Assistant

- Designed and deployed a multilingual medical retrieval system supporting physician search and evidence-grounded question answering across Japanese healthcare data.
- Built a retrieval pipeline integrating dense embeddings, FAISS vector search, history-aware retrieval, cross-encoder reranking, and confidence-based response gating.
- Developed multilingual entity normalization workflows for Japanese, Chinese, and English physician names to improve retrieval robustness across heterogeneous data sources.
- Created interactive interfaces for retrieval parameter tuning, evidence tracing, and multi-turn dialogue evaluation. -->

#### Medical Content Governance | GenAI / RAG Proof of Concept

- Developed an LLM-assisted workflow to identify inconsistencies between localized Japanese medical FAQs and approved regulatory labels.
- Built retrieval and comparison pipelines combining document chunking, semantic search, structured prompting, and GPT-based reasoning to support scalable compliance review.
- Delivered a proof-of-concept solution with evidence-backed outputs to support human review of potentially non-compliant content.

#### Databricks Migration & Feature Store Integration

<!-- - Participated in migration from legacy ML pipelines to Databricks-based feature management workflows.
- Supported feature standardization and reusable feature architecture to improve maintainability and model development efficiency. -->
- Contributed to a cross-team initiative to migrate existing Kedro-based ML pipelines to Databricks.
- Developed a reusable utility for writing feature tables to Databricks Feature Store, supporting configurable primary keys and optional timestamp columns.

#### Commercial ML System for Drug Launch & HCP Targeting 

- Developed machine learning models to predict potential early adopters of newly launched pharmaceutical products using HCP profiles, HCO attributes, and historical sales of analogous drugs.
- Engineered features incorporating internal HCP ratings and historical commercial data to support physician prioritization for drug launch planning.
- Implemented modular Kedro-based data pipelines with validation and reproducibility controls.
- Collaborated with commercial stakeholders to translate predictive outputs into actionable HCP targeting insights.

#### HCP Drug Preference Segmentation | Unsupervised Learning
- Applied unsupervised learning to segment HCPs into preferrer, non-preferrer, and undetermined groups using historical data.
- Delivered segmentation insights that received positive feedback from business stakeholders and were presented to senior leadership.





### Zenni Optical

**Data Scientist, AI/ML Department**  
Beijing, China  
Jun 2023 – Jan 2024

#### Prescription (Rx) Recognition System
- Built FastAPI-based inference service to extract structured optical parameters (sphere, cylinder, axis) from user-uploaded images.
- Integrated OCR outputs with rule-based and heuristic post-processing.
- Adapted parsing logic for Japanese prescription formats to support multilingual layout variation.
- Integrated CloudSQL and BigQuery for monitoring and multi-region usage analytics.

<!-- #### Blur Detection and Quality Monitoring
- Analyzed API usage logs and image quality metrics. -->

#### Human-in-the-Loop Evaluation & Quality Diagnostics
- Built internal Streamlit tool to visualize OCR and extraction outputs for rapid debugging.
- Analyzed API logs and user behavior to diagnose extraction failures related to image quality and capture issues.


### University of Texas Southwestern Medical Center
**Data Scientist, Quantitative Biomedical Research Center**  
Dallas, TX, USA  
Sep 2021 – May 2023

#### CyTOF Image Analysis Toolkit

- Designed end-to-end pipeline integrating multiplexed imaging with single-cell expression data.
- Built Flask-based service with Dockerized deployment and parallelized computation.
- Achieved approximately 10× runtime speed-up for large-scale experiments.

#### Digital Pathology: Nuclei Segmentation & Classification

- Developed Mask R-CNN–based pipeline for nuclei segmentation and 6-class classification on H&E slides.
- Customized loss functions for partially labeled data, recovering approximately 20% of training samples.
- Achieved 82.5% detection and 82.0% classification performance under weak supervision.


<!-- #### EHR De-identification and NLP Pipeline
- Built workflows for anonymizing and preprocessing EHR data. -->

### Donald Danforth Plant Science Center
**Data Science Researcher, Data Science Facility**  
St. Louis, MO, USA  
Feb 2020 – Sep 2021

#### Multimodal Imaging & Analysis Systems for Plant Phenotyping (open-source software)

- Built automated pipelines for large-scale multimodal plant imaging (RGB, thermal, hyperspectral).
- Developed instance-level segmentation and temporal tracking workflows for growth analysis.
- Contributed to the open-source PlantCV project (modules, tests, documentation, community support).
- Supported interdisciplinary teams with reproducible analysis and visualization.


### University of Florida Academic Health Center
**Data Science Intern**  
Gainesville, FL, USA  
May 2019 – Aug 2019
- Processed and cleaned patient vital-sign time-series data.
- Extracted predictive features and evaluated clustering methods.
- Reproduced interpolation-based models for irregular clinical data.

## Selected AI Projects

### AI News Agent

LLM-based News Summarization and QA Assistant

Open-source project for daily AI news aggregation, summarization, and question answering.

- Designed and implemented an end-to-end LLM-powered news agent for daily AI news aggregation, summarization, and question answering.
- Built a lightweight RAG pipeline integrating web scraping, local embedding models, hybrid retrieval, and OpenAI APIs.
- Implemented scheduled crawling, automatic topic tagging, and corpus-based QA over historical news data.
- Developed interactive Streamlit front-end and deployed on Hugging Face Spaces.
- Explored Docker-based deployment and embedding model switching.

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