
# Kortex Gen 3 Lite – Aurora Robotics Workshop Task 4

This project focuses on assembling, describing, and visualizing the **Kinova Gen3 lite** robotic arm using **ROS 2** and the **Unified Robot Description Format (URDF)**.  


## Overview

The project defines the full URDF structure for the robot arm, including links, joints, and visual meshes with assigned materials.  

Each link references its mesh in the `src/kinova_description/meshes` directory, and the arm is fully visualizable in **Rviz**.  
Simulation and advanced control (MoveIt, Gazebo/Ignition) can be added in later phases.


The URDF also applies a **white material** for all links for consistent visualization.


## Joint Configuration

| Joint Name | Type |
| :--- | :--- |
| base_to_shoulder | Revolute |
| shoulder_to_upper_arm | Revolute |
| arm_to_upper_arm | Revolute |
| forearm_to_lower_wrist | Revolute |
| lower_wrist_to_upper_wrist | Revolute |
| arm_to_gripper | Fixed |
| RIGHT_BOTTOM | Revolute |
| RIGHT_TIP | Revolute |
| LEFT_BOTTOM | Revolute |
| LEFT_TIP | Revolute |

## Description

Each link includes visual meshes and assigned **white material** for clear visualization in Rviz.  
Joints define spatial relationships (`xyz` and `rpy` origins), parent-child hierarchy, rotation axes, and joint limits.


## Next Steps
 
- **Dynamic Simulation:** Integration with Gazebo or Ignition  
- **Control & Planning:** MoveIt setup for motion planning  
- **Sensor & Gripper Modeling:** Extend URDF to include sensors, gripper interactions 

## Quick Launch (ROS 2 + Rviz)

Follow these steps to visualize the Kinova in Rviz:

### 1. Install ROS 2 and Required Packages

Make sure you have a ROS 2 distribution installed (Humble recommended).  
Then install the necessary packages:

```bash
sudo apt update
sudo apt install ros-humble-urdf-tutorial \
                 ros-humble-joint-state-publisher \
                 ros-humble-joint-state-publisher-gui \
                 ros-humble-robot-state-publisher \
                 ros-humble-rviz2
```
Replace humble with your ROS 2 distro if needed.

2. **Clone the repository**  

```bash
git clone https://github.com/samuelajala01/kinova.git
cd kinova/

```

3. **Build the ROS 2 package**

```bash
colcon build --symlink-install
source install/setup.bash
```

4. **Launch Rviz with the Kinova Gen3 URDF from ws**

```bash
ros2 launch urdf_tutorial display.launch.py model:=$(pwd)/src/kinova_description/urdf/kinova.urdf
```
- $PWD should point to the root of your cloned repository.
- The kinova.urdf file must exist under kinova_description/urdf/.

5. **Visualize and Interact**

- Rviz will open with the Kinova robot loaded.
- Use the Joint State Publisher GUI to move revolute joints interactively.
- The robot’s links are displayed with white and gray material for clarity.


## Next Steps

- Dynamic Simulation: Integration with Gazebo or Ignition
- Control & Planning: MoveIt setup for motion planning
- Sensor & Gripper Modeling: Extend URDF to include sensors and gripper interactions

*Developed as part of the [Aurora Robotics](https://ng.linkedin.com/company/aurora-robotics-in) Core Robotics Workshop – Task 4.*


readme template modified from [here](!https://github.com/Bakel-Bakel/abdullahi-ufractor_xarm7)

