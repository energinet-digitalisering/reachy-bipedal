cmake_minimum_required(VERSION 3.8)
project(reachy_msgs)

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

# Dependencies
find_package(ament_cmake REQUIRED)
find_package(geometry_msgs REQUIRED)
find_package(sensor_msgs REQUIRED)
find_package(std_msgs REQUIRED)
find_package(rosidl_default_generators REQUIRED)

rosidl_generate_interfaces(${PROJECT_NAME}
  "msg/Gripper.msg"
  "msg/ZoomCommand.msg"

  "srv/GetForwardKinematics.srv"
  "srv/GetInverseKinematics.srv"
  "srv/GetCameraZoomFocus.srv"
  "srv/SetCameraZoomFocus.srv"
  "srv/GetCameraZoomLevel.srv"
  "srv/SetCameraZoomLevel.srv"
  "srv/GetCameraZoomSpeed.srv"
  "srv/SetCameraZoomSpeed.srv"
  "srv/SetFocusState.srv"
  "srv/GetDynamicState.srv"

  DEPENDENCIES geometry_msgs sensor_msgs std_msgs
)

ament_package()
