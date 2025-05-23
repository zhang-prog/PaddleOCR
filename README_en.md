English | [简体中文](README.md)

<p align="center">
 <img src="https://github.com/PaddlePaddle/PaddleOCR/releases/download/v2.8.0/PaddleOCR_logo.png" align="middle" width = "600"/>
<p align="center">
<p align="center">
    <a href="https://discord.gg/z9xaRVjdbD"><img src="https://img.shields.io/badge/Chat-on%20discord-7289da.svg?sanitize=true" alt="Chat"></a>
    <a href="./LICENSE"><img src="https://img.shields.io/badge/license-Apache%202-dfd.svg"></a>
    <a href="https://github.com/PaddlePaddle/PaddleOCR/releases"><img src="https://img.shields.io/github/v/release/PaddlePaddle/PaddleOCR?color=ffa"></a>
    <a href=""><img src="https://img.shields.io/badge/python-3.7+-aff.svg"></a>
    <a href=""><img src="https://img.shields.io/badge/os-linux%2C%20win%2C%20mac-pink.svg"></a>
    <a href="https://pypi.org/project/PaddleOCR/"><img src="https://img.shields.io/pypi/dm/PaddleOCR?color=9cf"></a>
    <a href="https://github.com/PaddlePaddle/PaddleOCR/stargazers"><img src="https://img.shields.io/github/stars/PaddlePaddle/PaddleOCR?color=ccf"></a>
</p>

## Introduction

PaddleOCR aims to create multilingual, awesome, leading, and practical OCR tools that help users train better models and apply them into practice.

**⚠️ Note: The `main` branch is undergoing major refactoring. For stable access to documentation and code, please switch to a stable branch (e.g., `release/2.10`).**  

<div align="center">
    <img src="https://github.com/PaddlePaddle/PaddleOCR/releases/download/v2.8.0/demo.gif" width="800">
</div>

## 🚀 Community

