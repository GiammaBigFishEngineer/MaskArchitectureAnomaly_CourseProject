# Comprehensive Road Scene Understanding for Autonomous Driving

This repository documents the research and implementation activities for the analysis of the Encoder-only Mask Transformer (EoMT) model within the context of autonomous driving.

## Project Structure

- [Exercise 4: Semantic Segmentation Evaluation](#exercise-4-semantic-segmentation-evaluation)
- [Exercise 5: Fine-tuning & Ablation Study](#exercise-5-fine-tuning--ablation-study)
- [Exercise 6: Anomaly Detection Baseline (ERFNet)](#exercise-6-anomaly-detection-baseline-erfnet)
- [Exercise 7: Mask-based Anomaly Extraction (EoMT)](#exercise-7-mask-based-anomaly-extraction-eomt)
- [Exercise 8: Uncertainty Estimation & Evaluation](#exercise-8-uncertainty-estimation--evaluation)

---

## Exercise 4: Semantic Segmentation Evaluation
Initial performance evaluation of EoMT-Cityscapes and EoMT-COCO on the Cityscapes validation set. For EoMT-COCO, a manual semantic mapping step was necessary to align the COCO label space with the urban semantic categories of Cityscapes.

## Exercise 5: Fine-tuning & Ablation Study
Domain adaptation study via "network surgery". To prevent catastrophic forgetting of the ViT backbone, most parameters were frozen while focusing on targeted components:
- **Configuration A (Linear Probing):** Unfreezing exclusively the `class_head`.
- **Configuration B (Targeted Surgery):** Coordinated unfreezing of `class_head`, `mask_head`, `upscale`, and object queries (`q.weight`), which was essential to adapt spatial priors to urban morphologies.
The fine-tuned model achieved a global mIoU of 70.00%.

## Exercise 6: Anomaly Detection Baseline (ERFNet)


## Exercise 7: Mask-based Anomaly Extraction (EoMT)


## Exercise 8: Uncertainty Estimation & Evaluation


---