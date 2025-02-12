# Asbestos Fiber Segmentation

## Abstract

Asbestos refers to a group of naturally occurring fibrous minerals with a crystalline structure. When inhaled, asbestos fibers can settle deep in the lungs where the immune system cannot break them down, leading to lung damage and scarring (asbestosis). Moreover, exposure to asbestos significantly increases the risk of developing lung cancer and mesothelioma. Therefore, controlling asbestos in building materials and other areas is crucial.

Manually identifying asbestos fibers in low-magnification electron microscopy images is challenging—even for experts. Computer vision algorithms can help by automatically detecting the presence of asbestos and pinpointing its exact location within an image.

## Overview

This project presents a computer vision-based algorithm that leverages convolutional neural networks (CNNs) with a U-Net architecture to segment asbestos fibers in low-magnification electron microscopy images. Key aspects include:

- **Data Augmentation:**  
  Due to the limited amount of annotated data, extensive data augmentation techniques were employed. These include:
  - Image cropping
  - Random rotations
  - Other transformations

  The augmentation was carefully balanced to avoid:
  - **Over-augmentation:** Which can result in unrealistic images.
  - **Under-augmentation:** Which can lead to overfitting.

- **Model Optimization:**  
  Multiple experiments were conducted to optimize the model. The experiments explored:
  - Different loss functions
  - Learning rate schedulers
  - Various numbers of filters in the convolutional layers

  Notably:
  - A **weighted combination of Binary Cross-Entropy (BCE) and Dice loss** significantly improved performance.
  - The **OneCycle learning rate scheduler** outperformed other schedulers.

## Performance Metrics

The optimized model achieved impressive segmentation quality metrics, including:
- **ROC AUC:** 0.9864
- **Average Precision (PR curve):** 0.5076
- **Jaccard Score:** 0.36

## Future Work

Future research directions include:
- Exploring multiclass asbestos segmentation to not only detect asbestos but also classify fibers based on their threat levels.
- Enhancing automated image analysis workflows further.

---

Feel free to explore the repository for more details on the model architecture, experiments, and data augmentation strategies.
