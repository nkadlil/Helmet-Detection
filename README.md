# Helmet Detection Using Jetson Nano
This is my project title for Deep Learning in Intelligent Video Analytics and Computer Vision Workshop in IIUM.

This project is using the Yolov5 and it is deployed at the Jetson Nano. The framework that I used is the Pytorch and the model is trained in Google Colab
# Hardware Requirement
1. Jetson Nano 2GB
2. 5V DC Barrel jack (or Micro-USB power supply)
3. MicroSD card (32GB UHS-1 minimum recommended)
4. Logitech C270 HD Webcam
5. Mouse and Keyboard
6. Monitor
7. DisplayPort connector
# Dataset
I have collected a total of 600 datasets. Half of the datasets is collected by using Google and Kaggle website and the other half is form my own cam.
## Dataset Annotation 
The dataset are being annotated using Roboflow. The classes are Helmet and No Helmet. 
## Training model
The Yolo training is done in the Google Colab and the model is saved as a pt file.
This pt file will be copied into the Jetson Nano for inference later.
# Steps :
## 1. Create a new fresh environment with Python Version 3.8
`conda create -n myenv python=3.8`
## 2. Clone the YoloV5 repo
   -  Create a folder for the project and cd into the folder
   - `git clone https://github.com/ultralytics/yolov5`
   - `cd yolov5`
## 3. Modify requirements.txt
   - Locate and open YoloV5 directory
   - Open requirements.txt using text editor
   - Comment #torch>=1.7.0 and #torchvision>=0.8.1
   - run - `pip install -r requirements.txt`
## 4. Install PyTorch
   - `git clone --recursive --branch 1.7 http://github.com/pytorch/pytorch`
   - `cd pytorch`
   - `python3.8 -m pip install -r requirements.txt`
   - `python3.8 setup.py install`
 ## 5. Install torchvision
   - Pre-install some required lib `sudo apt-get install libjpeg-dev zlib1g-dev libpython3-dev libavcodec-dev libavformat-dev libswscale-dev`
   - Git clone the torchvision repo: `git clone --branch v0.5.0 https://github.com/pytorch/vision torchvision`
   - Cd into the vision folder: `cd torchvision/`
   - Run the setup.py: `python setup.py install`
   
## Check GPU 
1. cd to HOME
2. Activate python3 by inserting `python3`
3. `import torch`
4. `torch.cuda.is_available()`
5. `torch.cuda.current_device()`
6. `torch.cuda.device(0)`
7. `torch.cuda.device_count()`
8. `torch.cuda.get_device_name(0)`

## Running the Inference
1. Activate the environment `source activate 'name env' `
2. Cd into your folder project and yolov5 directory.
3. Copy the trained yolo file which is the pt file and paste into the "models" folder under the "Yolov5" directory.
4. Run the inference: `python detect.py --weights ./models/model.pt --conf 0.45 --source 0` 

#model.pt is the name of the model
#conf is the min confidence level for detection 
#source 0 will use the webcam
#source image.jpg for image inference
#source video.mp4 for video inference

## Appreciation
I would like to thank all lecturers, facilitators, friends and family for helping me to develop the project. Any kind of improvement or suggestions are most welcomed.
   
   
   
   
   
   
   
   
   
