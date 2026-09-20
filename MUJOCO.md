
# Kortex Gen 3 Lite

This project focuses on assembling, describing, and visualizing the **Kinova Gen3 lite** robotic arm using **Mujoco** and the **Unified Robot Description Format (URDF)**.  


## Overview

The project defines the full URDF structure for the robot arm, including links, joints, and visual meshes with assigned materials.  

Each link references its mesh in the `src/kinova_description/meshes` directory.


## Quick Launch (ROS 2 + Rviz)

Follow these steps to visualize the Kinova in Mujoco:




1. **Clone the repository**  

```bash
git clone https://github.com/samuelajala01/kinova_arm.git
cd kinova_arm/

```
2. Install Required Packages

```bash
pip install --upgrade pip
pip install mujoco
```
3. Complile the XML(optional)

If you make changes to the URDF, you must compile it into MuJoCo's native XML format (kinova.xml) before launching the scene. Run this one-liner from the root of the workspace:

```
python3 -c "import mujoco; m = mujoco.MjModel.from_xml_path('src/kinova_description/urdf/kinova_mujoco.urdf'); mujoco.mj_saveLastXML('src/kinova_description/urdf/kinova.xml', m)"
```
4. Launch the Interactive Simulation
Run the viewer using the pre-configured tabletop scene file. This scene automatically loads the compiled robot, ground plane, lighting, position actuators, and equality constraints for the gripper linkage:

```
python3 -m mujoco.viewer --mjcf=src/kinova_description/urdf/scene.xml
```
## Next Steps



*Developed as part of the [Aurora Robotics](https://ng.linkedin.com/company/aurora-robotics-in) Core Robotics Workshop – Task 4. Readme template modified from [here](!https://github.com/Bakel-Bakel/abdullahi-ufractor_xarm7)*

