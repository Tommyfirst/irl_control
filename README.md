## IRL Control

IRL Control is a simulation and control framework for bimanual robot manipulation developed at the the Interactive Robotics Lab at Arizona State University. The framework provides a variety of features and algorithms for implementing and learning of bimanual control policies. In particular, it provides easy access to functions for collecting training data from input devices, generating low-level robot control signals, for visualization and debugging, as well as the evaluation of generated robot controllers. IRL Control uses MuJoCo as a simulation backbone to generate physically-correct simulations of the interactions between the robot, its environment, and manipulated objects. 

## Capabilities
- Operational Space Control
- Admittance Control for handling external forces to the robot
- Rapid development of demos with a dual-arm UR5 robot through inheritance
- Support for PS Move controllers and 3D Connexion Space Mouse to teleoperate the robot arms
- Supports easy addition of controlled devices to the scene (handles Jacobians, forces, joint states, etc)
- YAML configuration files for setting the PID Gains, Min/Max velocities, and kinematic descriptions of the robot's controlled devices
- Male/Female adapters with low-tolerance for performing insertion tasks (with convex decompositions from V-HACD)

## Examples

### Insertion Task
<!-- | | |
|-|-|
| <img src="img/insertion_task3.gif" alt="drawing" width="300"/>  | <img src="img/insertion_task3.gif" alt="drawing" width="300"/>  | -->
In this example, the Dual UR5 Robot inserts adapters into their corresponding slot, with each component spawned at a randomly generated angle and position. The robot must precisely align and insert the components under small tolerance contraints. Here, the robot executes a sequence of actions defined by the [insertion action sequence](irl_control/action_sequence_configs/insertion_task.yaml). This action sequence defines a generic algorithm that can be executed on either arm, as well as: how much force the gripper should apply at each stage of the task, the velocity constraints, and the objects involved in the action (containing information on the proper location and orientation for picking/inserting).

<img src="img/insertion_task.gif" alt="drawing"/>

<br>

### PS Move Teleoperation
In this example, the user teleoperates the robot for picking up objects in the scene. The PS Move controllers allow for opening and closing the gripper and controlling the desired position of the end effector, which the robot moves to when the trigger is pressed. The controllers have a one-to-one correspondance with each robot arm, so that it is possible to extend this example to more complex (and jointly controlled) bi-manual manipulation tasks.

<img src="img/ps_move_demo.gif" alt="drawing"/>

