# MobileRobot-Openloopcontrol
## Aim:

To develop a python control code to move the mobilerobot along the predefined path.

## Equipments Required:
1. RoboMaster EP core
2. Python 3.7

## Procedure
### Step 1:
    DEFINE THE PREDIFINED PATH
      (i) Create a list or array to store the coordinates of the robot's predefined path.
      (ii) Each coordinate should represent a point along the path that the robot needs to follow.
### Step2:
    INITIALIZE THE ROBOT'S STARTING POSITION
      (i) Set the robot's initial position to the first coordinate in the predefined path.
### Step3:
    MOVE THE ROBOT ALONG THE PATH
      (i) Loop through each coordinate in the predefined path, starting from the second coordinate.
      (ii) Calculate the distance and direction from the robot's current position to the next coordinate.
      (iii) Use appropriate robot control commands to move the robot towards the next coordinate.
      (iv) Repeat this process for each coordinate in the predefined path.
### Step4:
    CHECK IF THE ROBOT HAS REACHED THE END OF THE PATH
      (i) After completing the loop, compare the robot's final position with the last coordinate in the
          predefined path.
      (ii) If the two positions match or are within a certain threshold, the robot has successfully reached
           the end of the path.
      (iii) If not, modify the path or make other adjustments as needed.
### Step5:
    END OF THE PROGRAM
      (i) Once the robot has reached the end of the path, stop the program or execute any additional
          tasks required.
      (ii) Print a message or perform any necessary cleanup steps before terminating the program.


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

    ep_chassis.move(x=2.3, y=0, z=0, xy_speed=1.3).wait_for_completed()
    ep_led.set_led(comp = "all",r=255,g=0,b=0,effect="on")

    ep_chassis.move(x=0.5, y=0, z=70, xy_speed=1.3).wait_for_completed()
    ep_led.set_led(comp = "all",r=0,g=255,b=0,effect="on")

    ep_chassis.move(x=0.5, y=0, z=0, xy_speed=1.3).wait_for_completed()
    ep_led.set_led(comp = "all",r=0,g=0,b=255,effect="on")

    ep_chassis.move(x=0.5, y=0, z=95, xy_speed=1.3).wait_for_completed()
    ep_led.set_led(comp = "all",r=255,g=0,b=255,effect="on")

    ep_chassis.move(x=1.5, y=0, z=0, xy_speed=1.3).wait_for_completed()
    ep_led.set_led(comp = "all",r=0,g=255,b=255,effect="on")

    ep_chassis.move(x=0, y=0, z=-115, xy_speed=1.3).wait_for_completed()
    ep_led.set_led(comp = "all",r=255,g=255,b=153,effect="on")

    ep_chassis.move(x=0, y=-1.4, z=0, xy_speed=1.3).wait_for_completed()
    ep_led.set_led(comp = "all",r=255,g=102,b=0,effect="on")

    ep_chassis.move(x=0, y=0, z=130, xy_speed=1.3).wait_for_completed()
    ep_led.set_led(comp = "all",r=255,g=153,b=205,effect="on")

    ep_chassis.move(x=1.55, y=0, z=0, xy_speed=1.3).wait_for_completed()
    ep_led.set_led(comp = "all",r=204,g=153,b=255,effect="on")
    
    ep_chassis.move(x=0, y=0, z=190, xy_speed=1.3).wait_for_completed()
    ep_led.set_led(comp = "all",r=153,g=204,b=255,effect="on")

    ep_chassis.move(x=0, y=1, z=0, xy_speed=1.3).wait_for_completed()
    ep_led.set_led(comp = "all",r=51,g=102,b=255,effect="on")

    ep_chassis.move(x=0, y=0, z=90, xy_speed=1.3).wait_for_completed()
    ep_led.set_led(comp = "all",r=255,g=204,b=0,effect="on")

    ep_chassis.move(x=-1.2, y=0, z=0, xy_speed=1.3).wait_for_completed()
    ep_led.set_led(comp = "all",r=0,g=51,b=102,effect="on")

    ep_chassis.move(x=0, y=0, z=-100, xy_speed=1.3).wait_for_completed()
    ep_led.set_led(comp = "all",r=0,g=255,b=0,effect="on")

    ep_chassis.move(x=0.4, y=0, z=0, xy_speed=1.3).wait_for_completed()
    ep_led.set_led(comp = "all",r=0,g=255,b=0,effect="on")



    
    time.sleep(4)
    ep_camera.stop_video_stream()
    print("Stopped video streaming.....")

    ep_robot.close()
```

## MobileRobot Movement Image:

![robo](./img/robomaster.png)
![image](/Screenshot%202023-07-30%20110147.png)

## MobileRobot Movement Video:
https://youtu.be/2656r0K_8a8

## Result:
Thus the python program code is developed to move the mobilerobot in the predefined path.

```
Mobile Robotics Laboratory
Department of Artificial Intelligence and Data Science/ Machine Learning
Saveetha Engineering College
```
