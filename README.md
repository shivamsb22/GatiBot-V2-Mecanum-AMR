<div align="center">

<a href="https://docs.ros.org/en/humble/">
<img src="https://capsule-render.vercel.app/api?type=rect&color=0:02040A,45:071B35,100:003B66&height=190&section=header&text=GatiBot%20V2&fontSize=58&fontColor=00D9FF&animation=fadeIn&fontAlignY=40&desc=AUTONOMOUS%20MECANUM-WHEEL%20MOBILE%20ROBOT&descSize=16&descColor=FFFFFF&descAlignY=68" width="100%" alt="GatiBot V2"/>
</a>

### ⚡ BUILDING THE NEXT GENERATION OF AUTONOMOUS ROBOTICS

*A ROS 2-based mobile robotics platform for omnidirectional motion, simulation, perception, mapping, and autonomous navigation.*

<br/>

<a href="https://docs.ros.org/en/humble/">
<img src="https://img.shields.io/badge/ROS_2-HUMBLE-00D9FF?style=for-the-badge&logo=ros&logoColor=white" alt="ROS 2 Humble"/>
</a>
<a href="https://ubuntu.com/">
<img src="https://img.shields.io/badge/UBUNTU-22.04-E95420?style=for-the-badge&logo=ubuntu&logoColor=white" alt="Ubuntu 22.04"/>
</a>
<a href="https://gazebosim.org/docs">
<img src="https://img.shields.io/badge/SIMULATION-GAZEBO-795BDE?style=for-the-badge" alt="Gazebo"/>
</a>
<a href="https://docs.nav2.org/">
<img src="https://img.shields.io/badge/NAVIGATION-NAV2-00B8D9?style=for-the-badge" alt="Nav2"/>
</a>
<a href="https://github.com/SteveMacenski/slam_toolbox">
<img src="https://img.shields.io/badge/MAPPING-SLAM%20TOOLBOX-00C896?style=for-the-badge" alt="SLAM Toolbox"/>
</a>

<br/>

<img src="https://img.shields.io/badge/DRIVE-4%20MECANUM%20WHEELS-00D9FF?style=flat-square" alt="Mecanum wheels"/>
<img src="https://img.shields.io/badge/COMPUTE-RASPBERRY%20PI%204-C51A4A?style=flat-square" alt="Raspberry Pi 4"/>
<img src="https://img.shields.io/badge/CONTROL-ESP32-AB47BC?style=flat-square" alt="ESP32"/>
<img src="https://img.shields.io/badge/STATUS-IN%20DEVELOPMENT-FF8C42?style=flat-square" alt="In development"/>

</div>

---

## 🔷 01 / PROJECT OVERVIEW

**GatiBot V2** is a ROS 2-based autonomous mobile robot project built around a four-wheel mecanum drive system.

The project combines robot modeling, simulation, embedded motor control, sensor integration, SLAM, localization, and autonomous navigation into a modular robotics platform.

The development workflow prioritizes simulation and software validation before deployment and testing on physical hardware.

> **Development status:** Active development. Individual features are subject to integration and hardware validation.

---

## 🚀 02 / KEY FEATURES

| Feature | Description |
|---|---|
| 🔵 Mecanum Drive | Omnidirectional movement: forward, sideways, diagonal, and rotational |
| 🤖 ROS 2 | Modular robotics software architecture |
| 🧩 URDF / Xacro | Robot links, joints, sensors, and coordinate frames |
| 🌐 Gazebo | Robot simulation and motion testing |
| 🗺️ SLAM Toolbox | Mapping and simultaneous localization and mapping |
| 🎯 Nav2 | Autonomous navigation and goal-based movement |
| 📡 RPLIDAR A1 | 2D laser scanning for mapping |
| 🎮 ESP32 | Embedded motor-control development |
| 📷 Camera | Raspberry Pi Camera Module 3 integration |
| 📊 RViz2 | Robot state, sensor, TF, and map visualization |

*Capabilities are listed as project goals or integrations; verify each feature against the current implementation.*

---

## 🛠️ 03 / TECHNOLOGY STACK

