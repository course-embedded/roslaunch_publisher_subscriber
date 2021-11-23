# server_parameter_publisher_subscriber

1. create project file

```bash
mkdir catkin_ws
cd catkin_ws/
mkdir Roslaunch_Publisher_Subscriber
cd Roslaunch_Publisher_Subscriber/
mkdir src
cd src
catkin_create_pkg roslaunch_publisher_subscriber_cpp_pkg publisher subscriber speed_calc rpm_pub
cd ..
catkin_make
 ls
```
2. run ATOM editor
3. BUILD CMAKE ROS PACKAGE: edit cmake file
```bash
# add_dependencies(${PROJECT_NAME} ${${PROJECT_NAME}_EXPORTED_TARGETS} ${catkin_EXPORTED_TARGETS})

# add_executable(${PROJECT_NAME}_node src/project1_cpp_pkg_node.cpp)

# target_link_libraries(${PROJECT_NAME}_node
add_executable(publisher src/publisher.cpp)
target_link_libraries(publisher ${catkin_LIBRARIES})
.
.
.

```
4. compile the ROS project

```bash
ros@ubuntu:~/catkin_ws/project1_ws$ catkin_make
```
4. change directory

```bash
ros@ubuntu:~/catkin_ws/Roslaunch_Publisher_Subscriber$ cd devel/lib/roslaunch_publisher_subscriber_cpp_pkg/
```

5. run the code and verify ros topics: you must already run roscore command
```bash
ros@ubuntu:~/catkin_ws/Roslaunch_Publisher_Subscriber/devel/lib/roslaunch_publisher_subscriber_cpp_pkg/$ ./publisher 
[ INFO] [1637454718.354285503]: Publisher Node Begun Sending Messages

os@ubuntu:~/catkin_ws/Roslaunch_Publisher_Subscriber/devel/lib/roslaunch_publisher_subscriber_cpp_pkg/$ rostopic list
/Welcome_from_publisher_node
/rosout
/rosout_agg
ros@ubuntu:~/catkin_ws/Roslaunch_Publisher_Subscriber/devel/lib/roslaunch_publisher_subscriber_cpp_pkg/$ rostopic echo /Welcome_from_publisher_node
data: "Welcome 1240"
---
data: "Welcome 1241"
---
data: "Welcome 1242"
---
data: "Welcome 1243"
---
```
5. Other method for running the code 

```bash
ros@ubuntu:~/catkin_ws/Roslaunch_Publisher_Subscriber/$ source devel/setup.bash
ros@ubuntu:~/catkin_ws/Roslaunch_Publisher_Subscriber/$ rosrun project1_cpp_pkg publisher
```
