# Kortex Gen 3 Lite – Aurora Robotics Workshop Task 4

This project focuses on assembling, describing, and visualizing the **Kinova Gen3 lite** robotic arm using the **Unified Robot Description Format (URDF)**. It has been built to support both traditional ROS 2 pipelines and high-fidelity physics simulations in MuJoCo.

## Overview

The project defines the full URDF structure for the robot arm, including links, joints, and visual meshes with assigned materials. Each link references its mesh in the `src/kinova_description/meshes` directory.

To support both kinematic planning and physical interaction, the documentation and launch instructions are split into two environments:

1. **[ROS 2 & Rviz (ROS.md)](ROS.md):** For kinematic visualization, joint state publishing, and traditional motion planning pipelines.
2. **[MuJoCo Physics Simulation (MUJOCO.md)](MUJOCO.md):** For closed-loop physics simulation, featuring mathematically constrained joint limits, active position actuators, and mimicking equality constraints for the parallel gripper.

## Joint Configuration

| Joint Name | Type |
| :--- | :--- |
| base_to_shoulder | Revolute |
| shoulder_to_upper_arm | Revolute |
| arm_to_upper_arm | Revolute |
| forearm_to_lower_wrist | Revolute |
| lower_wrist_to_upper_wrist | Revolute |
| arm_to_gripper | Revolute |
| RIGHT_BOTTOM | Revolute |
| RIGHT_TIP | Revolute |
| LEFT_BOTTOM | Revolute |
| LEFT_TIP | Revolute |

*Note: The `arm_to_gripper` joint is configured as revolute to support full 6-DoF end-effector control. The gripper tips utilize a mechanical linkage configuration.*

## Research Roadmap & Next Steps
 
- **Robot Learning Environments:** Implement a standardized reinforcement learning wrapper around the MuJoCo scene for continuous control benchmarking.
- **VLA Fine-Tuning:** Collect teleoperated demonstration rollouts (HDF5/RLDS format) to evaluate parameter-efficient fine-tuning of open-source Vision-Language-Action policies.
- **Control & Planning:** Integrate MoveIt for collision-free motion planning.

*Developed as part of the [Aurora Robotics](https://ng.linkedin.com/company/aurora-robotics-in) Core Robotics Workshop – Task 4. Readme template modified from [here](https://github.com/Bakel-Bakel/abdullahi-ufractor_xarm7)*