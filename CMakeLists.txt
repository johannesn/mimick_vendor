cmake_minimum_required(VERSION 3.10)
project(mimick_vendor)

find_package(ament_cmake REQUIRED)
find_package(ament_cmake_vendor_package REQUIRED)

set(mimick_version "ros2-riscv")    
ament_vendor(mimick_vendor
  VCS_URL https://github.com/guillaume-pais-siemens/Mimick.git
  VCS_VERSION ${mimick_version}
)

ament_export_dependencies(mimick)

if(BUILD_TESTING)
  find_package(ament_lint_auto REQUIRED)
  ament_lint_auto_find_test_dependencies()
endif()

ament_package()
