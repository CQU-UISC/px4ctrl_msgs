cmake_minimum_required(VERSION 3.8)
project(px4msgs)

# Find dependencies
find_package(ament_cmake REQUIRED)
find_package(rosidl_default_generators REQUIRED)
find_package(std_msgs REQUIRED)

# Generate messages
rosidl_generate_interfaces(${PROJECT_NAME}
  "msg/Command.msg"
  DEPENDENCIES std_msgs
)

# Export dependencies
ament_export_dependencies(
  rosidl_default_runtime
  std_msgs
)

ament_package()