PaddleOCR is being oversight by a [PMC](https://github.com/PaddlePaddle/PaddleOCR/issues/12122). Issues and PRs will be reviewed on a best-effort basis. For a complete overview of PaddlePaddle community, please visit [community](https://github.com/PaddlePaddle/community).

⚠️ Note: The [Issues](https://github.com/PaddlePaddle/PaddleOCR/issues) module is only for reporting program 🐞 bugs, for the rest of the questions, please move to the [Discussions](https://github.com/PaddlePaddle/PaddleOCR/discussions). Please note that if the Issue mentioned is not a bug, it will be moved to the Discussions module.

## 📣 Recent updates ([more](https://paddlepaddle.github.io/PaddleOCR/latest/en/update.html))


- **🔥🔥2025.3.7 release PaddleOCR v2.10, including**:

  - **12 new self-developed single models:**
    - **[Layout Detection](https://paddlepaddle.github.io/PaddleX/latest/en/module_usage/tutorials/ocr_modules/layout_detection.html)** series with 3 models: PP-DocLayout-L, PP-DocLayout-M, PP-DocLayout-S, supporting prediction of 23 common layout categories. High-quality layout detection for various document types such as papers, reports, exams, books, magazines, contracts, newspapers in both English and Chinese. **mAP@0.5 reaches up to 90.4%, lightweight models can process over 100 pages of document images per second end-to-end.**
    - **[Formula Recognition](https://paddlepaddle.github.io/PaddleX/latest/en/module_usage/tutorials/ocr_modules/formula_recognition.html)** series with 2 models: PP-FormulaNet-L, PP-FormulaNet-S, supporting 50,000 common LaTeX vocabulary, capable of recognizing complex printed and handwritten formulas. **PP-FormulaNet-L has 6 percentage points higher accuracy than models of the same level, and PP-FormulaNet-S is 16 times faster than models with similar accuracy.**
    - **[Table Structure Recognition](https://paddlepaddle.github.io/PaddleX/latest/en/module_usage/tutorials/ocr_modules/table_structure_recognition.html)** series with 2 models: SLANeXt_wired, SLANeXt_wireless. A newly developed table structure recognition model, supporting structured prediction for both wired and wireless tables. Compared to SLANet_plus, SLANeXt shows significant improvement in table structure, **with 6 percentage points higher accuracy on internal high-difficulty table recognition evaluation sets.**
    - **[Table Classification](https://paddlepaddle.github.io/PaddleX/latest/en/module_usage/tutorials/ocr_modules/table_classification.html)** series with 1 model: PP-LCNet_x1_0_table_cls, an ultra-lightweight classification model for both wired and wireless tables.
    - **[Table Cell Detection](https://paddlepaddle.github.io/PaddleX/latest/en/module_usage/tutorials/ocr_modules/table_cells_detection.html)** series with 2 models: RT-DETR-L_wired_table_cell_det, RT-DETR-L_wireless_table_cell_det, supporting cell detection in both wired and wireless tables. These can be combined with SLANeXt_wired, SLANeXt_wireless, text detection, and text recognition modules for end-to-end table prediction. (See the newly added Table Recognition v2 pipeline)
    - **[Text Recognition](https://paddlepaddle.github.io/PaddleX/latest/en/module_usage/tutorials/ocr_modules/text_recognition.html)** series with 1 model: PP-OCRv4_server_rec_doc, **supports over 15,000 characters, with a broader text recognition range, additionally improving the recognition accuracy of certain texts. The accuracy is more than 3 percentage points higher than PP-OCRv4_server_rec on internal datasets.**
    - **[Text Line Orientation Classification](https://paddlepaddle.github.io/PaddleX/latest/module_usage/tutorials/ocr_modules/text_recognition.html)** series with 1 model: PP-LCNet_x0_25_textline_ori, **an ultra-lightweight text line orientation classification model with only 0.3M storage.**

   - **4 high-value multi-model combination solutions:**
     - **[Document Image Preprocessing Pipeline](https://paddlepaddle.github.io/PaddleX/latest/en/pipeline_usage/tutorials/ocr_pipelines/doc_preprocessor.html)**: Achieve correction of distortion and orientation in document images through the combination of ultra-lightweight models.
     - **[Layout Parsing v2 Pipeline](https://paddlepaddle.github.io/PaddleX/latest/en/pipeline_usage/tutorials/ocr_pipelines/layout_parsing_v2.html)**: Combines multiple self-developed different types of OCR models to optimize complex layout reading order, achieving end-to-end conversion of various complex PDF files to Markdown and JSON files. The conversion effect is better than other open-source solutions in multiple document scenarios. It can provide high-quality data production capabilities for large model training and application.
     - **[Table Recognition v2 Pipeline](https://paddlepaddle.github.io/PaddleX/latest/en/pipeline_usage/tutorials/ocr_pipelines/table_recognition_v2.html)**: **Provides better table recognition capabilities.** By combining table classification module, table cell detection module, table structure recognition module, text detection module, text recognition module, etc., it achieves prediction of various styles of tables. Users can customize and finetune any module to improve the effect of vertical tables.
     - **[PP-ChatOCRv4-doc Pipeline](https://paddlepaddle.github.io/PaddleX/latest/en/pipeline_usage/tutorials/information_extraction_pipelines/document_scene_information_extraction_v4.html)**: Based on PP-ChatOCRv3-doc, **integrating multi-modal large models, optimizing Prompt and multi-model combination post-processing logic. It effectively addresses common complex document information extraction challenges such as layout analysis, rare characters, multi-page PDFs, tables, and seal recognition, achieving 15 percentage points higher accuracy than PP-ChatOCRv3-doc. The large model upgrades local deployment capabilities, providing a standard OpenAI interface, supporting calls to locally deployed large models like DeepSeek-R1.**

- **🔥 2024.10.18 release PaddleOCR v2.9, including**:
    - PaddleX, an All-in-One development tool based on PaddleOCR's advanced technology, supports low-code full-process development capabilities in the OCR field:
        - 🎨 [**Rich Model One-Click Call**](https://paddlepaddle.github.io/PaddleOCR/latest/en/paddlex/quick_start.html): Integrates **17 models** related to text image intelligent analysis, general OCR, general layout parsing, table recognition, formula recognition, and seal recognition into 6 pipelines, which can be quickly experienced through a simple **Python API one-click call**. In addition, the same set of APIs also supports a total of **200+ models** in image classification, object detection, image segmentation, and time series forecasting, forming 20+ single-function modules, making it convenient for developers to use **model combinations**.

        - 🚀 [**High Efficiency and Low barrier of entry**](https://paddlepaddle.github.io/PaddleOCR/latest/en/paddlex/overview.html): Provides two methods based on **unified commands** and **GUI** to achieve simple and efficient use, combination, and customization of models. Supports multiple deployment methods such as **high-performance inference, service-oriented deployment, and edge deployment**. Additionally, for various mainstream hardware such as **NVIDIA GPU, Kunlunxin XPU, Ascend NPU, Cambricon MLU, and Haiguang DCU**, models can be developed with **seamless switching**.

    - Supports [PP-ChatOCRv3-doc](https://paddlepaddle.github.io/PaddleX/latest/en/pipeline_usage/tutorials/information_extraction_pipelines/document_scene_information_extraction.html), [high-precision layout detection model based on RT-DETR](https://paddlepaddle.github.io/PaddleX/latest/en/module_usage/tutorials/ocr_modules/layout_detection.html) and [high-efficiency layout area detection model based on PicoDet](https://paddlepaddle.github.io/PaddleX/latest/en/module_usage/tutorials/ocr_modules/layout_detection.html), [high-precision table structure recognition model](https://paddlepaddle.github.io/PaddleX/latest/en/module_usage/tutorials/ocr_modules/table_structure_recognition.html), text image unwarping model [UVDoc](https://paddlepaddle.github.io/PaddleX/latest/en/module_usage/tutorials/ocr_modules/text_image_unwarping.html), formula recognition model [LatexOCR](https://paddlepaddle.github.io/PaddleX/latest/en/module_usage/tutorials/ocr_modules/formula_recognition.html), and [document image orientation classification model based on PP-LCNet](https://paddlepaddle.github.io/PaddleX/latest/en/module_usage/tutorials/ocr_modules/doc_img_orientation_classification.html).

- **🔥2024.7 Added PaddleOCR Algorithm Model Challenge Champion Solutions**:
    - Challenge One, OCR End-to-End Recognition Task Champion Solution: [Scene Text Recognition Algorithm-SVTRv2](https://paddlepaddle.github.io/PaddleOCR/algorithm/text_recognition/algorithm_rec_svtrv2.html);
    - Challenge Two, General Table Recognition Task Champion Solution: [Table Recognition Algorithm-SLANet-LCNetV2](https://paddlepaddle.github.io/PaddleOCR/algorithm/table_recognition/algorithm_table_slanet.html).

## 📚 Documentation

Full documentation can be found on [docs](https://paddlepaddle.github.io/PaddleOCR/latest/en/index.html).

## 🌟 Features

PaddleOCR support a variety of cutting-edge algorithms related to OCR, and developed industrial featured models/solution [PP-OCR](https://paddlepaddle.github.io/PaddleOCR/latest/en/ppocr/overview.html), [PP-Structure](https://paddlepaddle.github.io/PaddleOCR/latest/en/ppstructure/overview.html) and [PP-ChatOCR](https://aistudio.baidu.com/aistudio/projectdetail/6488689) on this basis, and get through the whole process of data production, model training, compression, inference and deployment.

<div align="center">
    <img src="./docs/images/ppocrv4_en.jpg">
</div>

> It is recommended to start with the “quick experience” in the document tutorial

## ⚡ [Quick Start](https://paddlepaddle.github.io/PaddleOCR/latest/en/quick_start.html)

## 📖 Technical exchange and cooperation

PaddleX provides a one-stop full-process high-efficiency development platform for flying paddle ecological model training, pressure, and push. Its mission is to help AI technology quickly land, and its vision is to make everyone an AI Developer!

- PaddleX currently covers areas such as image classification, object detection, image segmentation, 3D, OCR, and time series prediction, and has built-in 36 basic single models, such as RP-DETR, PP-YOLOE, PP-HGNet, PP-LCNet, PP- LiteSeg, etc.; integrated 12 practical industrial solutions, such as PP-OCRv4, PP-ChatOCR, PP-ShiTu, PP-TS, vehicle-mounted road waste detection, identification of prohibited wildlife products, etc.
- PaddleX provides two AI development modes: "Toolbox" and "Developer". The toolbox mode can tune key hyperparameters without code, and the developer mode can perform single-model training, push and multi-model serial inference with low code, and supports both cloud and local terminals.
- PaddleX also supports joint innovation and development, profit sharing! At present, PaddleX is rapidly iterating, and welcomes the participation of individual developers and enterprise developers to create a prosperous AI technology ecosystem!

## 📚 E-book: *Dive Into OCR*

- [Dive Into OCR](https://paddlepaddle.github.io/PaddleOCR/latest/en/ppocr/blog/ocr_book.html)

## 🎖 Contributors

<a href="https://github.com/PaddlePaddle/PaddleOCR/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=PaddlePaddle/PaddleOCR&max=400&columns=20"  width="800"/>
</a>

## ⭐️ Star

[![Star History Chart](https://api.star-history.com/svg?repos=PaddlePaddle/PaddleOCR&type=Date)](https://star-history.com/#PaddlePaddle/PaddleOCR&Date)

## 🇺🇳 Guideline for New Language Requests

If you want to request a new language support, a PR with 1 following files are needed：

- In folder [ppocr/utils/dict](./ppocr/utils/dict),
it is necessary to submit the dict text to this path and name it with `{language}_dict.txt` that contains a list of all characters. Please see the format example from other files in that folder.

If your language has unique elements, please tell me in advance within any way, such as useful links, wikipedia and so on.

More details, please refer to [Multilingual OCR Development Plan](https://github.com/PaddlePaddle/PaddleOCR/discussions/12734).

## 📄 License

This project is released under [Apache License Version 2.0](./LICENSE).
