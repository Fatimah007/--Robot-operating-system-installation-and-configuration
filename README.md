//Install ROS and running robotic arm.
fatimah@fatimah-VirtualBox:~$ sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
fatimah@fatimah-VirtualBox:~$ sudo apt-key adv --keyserver 'hkp://keyserver.ubuntu.com:80' --recv-key C1CF6E31E6BADE8868B172B4F42ED6FBAB17C654
fatimah@fatimah-VirtualBox:~$ apt-get update
fatimah@fatimah-VirtualBox:~$ sudo apt-get install ros-melodic-desktop-full
fatimah@fatimah-VirtualBox:~$ apt-cache search ros-melodic
fatimah@fatimah-VirtualBox:~$ echo "source /opt/ros/melodic/setup.bash" >> ~/.bashrc
fatimah@fatimah-VirtualBox:~$ source ~/.bashrc
fatimah@fatimah-VirtualBox:~$ sudo apt install python-rosdep python-rosinstall python-rosinstall-generator python-wstool build-essential
fatimah@fatimah-VirtualBox:~$ sudo apt install python-rosdep
fatimah@fatimah-VirtualBox:~$ sudo rosdep init
fatimah@fatimah-VirtualBox:~$ rosdep update
fatimah@fatimah-VirtualBox:~$ sudo apt-get install ros-noetic-catkin
fatimah@fatimah-VirtualBox:~$ mkdir -p ~/catkin_ws/src
fatimah@fatimah-VirtualBox:~$ cd ~/catkin_ws/
fatimah@fatimah-VirtualBox:~/catkin_ws$ catkin_make
fatimah@fatimah-VirtualBox:~/catkin_ws$ cd ~/catkin_ws/src
fatimah@fatimah-VirtualBox:~/catkin_ws/src$ git clone https://github.com/smart-methods/arduino_robot_arm.git
fatimah@fatimah-VirtualBox:~/catkin_ws/src$ cd ~/catkin_ws
fatimah@fatimah-VirtualBox:~/catkin_ws$ rosdep install --from-paths src --ignore-src -r -y
fatimah@fatimah-VirtualBox:~/catkin_ws$ sudo apt-get install ros-melodic-moveit
fatimah@fatimah-VirtualBox:~/catkin_ws$ sudo apt-get install ros-melodic-joint-state-publisher ros-melodic-joint-state-publisher-gui
fatimah@fatimah-VirtualBox:~/catkin_ws$ sudo apt-get install ros-melodic-gazebo-ros-control joint-state-publisher
fatimah@fatimah-VirtualBox:~/catkin_ws$ sudo apt-get install ros-melodic-ros-controllers ros-melodic-ros-control
fatimah@fatimah-VirtualBox:~/catkin_ws$ sudo nano ~/.bashrc
In new Terminal 
fatimah@fatimah-VirtualBox:~$ sudo nano ~/.bashrc
[sudo] password for fatimah:
at the end of the (bashrc) file add the follwing line
(source /home/fatimah/catkin_ws/devel/setup.bash)
then 
ctrl + o
Enter then ctrl + x
fatimah@fatimah-VirtualBox:~$ source ~/.bashrc
fatimah@fatimah-VirtualBox:~$ roslaunch robot_arm_pkg check_motors.launch
... logging to /home/fatimah/.ros/log/2f61cbac-d4f8-11eb-a023-08002747c0bb/roslaunch-fatimah-VirtualBox-2823.log
Checking log directory for disk usage. This may take a while.
Press Ctrl-C to interrupt
Done checking log file disk usage. Usage is <1GB.

started roslaunch server http://fatimah-VirtualBox:33581/

SUMMARY
========

PARAMETERS
 * /robot_description: <?xml version="1....
 * /rosdistro: melodic
 * /rosversion: 1.14.11

NODES
  /
    joint_state_publisher_gui (joint_state_publisher_gui/joint_state_publisher_gui)
    robot_state_publisher (robot_state_publisher/state_publisher)
    rviz (rviz/rviz)

ROS_MASTER_URI=http://localhost:11311

process[robot_state_publisher-1]: started with pid [2838]
process[rviz-2]: started with pid [2839]
process[joint_state_publisher_gui-3]: started with pid [2840]
[ WARN] [1624545411.019720081]: The 'state_publisher' executable is deprecated. Please use 'robot_state_publisher' instead
[ WARN] [1624545411.033919362]: The root link base has an inertia specified in the URDF, but KDL does not support a root link with an inertia.  As a workaround, you can add an extra dummy link to your URDF.
[INFO] [1624545412.021853]: Centering

![image](https://user-images.githubusercontent.com/86019166/123297496-49472080-d520-11eb-9529-2c6845b66501.png)
<img width="406" alt="Screen Shot 1442-11-14 at 5 40 11 PM" src="https://user-images.githubusercontent.com/86019166/123517417-783cce00-d6a9-11eb-96a9-db8785ac257e.png">

