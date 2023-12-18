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


