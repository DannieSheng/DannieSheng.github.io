## Projects
### Automatic Prescription Parsing Project（with a specific support for Japanese Market and VR eyegrasses' launch）2023.09 ～ 2023.10
In a recent project, I spearheaded the expansion of OptiReader, an internal tool designed for automatic eyeglass prescription parsing, to support the Japanese market — a critical step for our VR eyeglasses' launch in Japan. 
Initially, OptiReader was deployed using FastAPI in production for the North American market, leveraging Google Document AI API's Form Parser for PDF inputs. To address the unique challenges of the Japanese market, including the prevalence of vertical prescription formats which were virtually non-existent in North America, I led a research initiative to adapt our model for these specifications without the extensive overhead of retraining our existing model, Donut, which is a cutting-edge, OCR-free Visual Document Understanding model pre-trained on datasets in English, Chinese, Korean, and Japanese.

Recognizing that over 50% of Japanese prescriptions are in a vertical format and considering the smaller market size, we opted for a cost-effective yet efficient solution. I implemented a feature to classify prescriptions based on their orientation using post-processed outputs from Donut. For vertical prescriptions, identified through the country_of_origin=JP indicator, we integrated an additional step employing Google Form Parser. This strategic decision allowed us to efficiently parse vertical prescriptions without the need for retraining the model from scratch.

This initiative not only streamlined the adaptation of our tool for the Japanese market but also underscored our commitment to innovation and market expansion. It was a testament to our ability to leverage state-of-the-art technologies and adapt quickly to new market demands, ensuring seamless integration and functionality across different regions.

### Image Quality Assessment Module for Blur Detection 2023.11 ～ 2024.01
In one of my recent projects, I tackled a crucial challenge in the domain of prescription parsing accuracy by addressing the impact of image quality on the success rate of our existing optical character recognition (OCR) system. Observations from production environments and intuitive understanding both indicated that the quality of the images, particularly their blurriness, significantly influenced the parsing accuracy.

To enhance our system's robustness, I spearheaded the development of a multi-task image quality assessment module capable of simultaneously evaluating both the orientation and the blurriness of images. Leveraging the advanced ConvNeXt V2 architecture, known for its exceptional performance in image classification, object detection, and segmentation, I adapted this model to our specific needs. ConvNeXt V2's full-convolutional autoencoder architecture and Global Response Normalization (GRN) layer, which were instrumental in its success across various benchmarks, served as the backbone of our solution.

A significant part of this project involved addressing the challenge of data imbalance, particularly the underrepresentation of highly blurry images in our dataset. To mitigate this, I expanded our dataset through targeted data collection efforts from our production database and developed a visualization tool using Streamlit to streamline the data labeling process, resulting in a dataset of approximately 1800 labeled prescription images.

The model, powered by ConvNeXt V2 and optimized with a (Poly1) **Focal Loss** function to tackle class imbalance, achieved impressive performance metrics: 96.2% accuracy and an F1 score of 95.4% for 'Fine' images, and 89.6% accuracy with an F1 score of 88.9% for 'Blurry' images.

This project not only demonstrated my ability to apply cutting-edge computer vision technologies but also underscored my commitment to addressing real-world challenges through innovative data science solutions. It was a pivotal step in enhancing the accuracy and reliability of our OCR system, ensuring better service delivery in the market.

<!-- ### 西门子的“2023年科技促进可持续发展”活动比赛中的“电网中的群体行为”组获胜 (2023.02)
- 随着可再生能源变得更加经济实惠，其实施正导致生产方式越来越分散。此外，能源消费者正演变为拥有各种智能能源资产的生产消费者（prosumers）。能源管理的复杂性显著增加。为了处理这种复杂性，我们需要更好地理解人们的行为，并将其纳入电网管理中。
- 消费者和生产消费者的行为受到很多因素的巨大影响，例如体育赛事、假期或地缘政治事件，这些因素的影响难以预测。这导致管理电网稳定性的不确定性上升。问题在于如何最大化每个人对实现净零排放的贡献，同时最小化对能源网络运营的负担。 -->

### mask R-CNN 用于H&E染色病理图像检测项目 2021.10 ～ 2021.12
- 已有基于keras的mask R-CNN的模型，用于检测非小细胞肺癌(Non-Small Cell Lung Cancer)的染色病理图像中常见的6类细胞核，并同时进行分割和分类
- 通过迁移学习，微调一个用于检测乳腺癌的染色病理图像中常见的7类细胞核，并同时进行分割和分类
- 由于数据的标签存在一定缺陷，不能直接用于训练：
    - Mask R-CNN的需要同时有边界框和（位置）、类别标签、以及像素级别的掩码标签
    - 真实数据的标签有部分缺失———有些数据缺失了掩码标签，有些数据缺失了类别标签（`Unlabeled`）；经统计，这部分标签缺失占总数据的20%（直接舍弃会造成数据浪费）
