cmake_minimum_required(VERSION 3.8)
project(px4ctrl_msgs)

# Find dependencies
find_package(ament_cmake REQUIRED)
find_package(rosidl_default_generators REQUIRED)
find_package(builtin_interfaces REQUIRED)

# Generate messages
rosidl_generate_interfaces(${PROJECT_NAME}
  "msg/Command.msg"
  DEPENDENCIES builtin_interfaces
)

# Export dependencies
ament_export_dependencies(
  rosidl_default_runtime
  std_msgs
)

ament_package()