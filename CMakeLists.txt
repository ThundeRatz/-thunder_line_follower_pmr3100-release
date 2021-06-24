cmake_minimum_required(VERSION 3.0.2)
project(thunder_line_follower_pmr3100)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} ${GAZEBO_CXX_FLAGS}")
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED True)

find_package(gazebo REQUIRED)
find_package(roslaunch REQUIRED)

find_package(catkin REQUIRED COMPONENTS
  gazebo_plugins
  gazebo_ros
  roscpp
  rospy
  geometry_msgs
  velocity_controllers
  robot_state_publisher
  joint_state_publisher
)

catkin_package(
  INCLUDE_DIRS plugins/include
  CATKIN_DEPENDS gazebo_plugins gazebo_ros geometry_msgs roscpp
)

include_directories(${catkin_INCLUDE_DIRS}
                    ${Boost_INCLUDE_DIR}
                    ${GAZEBO_INCLUDE_DIRS}
)

link_directories(${GAZEBO_LIBRARY_DIRS})

include_directories(plugins/include)

add_library(line_sensor_plugin SHARED plugins/src/line_sensor_plugin.cpp)
target_link_libraries(line_sensor_plugin CameraPlugin ${catkin_LIBRARIES} ${GAZEBO_LIBRARIES})

install(TARGETS line_sensor_plugin
  LIBRARY DESTINATION ${CATKIN_PACKAGE_LIB_DESTINATION}
)

foreach(dir config launch meshes urdf)
	install(DIRECTORY ${dir}/
		DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}/${dir})
endforeach()

install(DIRECTORY plugins/include
    DESTINATION ${CATKIN_PACKAGE_INCLUDE_DESTINATION}
)

catkin_install_python(PROGRAMS scripts/keyboard_node.py
    DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
)
