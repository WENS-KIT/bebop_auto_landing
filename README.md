![Logo_for_Git](https://github.com/WENS-KIT/Altitude-based-Automatic-Tiling-Algorithm-for-Small-Object-Detection/assets/96454461/c66d7644-a9b7-4d77-a0db-46105f4b0aaa)
<!-- change the link of the logo which on your repo. -->

## The [WENS](https://wens.kumoh.ac.kr/) is a  Wireless and Emerging Network System Laboratory at the [Kumoh National Institute of Technology](https://eng.kumoh.ac.kr/) in the Republic of Korea (South Korea). 

### Our research interests include signal processing, algorithm, protocol, and application of the wireless network & communication. Such as 
* Radio access technologies (RAT) for Beyond B5G/6G and Future Radio Access
* Unmanned Every Vehicle (UxV) such UAV, UGV, UUV, USV 
* Artificial Intelligence, Deep Learning  
* Augmented reality, Mixed reality 
* Embedded System / Internet of Things
* Wearable device & computing
* Wired/wireless network application   
### but not limited.

### <!-- Note here the introduce of the repo or docker image. -->

# Bebop Auto Landing with Aruco marker
This repository is for auto landing drone using Bebop2 with Aruco marker</br>  
What it Aruco marker?  
>**Reference** : [**ArUco Markers**](https://www.sciencedirect.com/science/article/pii/S0031320314000235) 
 
An ArUco marker is a synthetic square marker composed by a wide black border and an inner binary matrix which determines its identifier (id).  

</br>

<img src="https://user-images.githubusercontent.com/70830088/159876633-b1b468b5-bdbd-4b39-ac4f-e96a089403b0.jpg" title="ArUco Marker" alt="make" width="40%" height="40%"/>
<figcaption><b>Aruco marker  Ref : https://docs.opencv.org/4.x/d5/dae/tutorial_aruco_detection.html</b></figcaption>

</br>

# Environment
 > **Warning:** Bebop2 ROS package supports only ROS_kinetic (ubuntu 16.04)

[Bebop2 drone](https://www.amazon.com/Parrot-Bebop-2-Drone-White/dp/B0179JFAW2)  
Host Ubuntu 18.04  
Docker Ubuntu 16.04 ([nvidia/cudagl:10.2-devel-ubuntu16.04](https://hub.docker.com/r/nvidia/cudagl/tags?page=1&name=ubuntu16.04))  

</br>

# Installation

Bebop Autonomy ROS : https://github.com/AutonomyLab/bebop_autonomy  
ArUco Markers ROS : https://github.com/pal-robotics/aruco_ros

```bash
mkdir -p ~/catkin_ws/src && cd ~/catkin_ws/src

# Download bebop_autonomy ROS
git clone https://github.com/AutonomyLab/bebop_autonomy

# Install Aruco Marker ROS
git clone -b kinetic-devel https://github.com/pal-robotics/aruco_ros.git

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

cd ~/catkin_ws/src/bebop_auto_landing
python bebop_auto_landing.py
python bebop_test.py
```
</br>

# Paper
* 강호현, and 신수용. "[Aruco Marker 를 사용한 드론 정밀 착륙 시스템](https://www.dbpia.co.kr/pdf/pdfView.do?nodeId=NODE11024380&mark=0&useDate=&ipRange=N&accessgl=Y&language=ko_KR&hasTopBanner=true)" 한국통신학회논문지 47.1 (2022): 145-150.
