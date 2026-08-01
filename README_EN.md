# AgileX Robotic Arm URDF Models

[中文](./README.md)

This repository contains URDF / Xacro model files and 3D mesh resources for AgileX series robotic arms, for ROS / ROS2 visualization, simulation, and motion planning.

> **Scope**: This repository is an independent ROS 2 package consumed by
> [agx_arm_ros](https://github.com/ipa-may/agx_arm_ros) and other robot
> descriptions through normal package dependencies.

---

## Supported Models

| Model | Directory | Base URDF | Gripper Xacro | Dexterous Hand Xacro |
|-------|-----------|-----------|---------------|----------------------|
| Piper | `piper/` | `piper_description.urdf` | `piper_with_gripper_description.xacro` | `piper_with_left_revo2_description.xacro` / `piper_with_right_revo2_description.xacro` |
| Piper H | `piper_h/` | `piper_h_description.urdf` | `piper_h_with_gripper_description.xacro` | `piper_h_with_left_revo2_description.xacro` / `piper_h_with_right_revo2_description.xacro` |
| Piper L | `piper_l/` | `piper_l_description.urdf` | `piper_l_with_gripper_description.xacro` | `piper_l_with_left_revo2_description.xacro` / `piper_l_with_right_revo2_description.xacro` |
| Piper X | `piper_x/` | `piper_x_description.urdf` | `piper_x_with_gripper_description.xacro` | `piper_x_with_left_revo2_description.xacro` / `piper_x_with_right_revo2_description.xacro` |
| Nero | `nero/` | `nero_description.urdf` | `nero_with_gripper_description.xacro` | `nero_with_left_revo2_description.xacro` / `nero_with_right_revo2_description.xacro` |
| Revo2 Hand | `revo2/` | `revo2_left_hand.urdf` / `revo2_right_hand.urdf` | — | — |

---

## Directory Structure

```
agx_arm_urdf/
├── piper/
│   ├── meshes/dae/    # 3D mesh files (.dae)
│   └── urdf/          # URDF / Xacro files
├── piper_h/
│   ├── meshes/dae/
│   └── urdf/
├── piper_l/
│   ├── meshes/dae/
│   └── urdf/
├── piper_x/
│   ├── meshes/dae/
│   └── urdf/
├── nero/
│   ├── meshes/dae/
│   └── urdf/
└── revo2/
    ├── meshes/dae/
    └── urdf/
```

---

## Usage

### Recommended: use with the main repository

Clone [agx_arm_ros](https://github.com/ipa-may/agx_arm_ros) and import this
package with `vcstool`:

```bash
mkdir -p ~/agx_arm_ws/src
cd ~/agx_arm_ws/src
git clone -b ros2 https://github.com/ipa-may/agx_arm_ros.git
vcs import . < agx_arm_ros/dependencies.repos
cd ..
colcon build --packages-up-to agx_arm_description
source install/setup.bash
```

Visualize the model in ROS2 (launch files are provided in the main repo):

```bash
ros2 launch agx_arm_description display.launch.py arm_type:=piper
```

For more details, see the [agx_arm_ros documentation](https://github.com/ipa-may/agx_arm_ros).

---

### Standalone use (your own workspace)

This repository already contains its ROS 2 package metadata:

```bash
mkdir -p ~/ws/src
cd ~/ws/src
git clone https://github.com/ipa-may/agx_arm_urdf.git
cd ~/ws
colcon build --packages-select agx_arm_urdf
source install/setup.bash
```

The model resources are installed under `share/agx_arm_urdf`.

---

## License

This project is released under the [MIT License](./LICENSE).
