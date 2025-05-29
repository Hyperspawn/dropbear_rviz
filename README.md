# Dropbear RViz Visualization

This package provides RViz-based visualization and basic joint interaction for the Dropbear humanoid robot. It is primarily intended for debugging URDF integrity, exploring robot structure, and performing manual joint testing using sliders.

## Features

- ✅ Load full-body URDF of Dropbear into RViz
- ✅ Visualize all links and joints in 3D
- ✅ Use sliders to control each joint interactively
- ✅ Easily switch between simplified and granular URDF variants
- ✅ Serves as a frontend for quick mechanical tests before full ROS control pipelines are integrated

---

## Getting Started

### Prerequisites

Ensure you have [ROS 2](https://docs.ros.org/en/humble/Installation.html) (tested on Humble)

---

### Launch RViz

```bash
source install/setup.sh
ros2 launch dropbear_rviz display.launch.py
```

> You can also use the launch files from `dropbear_modular_urdf` or `dropbear_granular_urdf`.

---

### Using the Sliders

Once RViz loads:
- You will see a GUI window with sliders for each joint.
- Moving a slider updates the corresponding joint in real-time.
- Useful for checking joint limits, link connections, and TF frames.

> Make sure `robot_description` is published via the launch file, or the robot won't render.

---

## Use Cases

- 🔧 Verify mesh placements, orientations, and scales
- 🤖 Educate or demo the structure of a humanoid robot without needing simulation
- 🧪 Test new joints/subassemblies visually
- 🕹️ Prototype actuator behaviors by testing joint angles directly

---

## Troubleshooting

- **Robot doesn’t appear?**
  - Set `Fixed Frame` to `torso_base_link`
  - Add a `RobotModel` manually and set its description topic to `robot_description`

- **Meshes missing?**
  - Make sure all `mesh` paths in the URDFs use `package://` and match casing exactly

---

## Example Previews

- Full-body render
- Joint slider interaction
- Comparison between simplified and granular URDFs

---

## License

MIT © Hyperspawn
