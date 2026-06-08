# Project structure

## 1. Semantic and Panoptic Segmentation
The file `inferenceSTEP4.ipynb` is used for:
* **Semantic Segmentation:** Calculates the mIoU for the checkpoints `eomt_cityscapes` and `eomt_coco`.
* **Panoptic Segmentation:** Tests the `eomt_coco` model on a sample image from the COCO dataset.

## 2. Fine-Tuning
The files `inferenceEx5.ipynb` and `step 5 - ...` are used for the fine-tuning process. 
They take the base `eomt_coco` model and use it to create a third checkpoint called `eomt-coco-ft`.

* In particular, nel file ... abbiamo fatto configuration A e nel file .. configuration B

## 3. Anomaly detection and Temperature Scaling
The file `step7` focuses on the baseline model ERFNet:
* **Post-Hoc Methods baseline:** Applies 3 methods (MSP, Max Entropy, and Max Logit) across 5 dataset.
* **Baseline Evaluation of mIoU:** Calculates the mIoU on the Cityscapes dataset. 
  
The file `step8_finito` contains the post-hoc analysis and temperature scaling:
* **Post-Hoc Methods:** Applies 4 different methods (MSP, Max Logit, Max Entropy, and RbA) across 5 datasets for all 3 EOMT checkpoints (`eomt_cityscapes`, `eomt_coco`, and `eomt_coco_ft`).
* **Temperature Scaling:** Applies temperature scaling to the MSP method specifically for the `eomt_cityscapes` checkpoint.
