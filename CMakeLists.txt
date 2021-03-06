cmake_minimum_required(VERSION 3.0.2)
project(butler_bringup)

find_package(catkin REQUIRED COMPONENTS geometry_msgs roscpp tf tf2_ros)

catkin_package()

###########
## Build ##
###########

include_directories(${catkin_INCLUDE_DIRS})

# Butler Broadcaster
add_executable(butler_tf_broadcaster src/butler_tf_broadcaster.cpp)

if(geometry_msgs_EXPORTED_TARGETS)
  add_dependencies(butler_tf_broadcaster ${geometry_msgs_EXPORTED_TARGETS})
endif()

target_link_libraries(butler_tf_broadcaster ${catkin_LIBRARIES})

# Butler Base_link Broadcaster
add_executable(butler_base_link_tf_br src/butler_base_link_tf_br.cpp)

if(geometry_msgs_EXPORTED_TARGETS)
  add_dependencies(butler_base_link_tf_br ${geometry_msgs_EXPORTED_TARGETS})
endif()

target_link_libraries(butler_base_link_tf_br ${catkin_LIBRARIES})

# Butler Listener
add_executable(butler_tf_listener src/butler_tf_listener.cpp)

if(geometry_msgs_EXPORTED_TARGETS)
  add_dependencies(butler_tf_listener ${geometry_msgs_EXPORTED_TARGETS})
endif()

target_link_libraries(butler_tf_listener ${catkin_LIBRARIES})

# Butler Base_link Listener
add_executable(butler_base_link_tf_ls src/butler_base_link_tf_ls.cpp)

if(geometry_msgs_EXPORTED_TARGETS)
  add_dependencies(butler_base_link_tf_ls ${geometry_msgs_EXPORTED_TARGETS})
endif()

target_link_libraries(butler_base_link_tf_ls ${catkin_LIBRARIES})

######## ADDED FRAMES #######

######## WHEELS #########

# Left Wheel Broadcaster

add_executable(butler_left_wheel_tf_br src/butler_left_wheel_tf_br.cpp)
target_link_libraries(butler_left_wheel_tf_br
 ${catkin_LIBRARIES}
)

# Left Wheel Listener

add_executable(butler_left_wheel_tf_ls src/butler_left_wheel_tf_ls.cpp)
target_link_libraries(butler_left_wheel_tf_ls
 ${catkin_LIBRARIES}
)

# Right Wheel Broadcaster

add_executable(butler_right_wheel_tf_br src/butler_right_wheel_tf_br.cpp)
target_link_libraries(butler_right_wheel_tf_br
 ${catkin_LIBRARIES}
)

# Right Wheel Listener

add_executable(butler_right_wheel_tf_ls src/butler_right_wheel_tf_ls.cpp)
target_link_libraries(butler_right_wheel_tf_ls
 ${catkin_LIBRARIES}
)

######## SWIVELS #########

# Front Left Swivel Broadcaster

add_executable(butler_front_left_swivel_tf_br src/butler_front_left_swivel_tf_br.cpp)
target_link_libraries(butler_front_left_swivel_tf_br
 ${catkin_LIBRARIES}
)

# Front Left Swivel Listener

add_executable(butler_front_left_swivel_tf_ls src/butler_front_left_swivel_tf_ls.cpp)
target_link_libraries(butler_front_left_swivel_tf_ls
 ${catkin_LIBRARIES}
)

# Back Left Swivel Broadcaster

add_executable(butler_back_left_swivel_tf_br src/butler_back_left_swivel_tf_br.cpp)
target_link_libraries(butler_back_left_swivel_tf_br
 ${catkin_LIBRARIES}
)

# Back Left Swivel Listener

add_executable(butler_back_left_swivel_tf_ls src/butler_back_left_swivel_tf_ls.cpp)
target_link_libraries(butler_back_left_swivel_tf_ls
 ${catkin_LIBRARIES}
)

# Front Right Swivel Broadcaster

add_executable(butler_front_right_swivel_tf_br src/butler_front_right_swivel_tf_br.cpp)
target_link_libraries(butler_front_right_swivel_tf_br
 ${catkin_LIBRARIES}
)

# Front Right Swivel Listener

add_executable(butler_front_right_swivel_tf_ls src/butler_front_right_swivel_tf_ls.cpp)
target_link_libraries(butler_front_right_swivel_tf_ls
 ${catkin_LIBRARIES}
)

# Back Right Swivel Broadcaster

