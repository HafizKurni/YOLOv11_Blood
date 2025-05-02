# Blood Cell Detection Using YOLOv10n and YOLOv11n

This repository contains the code, results, and analysis from a comparative study of two object detection models — **YOLOv10n** and **YOLOv11n** — applied to the task of **blood cell detection**. The models were evaluated based on detection accuracy, inference speed, training time, and model complexity using a public dataset.

## 📌 Abstract

Object detection in medical imaging plays a vital role in improving diagnostic accuracy and clinical workflow. This study evaluates the performance of YOLOv10n and the latest YOLOv11n on a blood cell detection dataset. YOLOv11n achieved higher accuracy (mAP50: 92.8%, mAP50-95: 65.2%) compared to YOLOv10n (mAP50: 91.2%, mAP50-95: 63.5%). However, YOLOv10n delivered faster inference and postprocessing times, making it more suitable for real-time applications. This comparison provides insight into model selection for medical imaging tasks with different deployment constraints.

## 📂 Dataset

- Source: [Blood Cell Detection Dataset on Kaggle](https://www.kaggle.com/datasets/adhoppin/blood-cell-detection-datatset)
- Classes: Platelets, Red Blood Cells (RBC), White Blood Cells (WBC)
- Format: COCO-style annotations

## ⚙️ Methodology

1. **Data Collection**  
   The dataset was sourced from Kaggle, consisting of annotated microscopic blood cell images.

2. **Data Preprocessing**  
   Images were resized to 640x640 pixels, and annotations were formatted to match YOLO requirements.

3. **Model Selection**  
   - YOLOv10n: Efficient model with 8.2 GFLOPs  
   - YOLOv11n: Latest state-of-the-art model released by Ultralytics in Sept 2024, with 6.3 GFLOPs

4. **Training**  
   - Both models trained for 100 epochs  
   - Device: Tesla P100 16GB GPU  
   - Framework: Ultralytics YOLOv8 implementation

5. **Evaluation Metrics**  
   - Precision, Recall  
   - mAP50 and mAP50-95  
   - Inference and postprocessing speed  
   - Training time and model size

## 📊 Results Summary

| Model     | mAP50 | mAP50-95 | Precision | Recall | Training Time | Inference (ms) | Postprocess (ms) | Size |
|-----------|--------|-----------|------------|--------|----------------|----------------|-------------------|------|
| YOLOv10n  | 0.9120 | 0.6347    | 0.836      | 0.890  | 22.5 minutes   | 7.00           | 0.90              | 5.8MB |
| YOLOv11n  | 0.9279 | 0.6524    | 0.847      | 0.896  | 18.7 minutes   | 11.35          | 8.64              | 5.5MB |

## 📌 Conclusion

YOLOv11n offers improved accuracy and model efficiency compared to YOLOv10n, making it suitable for high-accuracy tasks. However, YOLOv10n remains favorable for applications requiring faster inference. The model choice should be based on specific deployment needs — whether accuracy or real-time performance is prioritized.
