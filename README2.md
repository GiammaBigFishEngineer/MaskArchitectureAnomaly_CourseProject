# Project structure

## 1. Semantic and Panoptic Segmentation
The file `inferenceSTEP4.ipynb` is used for:
* **Semantic Segmentation:** Calculates the mIoU for the checkpoints `eomt_cityscapes` and `eomt_coco`.
* **Panoptic Segmentation:** Tests the `eomt_coco` model on a sample image from the COCO dataset.

## 2. Fine-Tuning
The files `inferenceEx5.ipynb` and `step 5 - ...` are used for the fine-tuning process. 
They take the base `eomt_coco` model and use it to create a third checkpoint called `eomt-coco-ft`.

* In particular, nel file ... abbiamo fatto configuration A e nel file .. configuration B

## 3. Anomaly detection 
