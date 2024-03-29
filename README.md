# raspberrypi-mnist
This is a method of recognizing handwritten numbers using Raspberry Pi 3/4.


## Training Data

<center> Mnist Dataset </center>

![image](https://github.com/everylumi/raspberrypi-mnist/blob/main/doc/MnistExamples.png)


## requirements 

- Raspberry Pi 3 or 4
- Raspberry Pi OS buster (recommended)
- Python 3.7(32bit), Python 3.9(64bit), 
- OpenCV 4
- TensorFlow 2.1.0 or above


## Pre Configuation after Raspi OS  
:GPU Memory Up to 128  
sudo raspi-config -> Performance Options -> GPU Memory -> input 128  

#### In case of raspberry pi 4
- EEPROM Check  
   sudo rpi-eeprom-update  -> check, BOOTLOADER: up to date  
- EEPROM Update  
   sudo rpi-eeprom-update -a && reboot  

## Installation

#### Step 1 clone repository
```sh
cd ~
git clone https://github.com/everylumi/raspberrypi-mnist.git
cd raspberrypi-mnist
```

#### Step 2 update Raspberry Pi OS to install OpenCV/TensorFlow
```sh
sudo apt update
sudo apt upgrade
```

#### Step 3 install OpenCV (skip, if installed already) 
```sh
bash get_pi_requirements_opencv.sh
pip3 install opencv-python==4.5.3.56 
```

#### Step 4 install tensorflow (skip, if installed already) 
```sh
pip3 install tensorflow

bash install_tensorflow-2.4.0.sh  --> don't use, error occur

# for OS bullseye - 64bit only
bash install_tensorflow-2.6.0.sh  --> don't use, error occur
```  
FYI, tensorflow releases  
https://github.com/lhelontra/tensorflow-on-arm/releases  
https://github.com/KumaTea/tensorflow-aarch64/releases    


#### Step 5 check version
```
python3
>>> import cv2
>>> cv2.__version__
>>> import tensorflow as tf
>>> tf.__version__
```


## Usage
```sh
cd ~/raspberrypi-mnist
python3 TFLite_mnist_webcam.py --modeldir=mnist_model
```


## Screenshot
![image](https://github.com/everylumi/raspberrypi-mnist/blob/main/doc/2021-11-21.png)


## License  
This project is licensed under the terms of the MIT license.