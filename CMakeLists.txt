cmake_minimum_required(VERSION 3.8)
project(px4ctrl_msgs)

# Find dependencies
find_package(ament_cmake REQUIRED)
find_package(rosidl_default_generators REQUIRED)
find_package(builtin_interfaces REQUIRED)
find_package(std_msgs REQUIRED)

# Generate messages
rosidl_generate_interfaces(${PROJECT_NAME}
  "msg/Command.msg"
  "msg/State.msg"
  "msg/Setpoint.msg"
  "srv/StepSim.srv"
  "srv/GetReference.srv"
  DEPENDENCIES builtin_interfaces std_msgs
)

# Export dependencies
ament_export_dependencies(
  rosidl_default_runtime
  builtin_interfaces
  std_msgs
)

ament_package()