# SVM

This is the repository of the feasibility test of pedestrian classification  using Support Vector Machine.

# Install & Build
```bash
$ cd catkin_ws/src
// Install prerequisite packages 
$ git clone https://github.com/wg-perception/people.git
$ git clone https://github.com/DLu/wu_ros_tools.git
$ sudo apt-get install ros-kinetic-bfl
// The core 
$ git clone https://github.com/yzrobot/online_learning
// Build
$ cd catkin_ws
$ catkin_make
```

# Run
After catkin_make succeed, modify 'line 3' of online_learning/object3d_detector/launch/object3d_detector.launch, and make the value is the path where your bag files are located:

`<arg name="bag" value="/home/yq/Downloads/LCAS_20160523_1200_1218.bag"/>`

The bag file offered by [Lincoln Centre for Autonomous Systems](http://lcas.lincoln.ac.uk) is in velodyne_msgs/VelodyneScan message type, so we would need related velodyne packages in ROS:
```bash
$ sudo apt-get install ros-kinetic-velodyne*
```
Now, the svm should be able to run:
```bash
$ cd catkin_ws
$ source devel/setup.bash
$ roslaunch object3d_detector object3d_detector.launch
```
# Citation
If you are considering using this code, please reference the following:
```
@inproceedings{yz17iros,
   author = {Zhi Yan and Tom Duckett and Nicola Bellotto},
   title = {Online learning for human classification in {3D LiDAR-based} tracking},
   booktitle = {In Proceedings of the 2017 IEEE/RSJ International Conference on Intelligent Robots and Systems (IROS)},
   pages = {864--871},
   address = {Vancouver, Canada},
   month = {September},
   year = {2017}
}
```
