cmake_minimum_required(VERSION 2.8.3)
project(tf_echo_fixed)

add_compile_options(-std=c++11)

find_package(catkin REQUIRED COMPONENTS
  tf
)

catkin_package(
#  INCLUDE_DIRS include
#  LIBRARIES tf_echo_fixed
  CATKIN_DEPENDS tf
#  DEPENDS system_lib
)
include_directories(
  # include
  ${catkin_INCLUDE_DIRS}
)

add_executable(tf_echo_fixed src/tf_echo_fixed.cpp)

target_link_libraries(tf_echo_fixed
  ${catkin_LIBRARIES}
)

install(TARGETS tf_echo_fixed
  RUNTIME DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
)
