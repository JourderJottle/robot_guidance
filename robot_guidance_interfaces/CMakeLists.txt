cmake_minimum_required(VERSION 3.8)
project(robot_guidance_interfaces)

# Dependencies
find_package(ament_cmake REQUIRED)
find_package(builtin_interfaces REQUIRED)
find_package(rosidl_default_generators REQUIRED)
find_package(geometry_msgs REQUIRED)

# Declare interfaces
rosidl_generate_interfaces(${PROJECT_NAME}
  "action/GoToDepth.action"
  "action/GoToSide.action"
  "action/NavigateAprilTags.action"
  DEPENDENCIES builtin_interfaces geometry_msgs std_msgs
)

# Export for downstream packages
ament_export_dependencies(rosidl_default_runtime)

ament_package()
