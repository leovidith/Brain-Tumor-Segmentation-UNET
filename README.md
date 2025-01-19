# Brain Tumor Segmentation using U-Net

<img src="https://github.com/leovidith/Brain-Tumor-Segmentation-UNET/blob/master/Generalized%20Images/segmentation.gif">

## Overview and Problem Statement
Brain tumor segmentation is a critical task in medical imaging that aids in the diagnosis, treatment planning, and monitoring of brain tumors. The project leverages the U-Net architecture, a convolutional neural network designed specifically for biomedical image segmentation. By automating the segmentation of brain tumors in MRI scans, the project reduces the workload of radiologists and ensures consistent, accurate results. Applications include:

- Early detection of brain tumors.
- Assisting in surgical planning.
- Monitoring tumor progression and treatment response.

<img src="https://github.com/leovidith/Brain-Tumor-Segmentation-UNET/blob/master/Generalized%20Images/img3.png" width=600px>

## About Dataset
The dataset used is the **BraTS 2020** dataset, consisting of multimodal MRI scans from glioma patients. Each patient has four imaging modalities:

1. T1 (Native)
2. T1ce (Post-contrast T1-weighted)
3. T2 (T2-weighted)
4. T2-FLAIR (Fluid Attenuated Inversion Recovery)

<img src="https://github.com/leovidith/Brain-Tumor-Segmentation-UNET/blob/master/Generalized%20Images/img1.png" width=600px>

Annotations include segmentation masks that label the tumor into sub-regions:

- **Label 0**: Not Tumor
- **Label 1**: Necrotic and Non-Enhancing Tumor Core
- **Label 2**: Peritumoral Edema
- **Label 4**: Enhancing Tumor

<img src="https://github.com/leovidith/Brain-Tumor-Segmentation-UNET/blob/master/Generalized%20Images/img5.png">

## Preprocessing Steps
1. **Data Normalization**:
   - Scaled pixel values to [0, 1] range using MinMaxScaler.
2. **Modality Selection**:
   - Retained T1ce and T2-FLAIR modalities for optimal performance.
3. **Resizing**:
   - Resized images to 128x128 for computational efficiency.
4. **Data Splitting**:
   - Split dataset into training (68%), validation (20%), and testing (12%).
5. **Data Augmentation**:
   - Applied transformations like rotations and resizing to enhance diversity.
  
  <img src="https://github.com/leovidith/Brain-Tumor-Segmentation-UNET/blob/master/Generalized%20Images/img4.png" width=400px>

## Model Architecture
The project employs a 2D U-Net architecture, featuring:

- **Encoder**:
  - Convolutional layers with ReLU activation and max-pooling for feature extraction.
- **Bottleneck**:
  - Dense layers capturing global context.
- **Decoder**:
  - Transposed convolutions for upsampling and skip connections to retain spatial information.
- **Output Layer**:
  - Softmax activation for multi-class segmentation.
 
<img src="https://github.com/leovidith/Brain-Tumor-Segmentation-UNET/blob/master/Generalized%20Images/model.png" height=1000px>

## Model Performance
**Accuracy and Loss Curves**:

- **Training Accuracy**: Showed steady improvement across epochs.
- **Validation Accuracy**: Plateaued without overfitting.
- **Loss**: Consistently decreased for both training and validation sets.

## Model Metrics
The following metrics were used to evaluate model performance:

- **Dice Coefficient**
- **Mean Intersection over Union (IoU)**
- **Accuracy**: Achieved a validation accuracy of approximately 92%.

  <img src="https://github.com/leovidith/Brain-Tumor-Segmentation-UNET/blob/master/Testing%20Image%20Strips%20-%20Set%202/img31.png">
  <img src="https://github.com/leovidith/Brain-Tumor-Segmentation-UNET/blob/master/Testing%20Image%20Strips%20-%20Set%202/img32.png">
  <img src="https://github.com/leovidith/Brain-Tumor-Segmentation-UNET/blob/master/Testing%20Image%20Strips%20-%20Set%202/img33.png">

## Sprints
1. **Sprint 1**: Data acquisition and preprocessing.
2. **Sprint 2**: Building and tuning the U-Net architecture.
3. **Sprint 3**: Model training with callbacks (e.g., early stopping, learning rate reduction).
4. **Sprint 4**: Performance evaluation and visualization of results.
5. **Sprint 5**: Model deployment and documentation.

## Conclusion
This project demonstrates the efficacy of the U-Net architecture in segmenting brain tumors from MRI scans. By automating the segmentation process, it enhances diagnostic accuracy and supports medical decision-making. Future directions could include:
