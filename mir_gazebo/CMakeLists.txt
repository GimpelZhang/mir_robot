cmake_minimum_required(VERSION 3.5.1)
cmake_policy(SET CMP0048 NEW)
project(mir_gazebo)

find_package(catkin REQUIRED COMPONENTS
  roslaunch
  gazebo_ros
)

###################################
## catkin specific configuration ##
###################################
catkin_package() 

#############
## Install ##
#############

# Mark other files for installation (e.g. launch and bag files, etc.)
install(DIRECTORY
  config
  launch
  maps
  sdf
  models
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)

#############
## Testing ##
#############

roslaunch_add_file_check(launch)
