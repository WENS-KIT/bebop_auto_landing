# Bebop Auto Landing with Aruco marker
This repository is for auto landing drone using Bebop2 with Aruco marker  
What it Aruco marker?  
>**Reference** : [ArUco Markers](https://docs.opencv.org/4.x/d5/dae/tutorial_aruco_detection.html) 
 
An ArUco marker is a synthetic square marker composed by a wide black border and an inner binary matrix which determines its identifier (id).   


<p align="center">
    <img src="https://user-images.githubusercontent.com/70830088/159876633-b1b468b5-bdbd-4b39-ac4f-e96a089403b0.jpg" title="ArUco Marker" alt="make" width="40%" height="40%"/>
</p>
</br>

# Environment
 > **Warning:** Bebop2 ROS package supports only ROS_kinetic (ubuntu 16.04)

[Bebop2 drone](https://www.amazon.com/Parrot-Bebop-2-Drone-White/dp/B0179JFAW2)  
Host Ubuntu 18.04  
Docker Ubuntu 16.04 ([nvidia/cudagl:10.2-devel-ubuntu16.04](https://hub.docker.com/r/nvidia/cudagl/tags?page=1&name=ubuntu16.04))  

</br>

# Installation

Bebop Autonomy ROS : https://github.com/AutonomyLab/bebop_autonomy  
ArUco Markers ROS : https://github.com/UbiquityRobotics/fiducials

```bash
mkdir -p ~/catkin_ws/src && cd ~/catkin_ws/src

# Download bebop_autonomy ROS
git clone https://github.com/AutonomyLab/bebop_autonomy

# Install Aruco Marker ROS
git clone -b kinetic-devel https://github.com/UbiquityRobotics/fiducials.git

git clone https://github.com/WENS-KIT/bebop_auto_landing.git
cd ..
catkin_make
```
</br>

# Usage

```bash
source ~/catkin_ws/devel/setup.bash

roslaunch bebop_driver bebop_nodelet.launch
roslaunch aruco_ros single.launch
python bebop_auto_landing.py
python bebop_test.py
```
</br>

# Paper
* 강호현, and 신수용. "[Aruco Marker 를 사용한 드론 정밀 착륙 시스템](https://www.dbpia.co.kr/pdf/pdfView.do?nodeId=NODE11024380&mark=0&useDate=&ipRange=N&accessgl=Y&language=ko_KR&hasTopBanner=true)" 한국통신학회논문지 47.1 (2022): 145-150.


bebop autonomy & arucomaker 서브모듈 추가하기
