# QCar_localization

本仓库为铁道出版社《自动驾驶决策规划技术理论与实践》第11.2小节，定位模块的附录代码。

## 使用

安装依赖：

```
sudo apt-get update
sudo apt-get install ros-$ROS_DISTRO-navigation ros-$ROS_DISTRO-robot-localization ros-$ROS_DISTRO-rplidar-ros
```

将[rf2o_laser_odometry](https://github.com/MAPIRlab/rf2o_laser_odometry)克隆到工作空间目录内，并编译工作空间：

```
cd ~/catkin_ws/src
git clone https://github.com/MAPIRlab/rf2o_laser_odometry.git
cd ../
catkin_make
```


运行`mapping.launch`文件，移动QCar对场地进行探索，建立地图：

```
roslaunch qcar_localization mapping.launch
```

使用如下命令将地图保存到 `qcar_localization/map/` 目录下：

```
rosrun map_server map_saver -f ~/catkin_ws/src/qcar_localization/map/map.yaml
```

运行`localization.launch`运行里程计及粒子滤波节点定位：
```
roslaunch qcar_localization localization.launch
```
