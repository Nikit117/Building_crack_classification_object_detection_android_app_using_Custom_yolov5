# Building_crack_object_detection_android_app_using_Custom_Yolov5

## YOLOv5 Object Detection for Crack Classification

This project aims to detect and classify cracks in images using a custom YOLOv5 object detection algorithm. The crack classification is divided into three categories: minor, moderate, and severe. The YOLOv5 model has been customized by modifying the `yolov5s.yaml` configuration file. The model is trained on a custom dataset of crack images, which was created by collecting images from various sources.

The project includes an Android application that allows users to capture images of cracks and classify them using the custom YOLOv5 model. The application is built using Android Studio and is available in the form of an APK, which can be downloaded from this [link](https://github.com/Nikit117/Building_crack_object_detection_android_app_using_Custom_yolov5/blob/main/apk.rar).


## Installation

To use this project, you will need to have Python 3.7 or higher installed on your system. You can install the required Python libraries by running the following command:

```python
pip install -r requirements.txt
```


## Customization

The YOLOv5 model has been customized by modifying the `yolov5s.yaml` configuration file. The modifications include changing the number of classes to 3, adding the `focal loss` function, and changing the anchor box sizes to better fit the crack images.

## Training

To train the custom YOLOv5 model, you can use the `train.py` script. The script takes the custom `yolov5s.yaml` configuration file and the path to the training and validation datasets as input. Here's an example:

```python
python train.py --img 640 --batch 16 --epochs 50 --data data.yaml --cfg yolov5s.yaml --weights yolov5s.pt --name crack_detection
```

This will train the custom YOLOv5 model on the `data.yaml` dataset for 50 epochs, using a batch size of 16 and an image size of 640. The trained weights will be saved in the file `crack_detection.pt`.

## Conversion to TFLite Model

After training the model, it is converted to a TFLite model for use in the Android application. The conversion is done using the export.py script. Here's an example:

```python
python export.py --weights crack_detection.pt --img 640 --cfg yolov5s.yaml --name crack_detection --quant --tfl-int8 --simplify
```
This will convert the trained YOLOv5 model to a TFLite model with int8 quantization and model simplification.

## Android Application

The Android application allows users to capture images of cracks and classify them using the custom YOLOv5 model. The application is built using Android Studio and is available in the form of an APK, which can be downloaded from this link.

Here are the steps to use the Android application:

1. Download and install the APK on your Android device.
2. Open the application and grant camera permissions.
3. Point the camera at the crack you want to classify.
4. Press the capture button to take a photo.
5. The application will display the detected objects and their classifications.

## Dataset

The custom dataset used to train the YOLOv5 model was created by collecting images from various sources. The dataset contains images of cracks of various types and severities. The images were manually annotated to create bounding boxes around the cracks and assign them a classification label.

## Acknowledgments

This project was inspired by the ```YOLOv5``` repository by Ultralytics. 
