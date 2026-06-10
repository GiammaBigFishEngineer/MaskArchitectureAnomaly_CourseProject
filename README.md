This repository contains the implementation, evaluation, and fine-tuning pipeline for the **EoMT** architecture, evaluating its performance against a convolutional baseline **ERFNet** on joint tasks of semantic/panoptic segmentation and anomaly detection.

# Repository structure

## 1. Semantic and Panoptic Segmentation
The file `inferenceSTEP4.ipynb` is used for:
* **Semantic Segmentation:** Calculates the mIoU for the checkpoints `eomt_cityscapes` and `eomt_coco`.
* **Panoptic Segmentation:** Tests the `eomt_coco` model on a sample image from the COCO dataset.

## 2. Fine-Tuning
The fine-tuning process is handled via PyTorch Lightning to adapt the base `eomt_coco` model to the Cityscapes domain, ultimately generating a third checkpoint called `eomt_coco_ft`. 

To validate our "network surgery" approach, the training process is split across two notebooks:
* **`STEP5_lighiting_no_head.ipynb` (Configuration A):** Implements the *Linear Probing Baseline*. In this notebook, only the `class_head` is unfrozen, keeping the object queries and mask heads frozen to test the model's ability to rely purely on unmodified COCO spatial features.
* **`STEP_5_lighting.ipynb` (Configuration B):** Implements the *Targeted Network Surgery*. This notebook coordinates the unfreezing of the `class_head`, `mask_head`, `upscale` module, and the learnable object queries (`q.weight`) to achieve the optimal spatial adaptation.

## 3. Anomaly detection and Temperature Scaling
This section compares ERFNet and EoMT on anomaly detection by measuring their prediction uncertainty across different datasets.
The file `step7.ipynb` focuses on the baseline model ERFNet:
* **Post-Hoc Methods baseline:** Establishes the OOD baseline by applying three post-hoc scoring methods directly to dense pixel logits: MSP, Max Entropy, and Max Logit across 5 datasets.
* **Baseline Evaluation of mIoU:** Calculates the mIoU on the Cityscapes dataset. 
  
The file `step8.ipynb` contains the post-hoc analysis and temperature scaling:
* **Post-Hoc Methods:** Applies 4 different methods (MSP, Max Logit, Max Entropy, and RbA) across 5 datasets for all 3 EOMT checkpoints (`eomt_cityscapes`, `eomt_coco`, and `eomt_coco_ft`).
* **Temperature Scaling:** Applies temperature scaling on the MSP score specifically for the `eomt_cityscapes` checkpoint, to analyze the effect of distribution sharpening ($T < 1.0$) and smoothing ($T > 1.0$) on AUPRC and FPR95 metrics.
