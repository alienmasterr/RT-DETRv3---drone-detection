# RT-DETRv3---drone-detection

Training RT-DETRv3 for drone detection on real and synthetic data

Title: INVESTIGATING MIXED LEARNING ON REAL AND SYNTHETIC DATA TO IMPROVE UAV RECOGNITION ACCURACY USING TRANSFORMER MODELS

Objective: To determine whether combining real and synthetic data enhances the accuracy and reliability of UAV recognition in transformer-based architectures under limited training sample conditions.

Hypothesis: Incorporating synthetic data during the training process can improve the quality of UAV recognition in transformer models.

Dataset: The selected dataset was sourced from the Kaggle platform. It consists of aerial vehicle imagery (drones, airplanes, helicopters) along with corresponding annotations (including bounding boxes and class labels) and is pre-split into training, testing, and validation sets.

For the specific task of drone detection, we employ binary labeling—"drone" and "not_drone"—by remapping the original classes accordingly.

Model Selection: RT-DETRv3

We selected the RT-DETRv3 model for this research. Key advantages and architectural features include:

First True Real-Time Transformer: It bridges the gap between the high accuracy of Transformers and the real-time processing speeds required for critical UAV detection.

Hybrid Architecture (CNN + Transformer): Utilizes an auxiliary CNN branch during training to enhance feature extraction, effectively "teaching" the encoder to capture fine-grained object details.

Enhanced Dense Supervision: Addresses the primary limitation of classic DETR models (slow convergence due to sparse positive samples) through innovative label assignment strategies.

Self-Attention Strategy: Implements a training strategy that diversifies the decoder's input, making the model more robust in complex visual environments.

Training-Only Enhancements: All architectural improvements are implemented in training-only modules. This ensures higher accuracy without increasing inference latency.

Outperforms YOLOv10: Demonstrates superior AP (Average Precision) compared to the latest YOLO models while maintaining competitive real-time speeds.

Current Performance Metrics (Trained on Real Data)

Metric,Value

mAP@50:95,0.6326

mAP@50,0.9532

mAP@75,0.6803

mAP_small,0.5904

mAP_medium,0.6329

mAP_large,0.8297

AP50_drone,0.9532

AP50_not_drone,0.9532

Classification Experiment

Additionally, the model was trained on a multi-class classification task as an experiment to verify its versatility beyond detection. The results confirmed high performance across various aircraft types:

Metric,Value

mAP@50:95,0.6831

mAP@50,0.9765

mAP@75,0.7638

mAP_small,0.5903

mAP_medium,0.6788

mAP_large,0.9178

AP50_drone,0.9765

AP50_airplane,0.9765

AP50_helicopter,0.9765


