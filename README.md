# DSC4310-Seals
Repository for Dr. Rivas' semester-long project in DSC 4310 | Leopard Seals Identification


Leopard seals (Hydrurga leptonyx) play a critical role as apex predators in the
Antarctic ecosystem, yet studying them poses difficulties due to their elusive nature.
Traditional monitoring methods require a large amount of time and effort while
providing limited contributions. To address this issue, our project explores utilizing
deep learning models for seal identification in photos, offering a noninvasive
approach to wildlife monitoring.

Our framework combines Meta AI’s Segment Anything Model (SAM) (Alexan-
der Kirillov, 2023) with Bootstrap Your Own Latent (BYOL) (Grill et al., 2020).
SAM is used to isolate seals from their backgrounds, emphasizing relevant features
and generating more consistent inputs for the learning pipeline. The segmented im-
ages are then passed into BYOL, which uses two neural networks that interact and
learn visual representations from each other. BYOL helps the model distinguish
features that identify individual seals using image augmentation techniques like
rotation, cropping, and color jitter. Embeddings are then extracted and evaluated
using a similarity search to produce accuracy scores.

We tested four model variations: SAM + YOLO8, YOLO8, YOLO9, and YOLO10.
YOLO10 achieved the best performance across all metrics, with a Top-1 accuracy
of 8.05%, Top-5 accuracy of 18.38%, Top-10 accuracy of 26.29%, an F1 Score of
0.0773, and a balanced accuracy of 4.65%. While SAM successfully segmented
some seals from complex backgrounds, its integration with YOLO8 did not improve
identification performance, highlighting the need to further refine the segmentation
process to ensure consistency and preserve critical features required for individual
recognition. Our contribution lies in designing and evaluating a deep learning
approach to wildlife identification that is scalable and noninvasive. Future work will
focus on improving the segmentation process, exploring the addition of supervised
learning components, and incorporating explainability tools to better understand
the features driving seal recognition