Click a technology to open its official website or documentation.

| Technology | Documentation |
|---|---|
| <a href="https://docs.ros.org/en/humble/">ROS 2 Humble</a> | <a href="https://docs.ros.org/en/humble/">Official Docs ↗</a> |
| <a href="https://ubuntu.com/">Ubuntu</a> | <a href="https://ubuntu.com/tutorials">Official Tutorials ↗</a> |
| <a href="https://gazebosim.org/">Gazebo</a> | <a href="https://gazebosim.org/docs">Official Docs ↗</a> |
| <a href="https://github.com/ros2/rviz">RViz2</a> | <a href="https://github.com/ros2/rviz">GitHub ↗</a> |
| <a href="https://github.com/SteveMacenski/slam_toolbox">SLAM Toolbox</a> | <a href="https://github.com/SteveMacenski/slam_toolbox">GitHub ↗</a> |
| <a href="https://docs.nav2.org/">Nav2</a> | <a href="https://docs.nav2.org/">Official Docs ↗</a> |
| <a href="https://control.ros.org/humble/">ros2_control</a> | <a href="https://control.ros.org/humble/">Official Docs ↗</a> |
| <a href="https://docs.espressif.com/projects/esp-idf/en/stable/esp32/">ESP32</a> | <a href="https://docs.espressif.com/projects/esp-idf/en/stable/esp32/">Official Docs ↗</a> |
| <a href="https://www.raspberrypi.com/documentation/">Raspberry Pi</a> | <a href="https://www.raspberrypi.com/documentation/">Official Docs ↗</a> |
| <a href="https://docs.ros.org/en/humble/Tutorials/Intermediate/URDF/URDF-Main.html">URDF</a> | <a href="https://docs.ros.org/en/humble/Tutorials/Intermediate/URDF/URDF-Main.html">Official Tutorial ↗</a> |

---

## 🔩 04 / HARDWARE CONFIGURATION

| Component | Specification / Purpose |
|---|---|
| Main computer | Raspberry Pi 4B, 8 GB RAM |
| Microcontroller | ESP32-WROOM |
| Drive system | 4 × 60 mm mecanum wheels |
| Motors | 4 × DC geared motors with encoders |
| Motor drivers | 2 × dual-channel motor drivers |
| LiDAR | RPLIDAR A1 |
| Camera | Raspberry Pi Camera Module 3 |
| Sensors | Ultrasonic, IR, temperature, flame, and sound sensors |
| Power regulation | DC-DC buck converters |

**Power safety:** Keep motor power within the motor-driver ratings. Use properly rated converters, suitable wiring, and a shared signal-ground reference where required. Do not power drive motors directly from the Raspberry Pi.

---

## 🧠 05 / SYSTEM ARCHITECTURE

<div align="center">

```text
              ┌────────────────────────┐
              │      ROS 2 HUMBLE      │
              │ Topics / Services / TF │
              └────────────┬───────────┘
                           │
              ┌────────────▼───────────┐
              │   SLAM / NAVIGATION    │
              │ SLAM Toolbox / Nav2    │
              └────────────┬───────────┘
                           │
              ┌────────────▼───────────┐
              │    ROBOT CONTROLLER    │
              │ Velocity / Odometry    │
              └────────────┬───────────┘
                           │
              ┌────────────▼───────────┐
              │      ESP32 WROOM      │
              │ Motors / Encoders / I/O│
              └────────────┬───────────┘
                           │
              ┌────────────▼───────────┐
              │   MECANUM DRIVE BASE   │
              │   4 Wheels / 4 Motors  │
              └────────────────────────┘
```

</div>

*Conceptual architecture. Actual communication interfaces depend on the implemented hardware and software.*

---

## 🖥️ 06 / SIMULATION, SLAM & NAVIGATION

The simulation and validation workflow includes:

- Robot model and joint validation in Gazebo.
- TF tree inspection and sensor-frame alignment.
- Mecanum wheel kinematics and velocity-command testing.
- LiDAR scan visualization in RViz2.
- SLAM mapping and map saving.
- Localization using AMCL, where configured.
- Nav2 goal navigation and obstacle avoidance.
- Comparison of simulated and physical robot behavior.

