---
layout: archive
title: "简历"
permalink: /resume-cn/
author_profile: true
redirect_from:
  - /resume-cn
lang: zh-CN
---

{% include base_path %}
[View English Resume]({{ site.baseurl }}/resume/)  
[下载我的简历](/files/盛胡丹筠简历.pdf)

## 个人简介

系统型数据科学家，具备 **机器学习（ML）与生成式 AI（GenAI）系统的端到端设计与落地经验**，长期从事医疗、生命科学及企业级 AI 应用相关工作。

研究与工程并重，擅长在**真实业务约束**下构建可用系统，包括：  
- 数据质量不稳定  
- 文档格式复杂（PDF / 扫描件 / OCR）  
- 多语言与合规要求  
- 需要人工参与（human-in-the-loop）的审核与修正流程  

关注点不局限于模型性能，而是 **系统鲁棒性、可解释性、失败兜底与工程可维护性**。

---

## 核心能力

### 机器学习 & 生成式 AI
- 传统机器学习：分类、排序、特征工程、模型评估  
- 生成式 AI 系统：RAG（检索增强生成）、Prompt 设计、LLM 评估  
- 向量检索、Cross-encoder 重排序、不确定性与置信度处理  
- Human-in-the-loop AI 系统设计  

### 数据与系统工程
- 端到端 ML / GenAI Pipeline 设计（质量校验 + fallback 机制）  
- 非结构化文档理解：PDF 解析、OCR、表格抽取、图像推理  
- 面向失败的系统设计（编码错误、破损文件、OCR 退化等）  

### 平台与云环境
- Databricks 上的 ML 工作流与特征流水线  
- Docker 容器化部署  
- 合规环境下的 Azure / Azure OpenAI 平台  
- 云原生数据处理与监控  

### 技术栈
- Python, Pandas, NumPy, scikit-learn  
- FAISS, Hugging Face（E5 embedding, reranker）  
- OpenAI / Azure OpenAI API  
- Kedro, Streamlit  

---

## 工作经历

---

### Johnson & Johnson | 数据科学家（外包）  
Center of Excellence，北京 | 2024.04 – 至今

面向商业与医学场景，参与 **机器学习与生成式 AI 系统的设计、原型构建与平台化落地**，工作环境具有严格的合规与数据质量约束。

#### 新药上市与 HCP 目标识别（商业 ML 系统）
- 基于历史销售、推广及医生行为数据，构建新药上市早期采用者识别模型  
- 设计特征工程与评分流水线，用于大规模医生排序与优先级推荐  
- 使用 Kedro 构建模块化数据流水线，提升数据校验、可复现性与跨团队交付能力  

#### 医学内容合规检查（GenAI / RAG）
- 设计 RAG 工作流，用于比对本地化医学 FAQ 与药品说明书，识别潜在 off-label 或不合规内容（日本市场）  
- 主导 Prompt 设计、检索策略选择及错误分析，应对翻译歧义与部分语义匹配问题  
- 构建结合规则、向量检索与 LLM 推理的多级兜底机制，降低误报率  

#### 医学知识检索与医生查询平台
- 构建日文医学 RAG 系统，集成 FAISS + 多语言 E5 embedding、历史感知检索与 cross-encoder 重排序  
- 实现中日文姓名标准化与模糊匹配（NFKC、假名–罗马字、简繁转换），提升跨书写体系召回率  
- 开发 Streamlit UI，用于参数调优、证据溯源与多轮对话记录，支持技术与非技术用户  

#### 医院排班表 PDF 抽取与审核系统
- 设计鲁棒的医院排班表抽取系统，支持电子 PDF、扫描件及格式异常文档  
- 集成 Camelot、OCR 表格检测与 LLM 图像推理，多策略协同并带质量校验  
- 构建 reviewer UI，支持批量检查、标注与人工修正  
- 系统性处理编码异常、破损 PDF、OCR 退化与超大图像等失败场景，避免 pipeline 中断  

#### 平台与基础设施
- 参与 ML 流水线向 Databricks 平台迁移  
- 协同数据工程团队调整特征存储与转换逻辑，确保合规与平台一致性  