add_executable(butler_back_right_swivel_tf_br src/butler_back_right_swivel_tf_br.cpp)
target_link_libraries(butler_back_right_swivel_tf_br
 ${catkin_LIBRARIES}
)

# Back Right Swivel Listener

add_executable(butler_back_right_swivel_tf_ls src/butler_back_right_swivel_tf_ls.cpp)
target_link_libraries(butler_back_right_swivel_tf_ls
 ${catkin_LIBRARIES}
)

######## CASTERS ########

# Front Left Caster Broadcaster

add_executable(butler_front_left_caster_tf_br src/butler_front_left_caster_tf_br.cpp)
target_link_libraries(butler_front_left_caster_tf_br
 ${catkin_LIBRARIES}
)

# Front Left Caster Listener

add_executable(butler_front_left_caster_tf_ls src/butler_front_left_caster_tf_ls.cpp)
target_link_libraries(butler_front_left_caster_tf_ls
 ${catkin_LIBRARIES}
)

# Back Left Caster Broadcaster

add_executable(butler_back_left_caster_tf_br src/butler_back_left_caster_tf_br.cpp)
target_link_libraries(butler_back_left_caster_tf_br
 ${catkin_LIBRARIES}
)

# Back Left Caster Listener

add_executable(butler_back_left_caster_tf_ls src/butler_back_left_caster_tf_ls.cpp)
target_link_libraries(butler_back_left_caster_tf_ls
 ${catkin_LIBRARIES}
)

# Front Right Caster Broadcaster

add_executable(butler_front_right_caster_tf_br src/butler_front_right_caster_tf_br.cpp)
target_link_libraries(butler_front_right_caster_tf_br
 ${catkin_LIBRARIES}
)

# Front Right Caster Listener

add_executable(butler_front_right_caster_tf_ls src/butler_front_right_caster_tf_ls.cpp)
target_link_libraries(butler_front_right_caster_tf_ls
 ${catkin_LIBRARIES}
)

# Back Right Caster Broadcaster

add_executable(butler_back_right_caster_tf_br src/butler_back_right_caster_tf_br.cpp)
target_link_libraries(butler_back_right_caster_tf_br
 ${catkin_LIBRARIES}
)

# Back Right Caster Listener

add_executable(butler_back_right_caster_tf_ls src/butler_back_right_caster_tf_ls.cpp)
target_link_libraries(butler_back_right_caster_tf_ls
 ${catkin_LIBRARIES}
)

######## LASERS ########

# Front Laser Broadcaster
add_executable(butler_front_laser_tf_br src/butler_front_laser_tf_br.cpp)
target_link_libraries(butler_front_laser_tf_br
 ${catkin_LIBRARIES}
)

# Front Laser Listener

add_executable(butler_front_laser_tf_ls src/butler_front_laser_tf_ls.cpp)
target_link_libraries(butler_front_laser_tf_ls
 ${catkin_LIBRARIES}
)

# Rear Laser Broadcaster
add_executable(butler_rear_laser_tf_br src/butler_rear_laser_tf_br.cpp)
target_link_libraries(butler_rear_laser_tf_br
 ${catkin_LIBRARIES}
)

# Rear Laser Listener

add_executable(butler_rear_laser_tf_ls src/butler_rear_laser_tf_ls.cpp)
target_link_libraries(butler_rear_laser_tf_ls
 ${catkin_LIBRARIES}
)

######## Camera ########

# Front Camera Broadcaster
add_executable(butler_front_camera_tf_br src/butler_front_camera_tf_br.cpp)
target_link_libraries(butler_front_camera_tf_br
 ${catkin_LIBRARIES}
)

# Front Camera Listener

add_executable(butler_front_camera_tf_ls src/butler_front_camera_tf_ls.cpp)
target_link_libraries(butler_front_camera_tf_ls
 ${catkin_LIBRARIES}
)


# Install the executable
install(TARGETS butler_tf_broadcaster butler_base_link_tf_br butler_tf_listener butler_base_link_tf_ls
  ARCHIVE DESTINATION ${CATKIN_PACKAGE_LIB_DESTINATION}
  LIBRARY DESTINATION ${CATKIN_PACKAGE_LIB_DESTINATION}
  RUNTIME DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION})

## Mark other files for installation (e.g. launch and bag files, etc.)
install(FILES
  butler_robot_commissary.launch
  coach_butler_robot_gazebo.launch
  coach_butler_robot_rviz_bringup.launch
  commissary_v2.launch
  butler_tf.launch
  
  # myfile2
 DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)
