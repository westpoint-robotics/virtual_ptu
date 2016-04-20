# usma_ptu

Quick Start Guide for using the usma_ptu package to control a dynamixel pan-tilt unit.  These instructions can also be extended to control a dynamixel-based multi-link arm.  There are currently three interfaces: a touch screen, a joystick, and a myo band. 
1. Download the usma_ptu source code.
 - Clone the source code into your catkin workspace src folder.
 - `$ cd ~/catkin_ws/src`
 - `$ git clone https://github.com/westpoint-robotics/usma_ptu.git`
 - Directory structure should look like ~/catkin_ws/src/usma_ptu
 - `$ catkin_make`

### For using a USB2Dynamixel Adapter or equivalent:

1. Install the [dynamixel_motor] {http://wiki.ros.org/dynamixel_motor?distro=indigo} package.
2. Connect a USB joystick.  Esnure the ROS [joy]{http://wiki.ros.org/joy/Tutorials/ConfiguringALinuxJoystick} package is installed.
3. Configuration and setup is based on the [dynamixel_controller tutorial]{http://wiki.ros.org/dynamixel_controllers/Tutorials}.
4. Connect the pan-tilt unit to the computer via the USB2Dynamixel connector.
 - Pan motor ID is 1, tilit motor ID is 2.
 - To install the Dynamixel RoboPlus software, follow this [tutorial]{http://support.robotis.com/en/software/roboplus_main.htm}.
- To configure the Dynamixel IDs, read this [tutorial]{http://support.robotis.com/en/product/bioloid/beginnerkit/usefullinfo/dxl_configuration.htm#ID_Change}
 - Ensure that your dynamixels are powered via an external power source and connected to a hub.

http://www.trossenrobotics.com/resize/shared/images/PImages/IL-6PHUB-c.jpg?bw=1000&bh=1000

6. In a terminal run: "roscore"

7. Open up a new terminal and run: "roslaunch virtual_ptu ptu_joy.launch"
	-This launch file calls on two launch files
		-Dynamixel control manager: controller_manager.launch
		-Dynamixel control spawner: controller_spawner.launch
	-It also starts the joystick node "joy_node" 
	
8. Now you will be able to control the pan-tilt using the Logitech Joystick
	-The twisting motion on the joystick (Z-Axis) will provide the panning
	-The forward-back motion (Y-Axis) will provide the tilting

