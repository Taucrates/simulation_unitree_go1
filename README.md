This repository allows to simulate the robot go1 by unitree in gazebo using the configuration given by [champ_setup_assistant](https://github.com/chvmp/champ_setup_assistant.git). The kinematics of the robot are also generated by the [champ](https://github.com/chvmp/champ) package. The robot provided in this package has installed a Hokuyo laser and a Real Sense.

* The package is tested in Ubuntu 20.04 using ROS Noetic.

## 1. Installation

### 1.1. Create workspace

  ```
  mkdir -p <catkin_workspace>/src
  cd <catkin_workspace>
  catkin_make
  ```

### 1.2. Dependencies
To run the repository these packages, as well as its dependencies, are required in the workspace:
  * Champ. [here](https://github.com/chvmp/champ.git)
  * Yocs velocity smoother. [here](https://github.com/chvmp/yocs_velocity_smoother.git)
  * Real Sense plugin edited. [here](https://github.com/Taucrates/realsense_gazebo_plugin.git)
  * Real Sense description. [here](https://github.com/issaiass/realsense2_description.git)
  * Scan Tools. [here](https://github.com/CCNYRoboticsLab/scan_tools.git)
  * Slam_gmapping with some modifications. [here](https://github.com/Taucrates/go1_slam_gmapping.git)

### 1.3. Install the repository
  ```
  cd <catkin_workspace>/src
  git clone https://github.com/Taucrates/simulation_unitree_go1.git
  cd ..
  catkin_make
  ```
  To run the files of the workspace the execution of ```source <PATH TO YOURWORKSPACE>/<catkin_workspace>/devel/setup.bash``` is required.
  
  ## 2. Example
  In this section is shown an example on how to use this package. 
  
  ### 2.1. Gazebo launch
  The robot spawned (unitree_go1) has a hokuyo laser and a Real Sense installed.
  ´´´roslaunch go1_simulation go1_simulation.launch´´´
  
  ### 2.2. Slam launch
  ´´´roslaunch go1_simulation slam.launch rviz:=true´´´
