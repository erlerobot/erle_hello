cmake_minimum_required(VERSION 2.8.3)

project(hello_erle)

if(NOT WIN32)
  set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11 -Wall -Wextra")
endif()

find_package(ament_cmake REQUIRED)
find_package(example_interfaces REQUIRED)
find_package(rclcpp REQUIRED)
find_package(rmw REQUIRED)
find_package(rmw_implementation_cmake REQUIRED)
find_package(sensor_msgs REQUIRED)
find_package(std_msgs REQUIRED)

ament_package()

##
## Examples of Publish/Subscribe with Topics
##

add_executable(talker src/talker_erle.cpp)
ament_target_dependencies(talker
  "rclcpp"
  "rmw_implementation"
  "std_msgs"
)

add_executable(listener src/listener_erle.cpp)
ament_target_dependencies(listener
  "rclcpp"
  "rmw_implementation"
  "std_msgs"
)

install(TARGETS talker listener DESTINATION bin)
