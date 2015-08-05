# Pick-Place-moving
Pick and Place a moving object
In this part the task is the same but we should perform the same action without stopping the conveyor.
First we set the monitor speed to 100. This will be important during the program. Then we set the speed
to 30%. This means that the speed is the 30% percent of the monitor speed which is 100% in the case.
Then we also set the speed for straight line motions indicated in the program. We use here the command
always which signifies that all motion instructions are executed at this speed.
Then we also load the appropriate tool and initialize the variables. The extra variables are for defining the
length of the conveyor and the speed of the conveyor. Then we perform the same task until we put the
object on the conveyor. Here we return the manipulator immediately to the grasp location then we start
the conveyor. After the object reaches the second sensor we wait 2 seconds by which we make sure that
the object passes the sensor completely which can enhance our speed estimation.
Then we restart the conveyor in the other direction and when the object is detected by the second sensor
we initialize a timer to count the time. This is done synchronously as it can be seen. Then we wait till the
object reaches the first sensor and then we register the time and we calculate the conveyor speed.
we can calculate the distance which the robot must take and this is √2 ∗ 150. So to cover this
distance to grasp the object we redefine the speed of the robot for the next motion by multiplying the
conveyor speed by √2.
As the predefined grasping position has changed with 150 mm we redefine it in the program by shifting
the point with 150 mm. Then we move straight to grasp the object. The monitor speed in the beginning
of the program is set because of this motion. Then we put the object to the destination then we return to
the waiting position as in the previous exercise.
If we test the problem we encounter a problem. First if we execute at low speed the robot cannot grasp
the object as it is too slow that is why the monitor speed is set to 100. But still even if we use high speed
the robot is still too slow to grasp the object. This is due to the trajectory generation.it can be
seen we have discontinuities at the acceleration which can cause damage to the mechanical system. That
is why continuous acceleration profile is proposed to have a continuous trajectory to get a smoother profile. By achieving this we need more time to achieve the speed which in our case causes the problem
that we cannot reach the object in time.
The other test is made when we do not wait 2 seconds after passing the second sensor. In this case the
robot was too fast as the accuracy of speed estimation is degraded.
