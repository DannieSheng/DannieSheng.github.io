---
title: "Automated Prescription Parsing API development, maintain, and improvement (for the Japanese Market)"
excerpt: "September 2023 – October 2023<br/>
This project aimed to extend the capabilities of an existing in-house developed tool, OptiReader, designed for the automatic parsing of eyeglass prescriptions. 
Initially supporting the North American market, the project's goal was to adapt the tool for the Japanese market, particularly for VR eyeglasses, by incorporating innovative document understanding technologies and custom solutions to handle unique prescription formats prevalent in Japan. <br/>"
collection: portfolio
---

Business Question
======
How can we leverage advanced document understanding and machine learning technologies to automate the parsing of eyeglass prescriptions, thereby improving accuracy, reducing manual processing times, and enhancing our service offerings in a new international market?

Key Achievements
======

* Technology Integration: Leveraged Google Document AI API's Form Parser for initial solutions, primarily for PDF format inputs, and integrated [Donut, an OCR-free Visual Document Understanding (VDU) model](https://arxiv.org/abs/2111.15664). Donut utilizes a Transformer architecture and is pretrained on datasets in English, Chinese, Korean, and Japanese, showcasing state-of-the-art performance in VDU without the need for OCR.

* Market Research: Identified two main types of prescriptions in the Japanese market: horizontal prescriptions, similar to those in North America except for the language, and vertical prescriptions, which are rare in North America but constitute over 50% of prescriptions in Japan.

* Model Adaptation: Modified the existing model to process prescriptions containing Japanese text and to handle vertical prescriptions, addressing a significant need in the Japanese market without the extensive time and resources required to retrain the Donut model from scratch.

* API Enhancement: Added a country_of_origin input parameter to the API to differentiate prescriptions based on their origin, enabling tailored processing steps for Japanese prescriptions.

* Post-Processing and Integration: Implemented a post-processing step to determine the orientation of Japanese prescriptions. Horizontal prescriptions are processed directly, while vertical prescriptions are parsed using Google Form Parser, leveraging existing tools for accurate parsing.

* Deployment and Market Support: After successful testing in the development environment, the enhanced OptiReader tool was deployed in the production environment, offering full support for the Japanese market.

Why This Approach?
------

* Innovative Use of VDU Technology: By adopting Donut, an OCR-free model, the project bypassed traditional OCR limitations, achieving high accuracy and speed in document understanding tasks.

* Market-Specific Adaptations: The project's focus on understanding and adapting to the unique aspects of the Japanese prescription market demonstrates a commitment to providing tailored solutions that meet specific regional needs.

* Efficient Resource Utilization: The decision to use post-processing techniques and integrate with Google Form Parser for vertical prescriptions allowed for rapid adaptation to the Japanese market without the need for extensive model retraining.

Conclusion
======

This project highlights the potential of advanced document understanding technologies in automating prescription parsing, with specific adaptations to meet the unique needs of the Japanese eyewear market. It showcases our ability to innovate and efficiently extend the reach of existing tools to new markets.
