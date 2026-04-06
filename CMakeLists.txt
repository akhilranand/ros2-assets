cmake_minimum_required(VERSION 3.8)
project(my_cpp_pkg)

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

# find dependencies
find_package(ament_cmake REQUIRED)
find_package(rclcpp REQUIRED)


#........................................................
add_executable(executable_name  src/node_file_name.cpp)
ament_target_dependencies(executable_name  rclcpp)

install(TARGETS
  executable_name 
  DESTINATION lib/${PROJECT_NAME}
)
#........................................................


ament_package()