# EOMT Model - Inference and Fine-Tuning

## EOMT Folder Structure

### 1. Semantic and Panoptic Segmentation
The file `inferenceSTEP4.ipynb` is used for:
* **Semantic Segmentation:** Calculates the mIoU (Mean Intersection over Union) for the checkpoints `eomt_cityscapes` and `eomt_coco`.
* **Panoptic Segmentation:** Tests the `eomt_coco` model on a sample image from the COCO dataset.

### 2. Fine-Tuning
The files `inferenceEx5.ipynb` and `step 5 - ...` are used for the fine-tuning process. 
They take the base `eomt_coco` model and use it to create a third checkpoint called `eomt-coco-ft`.

* In particular, in [COMPLETA QUI CON IL NOME DEL FILE], we [COMPLETA QUI CON COSA FA IL FILE].
