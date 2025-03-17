# Pedestrian Detection & Tracking using Classical Computer Vision  

## Project Overview  
This project aims to **detect and track pedestrians in crowded scenes** using **classical computer vision techniques**, without relying on deep learning. The goal is to explore whether traditional feature-based methods can provide a computationally efficient alternative for pedestrian tracking while handling **scale variations, occlusions, and dynamic backgrounds**.  

The project includes **three major components**:  
1. **Pedestrian Detection** (Feature-Based & Motion-Based).  
2. **Tracking & Identity Assignment** (Motion Prediction & Data Association).  
3. **Evaluation & Performance Analysis** (Detection & Tracking Metrics).  

**No deep learning required** – making it efficient for real-time and low-power applications.  

## Methodologies
1. Pedestrian Detection using HOG + SVM
  - Uses Histogram of Oriented Gradients (HOG) to extract edge and shape features.
  - Support Vector Machine (SVM) classifies regions as pedestrians or non-pedestrians.
  - The image is scanned at multiple scales to capture pedestrians at different distances.

2. Pedestrian Detection and Tracking using HOG + Centroid Tracking
  - Detects pedestrians using HOG + SVM.
  - Tracks pedestrians by computing the centroid of each bounding box and associating centroids across frames using Euclidean distance.

3. Hybrid Model: MOG2 + HOG + Kalman Filter + Hungarian Algorithm + Bhattacharyya Distance

  - Background Subtraction (MOG2): Removes static elements to isolate moving objects.
  - HOG + SVM: Refines pedestrian detection using feature-based analysis.
  - IoU Filtering: Merges overlapping detections from MOG2 and HOG to improve accuracy.
  - Kalman Filter: Predicts the future positions of pedestrians based on their motion, ensuring smooth tracking even during occlusions.
  - Hungarian Algorithm: Optimally matches new detections to existing tracks using a cost matrix based on spatial and appearance similarities.
