cmake_minimum_required(VERSION 2.8.3)
#set (CMAKE_CXX_STANDARD 11)
project(ros_turtle_control)

add_compile_options(-std=c++11)

find_package(catkin REQUIRED COMPONENTS
  roscpp
  std_msgs
  turtlesim
  geometry_msgs
)

catkin_package()

include_directories(${catkin_INCLUDE_DIRS})

add_executable(move_to_goal src/move_to_goal.cpp)
target_link_libraries(move_to_goal ${catkin_LIBRARIES})

add_executable(multi_checkpoint src/multi_checkpoint.cpp)
target_link_libraries(multi_checkpoint ${catkin_LIBRARIES})

add_executable(multi_turtle src/multi_turtle.cpp)
target_link_libraries(multi_turtle ${catkin_LIBRARIES})
