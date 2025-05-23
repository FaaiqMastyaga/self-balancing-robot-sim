cmake_minimum_required(VERSION 3.8)
project(balancing_robot)

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

# find dependencies
find_package(ament_cmake REQUIRED)
find_package(rclcpp REQUIRED)
find_package(urdf REQUIRED)
find_package(robot_state_publisher REQUIRED)
find_package(gazebo_ros REQUIRED)

# Install launch files
install(
  DIRECTORY launch
  DESTINATION share/${PROJECT_NAME}
)

# Install URDF files
install(
  DIRECTORY urdf
  DESTINATION share/${PROJECT_NAME}
)

# Install mesh files (if any)
install(
  DIRECTORY meshes
  DESTINATION share/${PROJECT_NAME}
)

# Install config files (optional)
install(
  DIRECTORY config
  DESTINATION share/${PROJECT_NAME}
)

ament_package()