Useful ROS 2 commands:

```bash
# Source ROS 2 Humble
source /opt/ros/humble/setup.bash

# Inspect running nodes
ros2 node list

# Inspect available topics
ros2 topic list

# Inspect transforms
ros2 run tf2_tools view_frames

# Inspect installed GatiBot packages
ros2 pkg list | grep gati_bot
```

---

## ⚙️ 07 / GETTING STARTED

### Requirements

- Ubuntu 22.04 LTS
- ROS 2 Humble
- Colcon and required ROS dependencies
- Gazebo version compatible with the installed ROS packages

Official installation guide:

<a href="https://docs.ros.org/en/humble/Installation/Ubuntu-Install-Debs.html">
<img src="https://img.shields.io/badge/INSTALL-ROS%202%20HUMBLE-00D9FF?style=for-the-badge&logo=ros&logoColor=white" alt="Install ROS 2 Humble"/>
</a>

### Build the workspace

```bash
# Navigate to the workspace
cd ~/gatibot_v2_ws

# Source ROS 2
source /opt/ros/humble/setup.bash

# Install dependencies if package.xml files are present
rosdep install --from-paths src --ignore-src -r -y

# Build the workspace
colcon build --symlink-install

# Source the build
source install/setup.bash
```

### Inspect available packages

```bash
ros2 pkg list | grep gati_bot
```

Launch commands depend on the launch files included in the workspace. Check the actual package launch directories before starting simulation or navigation.

---

## 📁 08 / WORKSPACE STRUCTURE

Expected package organization:

```text
gatibot_v2_ws/
├── src/
│   ├── gati_bot_description/
│   ├── gati_bot_bringup/
│   ├── gati_bot_control/
│   ├── gati_bot_hardware/
│   └── gati_bot_navigation/
├── build/
├── install/
├── log/
└── README.md
```

The structure above is a reference. Keep the README synchronized with the actual folders and files in your workspace.

---

## 🗺️ 09 / DEVELOPMENT ROADMAP

- [x] Create the ROS 2 workspace.
- [x] Develop the robot description.
- [x] Begin Gazebo simulation.
- [ ] Validate mecanum-drive kinematics.
- [ ] Complete ESP32 motor-control integration.
- [ ] Validate encoder feedback and odometry.
- [ ] Verify LiDAR frames and SLAM.
- [ ] Configure localization and Nav2.
- [ ] Validate obstacle avoidance and safety.
- [ ] Complete physical robot testing.
- [ ] Publish setup and troubleshooting documentation.

*Update the checklist as milestones are verified.*

---

## 🔬 10 / ENGINEERING NOTES

- Check mecanum wheel orientation and roller direction.
- Keep `base_link`, wheel frames, and sensor frames consistent.
- Verify LiDAR topic names and frame IDs before running SLAM.
- Calibrate wheel radius, wheel separation, and encoder scaling.
- Test emergency-stop behavior before autonomous physical runs.
- Match the Gazebo version to the ROS packages and launch files installed on the system.

---

## 👨‍💻 11 / DEVELOPER

<div align="center">

### JERRY | ROBOTICS & AUTOMATION ENGINEERING

**ROS 2 · Autonomous Mobile Robots · SLAM · Gazebo · Embedded Systems**

<a href="https://github.com/">
<img src="https://img.shields.io/badge/GitHub-Explore%20Projects-111111?style=for-the-badge&logo=github&logoColor=white" alt="GitHub"/>
</a>
<a href="https://www.linkedin.com/">
<img src="https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn"/>
</a>

<br/>

<img src="https://capsule-render.vercel.app/api?type=rect&color=0:02040A,50:002B49,100:00D9FF&height=75&section=footer&text=ENGINEERED%20TO%20MOVE%20BEYOND&fontSize=19&fontColor=FFFFFF" width="100%" alt="GatiBot footer"/>

<sub>Designed with curiosity. Built through engineering. Improved through testing.</sub>

</div>
