# DualA-Net: Image Segmentation Model Implementation

Medical image segmentation is a crucial tool in healthcare, essential for early disease detection and diagnosis. However, existing models struggle to balance accuracy, adaptability, and computational efficiency, limiting their application across various medical image segmentation tasks.

This project explores **DualA-Net**, a novel deep-learning architecture designed to enhance segmentation accuracy while maintaining computational efficiency. The model was evaluated on the **CHASE DB1** dataset, demonstrating its ability to closely replicate ground truth segmentation masks. These findings highlight the potential of DualA-Net for real-world medical applications.

**Based on Research Paper:**  
[DualA-Net for Medical Image Segmentation](https://www.sciencedirect.com/science/article/abs/pii/S0169260723005436)

---

## DualA-Net Architecture  
![Screenshot 2025-03-17 104509](https://github.com/user-attachments/assets/a24a55f2-bce5-43c6-9346-157fad7598b0)

### 🔹 Key Components:  
- **Dual-branch encoder** (for downsampling)  
- **Multi-scale skip connections**  
- **Adaptive Region Field Selection Decoder (ARFSD)** (for upsampling)  

---

## Dataset  
- **Dataset:** CHASE_DB1 (Retinal vessel segmentation dataset)  
- **Source:** [Download here](https://researchdata.kingston.ac.uk/96/)  
- **Description:** 28 images, collected from both left and right eyes of 14 children.  
- **Image Size:** 3 × 999 × 960 pixels  

---

## Implementation Details  
| Parameter         | Value                                  |
|------------------|--------------------------------------|
| **Loss Function** | BCE Dice loss (0.5 * BCE + Dice loss) |
| **Optimizer**     | Adam                                  |
| **Learning Rate** | 0.001                                 |
| **Epochs**       | 75                                    |
| **Batch Size**    | 4                                     |
| **Augmentation**  | Random 90° rotation, flip, HSE, brightness, contrast adjustment |

### Data Split  
| Split        | Number of Images |
|-------------|----------------|
| **Training**   | 18 (with random augmentations applied at every epoch) |
| **Validation** | 5  |
| **Testing**    | 5  |

---

## Model Evaluation  
| Metric       | Score (%) |
|-------------|----------|
| **Accuracy**  | 96.69%  |
| **IoU**       | 60.80%  |
| **Dice Score** | 72.78%  |
| **Precision**  | 80.19%  |
| **Sensitivity** | 70.89%  |
| **Specificity** | 98.66%  |

![test (1)](https://github.com/user-attachments/assets/eef7901e-7bb8-471d-b8fa-36b52a57befd)

