# Anomaly-Detection-Project
This project aims to detect anomalies from images and displays the detections on the images by drawing bounding boxes on it. This project also contains Annotation and Segmentation tools integrated into it, which enables users to modify annotations and segmentations predicted by the application. These images are stored and used for re-training of detection models to get higher accuracy.

This is frontend part of the project. For backend refer https://github.com/mkovelamudi/Anomaly-Detection-Backend.git

## Technoglies Used
### Front End
1. Front End - React
2. Annotation Tool - Streamlit
3. Segmentation Tool - Django
### Back End
Deployed on Nvidia Jetson Orin Nano device as edge node.
1. Gstreamer Pipeline - Pipeline to send camera video feed to image pipeline.
2. Nvidia Isaac ROS Image Pipeline - Processing and Detections on Images
3. Remote Control of the pipeline - Flask Server

## Architecture
![Architecture (3)](https://github.com/mkovelamudi/Anomaly-Detection-Frontend/assets/99615170/5c911b4c-4711-4ef6-b1a9-b3e16fb0c260)

## Project Flow
![FlowChart295B (1)](https://github.com/mkovelamudi/Anomaly-Detection-Frontend/assets/99615170/ec205ca6-4d65-4b16-9266-a29bc5829086)

# Setup
### Front End
```
git clone <this repo> # This clones web application and annotaiton tool
cd  Anomaly-Detection-Frontend/src/Frontend/
git clone https://github.com/Britefury/django-labeller.git # This clones segmentation tool
cd 295AnomalyDetection-main/
npm -i install # make sure npm is installed and use this command to install required packages
cd ../labeling-main/
pip install -r requirements.txt # install annotation tool requirements
pip install streamlit-img-label
cd ../django-labeller/
python setup.py install
pip install -r requirements.txt # install segmentation tool requirements
pip install django-labeller

# Launch 3 terminals

#1st terminal
cd ../295AnomalyDetection-main/
npm start # Launch main web application

#2nd terminal
cd ../labeling-main/
streamlit run app.py

#3rd terminal
cd ../django-labeller/
python simple_django_labeller/manage.py migrate
python simple_django_labeller/manage.py runserver
```
After following above instructions, the web application along with tools are launched.

We need to connect this frontend with backend image pipeline, follow instructions below

### Back End
https://github.com/mkovelamudi/Anomaly-Detection-Backend.git

# Results
### Home page
<img width="1439" alt="Home Page" src="https://github.com/mkovelamudi/Anomaly-Detection-Frontend/assets/99615170/e4ec1a8e-ffc2-47ef-b74b-be8c177d13d0">

### Start Pipeline
This image shows the dialog box to start the pipeline on Jetson device with desired model.
<img width="1440" alt="Start pipeline" src="https://github.com/mkovelamudi/Anomaly-Detection-Frontend/assets/99615170/3274944b-ce1d-433c-85cd-7fa6d66885e8">

### Pipeline start successful
This image displays the success message of pipeline start
<img width="1440" alt="pipeline start" src="https://github.com/mkovelamudi/Anomaly-Detection-Frontend/assets/99615170/fc67aace-944b-469f-b1ef-08e3e11e02d8">

### Live Anomaly Detections Streaming
These images show the processed detections on frames
<img width="1440" alt="streaming1" src="https://github.com/mkovelamudi/Anomaly-Detection-Frontend/assets/99615170/1b0854a0-1809-4b3a-aa21-7681444e9f5d">

<img width="1440" alt="streaming2" src="https://github.com/mkovelamudi/Anomaly-Detection-Frontend/assets/99615170/3845f44d-a12f-4630-ba9f-f89e24ea346f">

### Images with detections saved in S3
This image displays the list of images stored in S3 bucket after processing, we can view each image by clicking on it.
<img width="1438" alt="Predicted detections" src="https://github.com/mkovelamudi/Anomaly-Detection-Frontend/assets/99615170/990ef16d-7061-47bf-b230-e4d7a4fbc659">

### Report Predicted Detections
This image displays the report detection option for the predicted image
<img width="1440" alt="Report" src="https://github.com/mkovelamudi/Anomaly-Detection-Frontend/assets/99615170/40c573c2-6035-4b5d-b23f-009e6c39fca7">

### Annotation Tool
This image displays the Annotation tool after selecting report annotation option
<img width="1440" alt="Annotation" src="https://github.com/mkovelamudi/Anomaly-Detection-Frontend/assets/99615170/716aab3b-230a-4502-be8f-4ab001d80ece">

### Segmentation Tool
This image displays the Segmentation tool after selecting report segmentation option
<img width="1437" alt="Segmentation" src="https://github.com/mkovelamudi/Anomaly-Detection-Frontend/assets/99615170/c33101af-bb6c-466a-b6eb-b05da9473405">

### New model upload from S3
This image displays the upload new model option
<img width="1439" alt="Copy new model" src="https://github.com/mkovelamudi/Anomaly-Detection-Frontend/assets/99615170/6fdd7258-cf57-4cca-932f-a3fbc2497150">







