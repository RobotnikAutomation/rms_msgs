cmake_minimum_required(VERSION 2.8.3)
project(rms_msgs)

## Find catkin macros and libraries
## if COMPONENTS list like find_package(catkin REQUIRED COMPONENTS xyz)
## is used, also find other catkin packages
find_package(catkin REQUIRED COMPONENTS actionlib_msgs std_msgs geometry_msgs message_generation)


#######################################
## Declare ROS messages and services ##
#######################################

## Generate messages in the 'msg' folder
add_message_files(DIRECTORY msg
    FILES
    Mission.msg
    State.msg
    Status.msg
    Target.msg
)

## Generate services in the 'srv' folder
add_service_files(
    DIRECTORY srv
    FILES
    MissionQuery.srv
    AddRMSMission.srv
    TargetsQuery.srv
    UserAction.srv
)

#add_action_files(
#    FILES
#    action.action
#)


## Generate added messages and services with any dependencies listed here
generate_messages(
DEPENDENCIES
   actionlib_msgs
   std_msgs  # Or other packages containing msgs
   geometry_msgs
)

catkin_package(CATKIN_DEPENDS
  actionlib_msgs
  message_runtime
  std_msgs
  geometry_msgs
)
