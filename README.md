# Explainable-Autonomous-Driving-Object-Detection-Using-Yolov5-Model-and-D-RISE-XAI-Technique
<img width="1071" alt="Screen Shot 2024-10-06 at 5 46 22 PM" src="https://github.com/user-attachments/assets/24131edc-331d-4241-a012-3ecc5f44f9ba">

## Introduction
This notebook delves into the interpretability of object detection models, specifically within the context of autonomous driving. In this study, I use the [YOLOv5](https://github.com/ultralytics/yolov5) model, a state-of-the-art object detection algorithm, to analyze two sample images from the widely used [KITTI](https://www.cvlibs.net/datasets/kitti/eval_object.php?obj_benchmark=2d) dataset, which captures real-world driving scenarios, including various objects like cars and pedestrians. The KITTI dataset provides a diverse and challenging environment, making it ideal for evaluating object detection models in autonomous driving tasks.

The notebook is structured into two main phases. First, I test the performance of a pre-trained YOLOv5 model by running inference on the two selected images. This initial evaluation assesses YOLOv5’s ability to accurately detect and localize key objects in complex driving scenes. Next, I apply the D-RISE (Detector Randomized Input Sampling for Explanation) technique to generate visual explanations for YOLOv5's predictions on these images. D-RISE works by masking random parts of the input images and measuring the impact on detection confidence, ultimately producing heatmaps that reveal the most influential regions for each detected object.

By combining YOLOv5’s detection capabilities with the interpretability offered by D-RISE, this notebook provides a comprehensive analysis of the model’s decision-making process. The goal is to enhance transparency and trust in object detection models used in autonomous vehicles, offering insights into how the model prioritizes different regions of an image during detection. This can lead to improved safety and reliability in real-world driving applications, making the integration of explainable AI techniques critical in autonomous driving systems.

### Object Detection Performance Using Pre-Trained Yolov5

#### Example 1
Original Image 007480
![007480_original](https://github.com/user-attachments/assets/c2ef44e8-000b-451e-b12e-58fba3c2888c)

Object Detection on Image 007480
![007480_detection](https://github.com/user-attachments/assets/0e4134c1-e4e5-4458-bbac-79e460afa4b6)

#### Example 2
Original Image 000015
![000015_original](https://github.com/user-attachments/assets/2eee4220-caed-4993-97de-a6b15b28895a)

Object Detection on Image 000015
![000015_detection](https://github.com/user-attachments/assets/45fed558-92cf-422f-8752-75885eec9594)

### D-RISE for Explainability

D-RISE (Detector Randomized Input Sampling for Explanation) is an explainability technique specifically designed for object detection models. It builds upon the original RISE method, which creates visual explanations for image classifiers by analyzing how randomly masked versions of the input image affect the model’s output. D-RISE extends this concept to object detection by generating heatmaps that highlight the importance of different regions in an image for detecting specific objects. By randomly masking parts of the input and observing the resulting changes in detection confidence, D-RISE provides insights into which parts of the image are most influential for each detected object.

Here we implement this technique to help explain the decisions made by YOLOv5, aiming to make the models more interpretable and trustworthy for critical applications like autonomous driving.

#### Example 1
Sample explainability on Image 007480
<img width="593" alt="Screen Shot 2024-10-06 at 5 53 38 PM" src="https://github.com/user-attachments/assets/984a9eba-5e48-4e63-bec4-cd0bb2276ffa">

Sample explainability on Resized Image 007480
<img width="491" alt="Screen Shot 2024-10-06 at 5 52 52 PM" src="https://github.com/user-attachments/assets/75a434ed-bbc5-433f-9800-51912ad4d5d6">

#### Example 2
Sample explainability on Image 000015
<img width="667" alt="Screen Shot 2024-10-06 at 5 50 24 PM" src="https://github.com/user-attachments/assets/54aa1d82-ba61-4d55-8983-8704d92714d8">

Sample explainability on Resized Image 000015
<img width="1071" alt="Screen Shot 2024-10-06 at 5 46 22 PM" src="https://github.com/user-attachments/assets/24131edc-331d-4241-a012-3ecc5f44f9ba">
