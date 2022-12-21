# install

## ros
### dockered

https://github.com/julled/rosdocked

### plain

follow https://gazebosim.org/docs/garden/install_ubuntu
but install fortress for needed ros-ign-bridge interop
```bash
sudo apt install gz-fortress
```

## ros bridge

https://github.com/gazebosim/ros_gz/tree/noetic#binaries

# run sim

###  Zephyr delta wing  

The Zephyr delta wing is positioned on the runway for vertical take-off. 

#### Run Gazebo

```bash
gz sim -v4 -r worlds/zephyr_runway_camera.sdf
```

#### Run ArduPilot SITL

```bash
sim_vehicle.py -v ArduPlane -f gazebo-zephyr --model JSON --map --console
```

#### Arm, takeoff and circle

```bash
MANUAL> mode fbwa
FBWA> arm throttle
FBWA> rc 3 1800
FBWA> mode circle
```

### image bridge

# debug

```bash
gz topic --echo -t /camera_info
```

# use

* gz fortress:

export IGN_GAZEBO_RESOURCE_PATH=/home/julle/projects/SearchWing/Code/ardupilot_gazebo/models:/home/julle/projects/SearchWing/Code/ardupilot_gazebo/worlds:$GZ_SIM_RESOURCE_PATH

ardupilot plugin doesnt work with fortress....

* gz garden:

export GZ_SIM_RESOURCE_PATH=/home/julle/projects/SearchWing/Code/ardupilot_gazebo/models:/home/julle/projects/SearchWing/Code/ardupilot_gazebo/worlds:$GZ_SIM_RESOURCE_PATH

[gazebo => ROS noetic bridge](https://github.com/gazebosim/ros_gz/tree/noetic#binaries) doesnt support gz garden....