- 通过重新设计mask R-CNN的损失函数，使得计算损失的时可以有选择地忽略标签有缺失的样本
    - 具体来说，缺少分类标签的样本不参与分类损失的计算，缺少掩码标签的样本不参与掩码损失的计算
-  获得了一个基于PyTorch框架的、适用于检测乳腺癌的染色病理图像中常见的7类细胞核，并同时进行分割和分类的mask R-CNN模型（检测率82.5%，7分类准确率82.0%）
- Mask R-CNN (region based CNN) 选择原因：
    - Mask R-CNN在实例分割任务中具有高精确度和准确性。在肿瘤细胞核检测中，准确地定位和分割细胞核是至关重要的。
    - Mask R-CNN不仅能够检测物体的边界框，还能生成每个对象实例的详细掩码。对于肿瘤细胞核检测，掩码的生成能力可以提供更详细和精细的信息，有助于更准确地理解细胞核的形状和结构。
    - 基于PyTorch的Mask R-CNN具有灵活性和可调整性，可以根据任务的需求进行修改和调整。这使得它非常适合处理不同形状、尺寸和密度的肿瘤细胞核。
    - Mask R-CNN 是一个受欢迎的模型，有一个庞大而先进的社区支持，拥有丰富的资源、文档和预训练模型。这有助于简化开发过程，加速模型训练和优化过程。

### plantCV 项目 2020.02 ～ 2021.09
- [PlantCV](https://plantcv.danforthcenter.org/)（Plant Computer Vision）是一个专为植物表型分析设计的开源软件包，它基于Python编程语言开发，集成了OpenCV（Open Source Computer Vision Library）等先进的图像处理库。该项目旨在为植物科学家和研究人员提供一个强大、灵活且用户友好的工具，以自动化和量化从各种图像数据中提取的植物表型信息
- 核心功能
    - 图像预处理：PlantCV提供了一系列图像预处理功能，如调整大小、裁剪、背景去除、噪声滤波等，以改善图像质量，为后续分析做准备
    - 特征提取：能够从图像中提取多种植物表型特征，包括但不限于形态学特征（如面积、周长、形状描述符）、颜色特征、纹理特征等
    - 多模态分析：支持处理和分析来自不同成像模式的数据，包括可见光、荧光、红外线和三维成像数据，使其能够适应多种研究需求和实验设计
    - 高通量处理：针对高通量植物表型平台设计，能够自动化处理大量图像数据，提高研究效率和数据处理能力
- 设计理念
    - 开源和社区驱动：PlantCV是一个开源项目，鼓励社区贡献和协作，通过GitHub等平台进行代码共享、问题解答和功能更新
    - 易于使用和扩展：提供了详细的文档、教程和示例代码，帮助用户快速上手并根据自己的研究需求定制和扩展功能
    - 跨学科工具：虽然主要面向植物科学领域，但其强大的图像处理和分析能力也适用于生物学、生态学和农业科学等相关领域的研究
- 应用场景
    - 基因型与表型关联分析：通过量化表型特征，帮助研究人员探索基因型与表型之间的关系
    - 环境应答研究：分析植物对环境变化（如光照、温度、水分等）的表型响应，以研究其适应性和生存策略
    - 品种筛选和育种：量化分析植物表型特征，为植物育种和品种改良提供科学依据

# Skills
* 数学和统计学基础：具备扎实的数学原理、概率论和统计学基础，并将这些概念应用于实际情境
* 人工智能和机器学习：机器学习、深度学习和计算机视觉，开发和部署复杂的深度学习和机器学习模型
* 深度学习框架或平台：PyTorch、spaCy、TensorFlow、Keras、Hugging Face
* 编程语言和工具：Python (包括NumPy、Pandas、Scikit-learn、SciPy、ggplot2、Seaborn、OpenCV、Streamlit和plotly等库)、 MATLAB
* DevOps及云技术：Google Cloud、熟练使用Docker进行容器化
* 版本控制：Git
* 数据库和数据存储：MySQL、CloudSQL、BigQuery
* Web开发：Flask框架、FastAPI框架、HTML、CSS、Ajax和JavaScript
* 数据分析：SQL、MS Office、Tableau
* 其他领域：电子健康档案（EHR）数据分析
