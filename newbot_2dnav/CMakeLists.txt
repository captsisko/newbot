cmake_minimum_required(VERSION 2.8.3)
project(newbot_2dnav)


find_package(catkin REQUIRED COMPONENTS
  geometry_msgs
  nav_msgs
  roscpp
  rospy
  sensor_msgs
  std_msgs
  tf
)

catkin_package()

include_directories(
  ${catkin_INCLUDE_DIRS}
)

add_executable(newbot_pid_controller src/newbot_pid_controller.cpp)
target_link_libraries(newbot_pid_controller ${catkin_LIBRARIES})
add_dependencies(newbot_pid_controller ${catkin_EXPORTED_TARGETS})

add_executable(move_base_recover src/move_base_recover.cpp)
target_link_libraries(move_base_recover ${catkin_LIBRARIES})
add_dependencies(move_base_recover ${catkin_EXPORTED_TARGETS})
