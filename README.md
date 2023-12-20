# MobileRobot-Openloopcontrol
## Aim:

To develop a python control code to move the mobilerobot along the predefined path.

## Equipments Required:
1. RoboMaster EP core
2. Python 3.7

## Procedure
### 1. Robot Connection:

Connect the RoboMaster EP robot to the PC using Wi-Fi.

### 2. Initialize Robot:

Use the robot.Robot() class to initialize the robot.
Initialize the chassis (ep_chassis), LED system (ep_led), and camera (ep_camera).

### 3. Start Video Streaming:

Begin the video streaming to visualize the robot's perspective.
Utilize the ep_camera.start_video_stream(display=True, resolution=camera.STREAM_360P) function to start streaming with a specified resolution and display on the PC.
### 4. Execute Path Commands:

Sequentially execute movement commands for the robot using the chassis (ep_chassis).
Set LED effects for visual feedback using ep_led.set_led() after each movement to indicate different states.
### 5. Path Calibration:

Conduct trial and error to calibrate the robot's path by adjusting movement parameters.
Fine-tune the robot's trajectory until it accurately follows the desired path.
### 6. End Operation:

Stop video streaming using ep_camera.stop_video_stream() after the robot completes the designated path.
Close the robot connection using ep_robot.close().

### 7. Documentation:

Record the parameters and adjustments made during calibration.
Note any challenges encountered and their resolutions.
Include a description of the executed path and LED effects for each movement.
## Program
```python
from robomaster import robot
import time
from robomaster import camera

if _name_ == '_main_':
    ep_robot = robot.Robot()
    ep_robot.initialize(conn_type="ap")

    ep_chassis = ep_robot.chassis
    ep_led = ep_robot.led
    ep_camera = ep_robot.camera

    print("Video streaming started.....")
    ep_camera.start_video_stream(display=True, resolution = camera.STREAM_360P)

    ep_chassis.move(x=2.6, y=0, z=0,xy_speed=1.2).wait_for_completed()
    ep_led.set_led(comp = "all",r=0,g=255,b=0,effect="on")

    ep_chassis.move(x=0.3, y=0, z=80,xy_speed=1.0).wait_for_completed()
    ep_led.set_led(comp = "all",r=255,g=0,b=0,effect="on")

    ep_chassis.move(x=1, y=0, z=0,xy_speed=1.0).wait_for_completed()
    ep_led.set_led(comp = "all",r=0,g=255,b=255,effect="on")

    ep_chassis.move(x=0, y=0, z=90,xy_speed=1.0).wait_for_completed()
    ep_led.set_led(comp = "all",r=255,g=0,b=255,effect="on")

    ep_chassis.move(x=1.5, y=0, z=0,xy_speed=1.0).wait_for_completed()
    ep_led.set_led(comp = "all",r=255,g=102,b=0,effect="on")

    ep_chassis.move(x=0, y=0, z=60,xy_speed=1.0).wait_for_completed()
    ep_led.set_led(comp = "all",r=128,g=0,b=0,effect="on")

    ep_chassis.move(x=0, y=1.6, z=0,xy_speed=1.0).wait_for_completed()
    ep_led.set_led(comp = "all",r=255,g=255,b=0,effect="on")

    ep_chassis.move(x=0, y=0, z=-44,xy_speed=1.0).wait_for_completed()
    ep_led.set_led(comp = "all",r=255,g=255,b=0,effect="on")

    ep_chassis.move(x=1.45, y=0, z=0,xy_speed=1.0).wait_for_completed()
    ep_led.set_led(comp = "all",r=153,g=51,b=102,effect="on")

    
    ep_chassis.move(x=0, y=-1.8, z=0,xy_speed=1.0).wait_for_completed()
    ep_led.set_led(comp = "all",r=0,g=255,b=255,effect="on")

    ep_chassis.move(x=0, y=0, z=170,xy_speed=1.0).wait_for_completed()
    ep_led.set_led(comp = "all",r=0,g=0,b=128,effect="on")

    ep_chassis.move(x=0, y=0.3, z=0,xy_speed=1.0).wait_for_completed()
    ep_led.set_led(comp = "all",r=0,g=0,b=128,effect="on")

    ep_chassis.move(x=0.7, y=0, z=0,xy_speed=1.0).wait_for_completed()
    ep_led.set_led(comp = "all",r=0,g=102,b=204,effect="on")

    ep_chassis.move(x=0, y=0, z=0,xy_speed=1.0).wait_for_completed()
    ep_led.set_led(comp = "all",r=255,g=255,b=0,effect="on")

    time.sleep(4)
    ep_camera.stop_video_stream()
    print("Stopped video streaming.....")

    ep_robot.close()
```

## MobileRobot Movement Image:
![WhatsApp Image 2023-12-20 at 22 51 34_516cbf9b](https://github.com/SANTHAN-2006/mobilerobot-openloopcontrol/assets/80164014/33832a5a-bea6-4be0-b9ae-99ab82d4da2d)
<br/>
<br/>
![WhatsApp Image 2023-12-20 at 22 51 34_64a70367](https://github.com/SANTHAN-2006/mobilerobot-openloopcontrol/assets/80164014/1f5722f8-5603-46c9-ab6b-f2215444ae48)

## MobileRobot Movement Video:
https://youtu.be/nm324UdKpqY?si=q1j0egVRx6X9RjCZ

## Result:
Thus the python program code is developed to move the mobilerobot in the predefined path.
```
Mobile Robotics Laboratory
Department of Artificial Intelligence and Data Science/ Machine Learning
Saveetha Engineering College
```
