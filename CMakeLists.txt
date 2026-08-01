cmake_minimum_required(VERSION 3.8)
project(agx_arm_urdf)

find_package(ament_cmake REQUIRED)

install(
  DIRECTORY nero piper piper_h piper_l piper_x revo2
  DESTINATION share/${PROJECT_NAME}
)

ament_package()
