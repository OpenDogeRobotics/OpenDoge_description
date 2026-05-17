# OpenDoge_description

OpenDoge 四足机器人的 URDF/Xacro 描述包，提供运动学、动力学模型与可视化网格，用于仿真与实机控制。

## 目录结构

```
OpenDoge_description/
├── URDF/
│   ├── urdf/
│   │   ├── Opendoge.urdf         # 机器人 URDF 描述文件
│   │   └── Opendoge.csv          # 关节/连杆映射表
│   ├── meshes/                   # 各连杆 STL 网格文件
│   │   ├── base_link.STL         # 机身基座
│   │   ├── FL_*.STL              # 左前腿 (hip/thigh/calf/foot)
│   │   ├── FR_*.STL              # 右前腿
│   │   ├── RL_*.STL              # 左后腿
│   │   └── RR_*.STL              # 右后腿
│   ├── config/
│   │   └── joint_names_Opendoge.yaml
│   ├── launch/
│   │   ├── display.launch        # RViz 可视化启动
│   │   └── gazebo.launch         # Gazebo 仿真启动
│   ├── xml/
│   │   ├── Opendoge.xml
│   │   └── scene.xml
│   ├── CMakeLists.txt
│   └── package.xml
```

## 机器人结构

每条腿包含 3 个驱动关节 (hip / thigh / calf) + 足端 (foot)：

| 腿 | Hip | Thigh | Calf | Foot |
|---|-----|-------|------|------|
| FL (左前) | FL_hip_joint | FL_thigh_joint | FL_calf_joint | FL_foot |
| FR (右前) | FR_hip_joint | FR_thigh_joint | FR_calf_joint | FR_foot |
| RL (左后) | RL_hip_joint | RL_thigh_joint | RL_calf_joint | RL_foot |
| RR (右后) | RR_hip_joint | RR_thigh_joint | RR_calf_joint | RL_foot |

## 依赖

- ROS / ROS2
- `robot_state_publisher`
- `joint_state_publisher`
- `rviz`
- `gazebo`

## 使用

### RViz 可视化

```bash
roslaunch Opendoge display.launch
```

### Gazebo 仿真

```bash
roslaunch Opendoge gazebo.launch
```

模型可同时用于 Isaac Gym、Mujoco 等外部仿真器的导入。

## 许可证

BSD