### Zenni Optical | 数据科学家（AI / ML）  
北京 | 2023.06 – 2024.01

#### 眼镜处方理解与识别系统
- 设计并实现处方识别服务，从用户上传图片中提取球镜、柱镜、轴位等结构化参数  
- 构建基于 FastAPI 的推理服务，将 OCR 结果与规则/启发式解析逻辑结合  
- 针对日本处方格式进行定制化适配，提升多语言、多版式场景下的识别准确率  
- 集成 CloudSQL 与 BigQuery，用于多区域数据存储与使用监控  

#### 图像质量分析与人工审核工具
- 分析因模糊、拍摄质量问题导致的 OCR / 解析失败案例  
- 基于日志与用户行为分析定位质量退化模式  
- 构建 Streamlit 内部工具，用于结果可视化与人工校验  


### UT Southwestern Medical Center | 数据科学家  
Quantitative Biomedical Research Center  
美国达拉斯 | 2021.09 – 2023.05

#### 生物医学影像与多模态数据系统
- 设计并实现结合空间影像与 CyTOF 单细胞表达数据的分析系统  
- 构建 Flask 服务，支持并行处理与 Docker 化部署  
- 相比基线流程实现约 10× 性能提升  

#### 数字病理细胞分割与分类
- 基于 Mask R-CNN 构建 H&E 切片中的细胞核分割与 6 类分类模型  
- 针对不完整标注数据定制 loss 与训练策略，挽回约 20% 数据  
- 在弱监督条件下达到 82.5% 检测率与 82.0% 分类准确率  

#### 电子病历文本处理（支持性工作）
- 协助将现有 EHR 去标识化与预处理工具接入研究流程  


### Donald Danforth Plant Science Center | 数据科学研究员  
美国圣路易斯 | 2020.02 – 2021.09

- 构建 RGB、热成像与高光谱植物影像的自动化处理与可视化流水线  
- 开发叶片实例级分割与时间序列跟踪算法，用于生长分析  
- 参与开源项目 PlantCV：模块开发、测试、文档与社区培训  
- 支持生物学与工程团队开展可复现的数据分析  

---

### University of Florida Academic Health Center | 数据科学实习生  
美国盖恩斯维尔 | 2019.05 – 2019.08

- 处理住院后 24 小时内的生命体征时间序列数据  
- 构建特征并评估多种聚类方法  
- 复现并验证应对非规则采样的插值建模方法  

---

## 个人项目

### AI 新闻 Agent（LLM 新闻摘要与问答）
- 构建 AI 相关新闻的自动抓取、摘要与问答系统  
- 设计轻量级 RAG 架构，结合网页抓取、向量检索与 LLM  
- 实现定时抓取、自动标签与分类摘要  
- 支持基于新闻语料的用户问答  
- 使用 Streamlit 构建前端，部署于 Hugging Face Spaces，并探索 Docker 化部署  

---

## 教育背景

**佛罗里达大学**  
- 电气与计算机工程 硕士（GPA 3.86/4），2019  
  *论文：基于高光谱影像的牧草基因型分类*  

- 工业与系统工程 硕士（GPA 3.87/4），2017  

**同济大学**  
- 物理学 学士（GPA 4.45/5），2015  
  *论文：X-Ray KB 成像强度不均匀性校正*  

---

## 发表论文

<!-- - Sheng et al., MTIA: An open-source python package for multiplexed tissue image analysis（准备中）  
- Sheng et al., Plant Phenotyping Annotation Throughput, Authorea, 2023  
- Rong et al., Modern Pathology, 2023  
- Panda et al., New Phytologist, 2023  
- Yu et al., Machine Vision and Applications, 2020   -->
<ul>
  {% for post in site.publications reversed %}
    {% include archive-single-cv.html %}
  {% endfor %}
</ul>
---

## 个人优势

- **系统思维**：关注鲁棒性、失败处理与端到端设计  
- **快速学习能力**：可快速进入新领域并独立落地  
- **沟通能力**：能向技术与非技术对象解释复杂系统  
- **跨文化协作**：中英双语，具备中美团队合作经验  