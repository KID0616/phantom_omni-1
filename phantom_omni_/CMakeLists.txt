cmake_minimum_required(VERSION 2.8.3)
project(phantom_omni)

find_package(catkin REQUIRED COMPONENTS roscpp std_msgs geometry_msgs genmsg rosconsole tf urdf)

add_message_files(FILES PhantomButtonEvent.msg OmniFeedback.msg)

generate_messages(DEPENDENCIES geometry_msgs)

catkin_package(CATKIN_DEPENDS roscpp std_msgs geometry_msgs genmsg rosconsole tf urdf)

include_directories(${Boost_INCLUDE_DIR} ${catkin_INCLUDE_DIRS})

add_executable(omni_sim src/omni.cpp)

target_link_libraries(omni_sim rt ncurses ${catkin_LIBRARIES})


