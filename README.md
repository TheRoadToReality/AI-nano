<H1 align="center">


<H1 align="center">

## 安装Miniconda
```
bash Miniconda3-latest-Linux-aarch64.sh 
```
添加conda到环境变量
```
export PATH="/home/chench/miniconda/bin:$PATH"
```
创建一个名叫yes的环境
```
conda create -n yes python=3.8
```
激活该环境
```
conda activate yes
```
## 安装ROS/Mavlink/MavROS(Ubuntu18.04)

```
sudo apt-get install ros-melodic-mavros ros-melodic-mavros-extras
```
```
wget https://raw.githubusercontent.com/mavlink/mavros/master/mavros/scripts/install_geographiclib_datasets.sh
sudo bash ./install_geographiclib_datasets.sh   
```
```
mkdir -p ~/catkin_ws/src
cd ~/catkin_ws
catkin init
wstool init src
```
```
sudo apt-get install python-catkin-tools python-rosinstall-generator -y
```
```
$ wstool init ~/catkin_ws/src
```
```
rosinstall_generator --rosdistro melodic mavlink | tee /tmp/mavros.rosinstall
```
```
rosinstall_generator --upstream mavros | tee -a /tmp/mavros.rosinstall
```
```
wstool merge -t src /tmp/mavros.rosinstall
wstool update -t src -j4
rosdep install --from-paths src --ignore-src -y
```
```
./src/mavros/mavros/scripts/install_geographiclib_datasets.sh

```
```
catkin build
```
```
source devel/setup.bash
```
## 运行代码
- 安装依赖
```
Sudo pip install -r requirement.txt
```
-运行代码
```
python Jeston\YOLOv8-DeepSORT-Object-Tracking-main\ultralytics\yolo\v8\detect source=0 show=ture
```
## 装配操作
-Jeston nano连接Pixhawk所需引脚
![](./figure/nano.png)
-6p端子线剪成3p保留RX TX GND
![](./figure/接Telem2线.png)
-焊接杜邦线后，RX接TX，TX接RX，GND接GND
![](./figure/755acb392c7e90d195f0389826a685e.jpg)
![](./figure/eff90ce5a0f1c483cdd52401d67d646.jpg)
##(Jeston nano)安装px4依赖库
```
sudo apt-get install python3-pip
```
![](./figure/eff90ce5a0f1c483cdd52401d67d646.jpg)
