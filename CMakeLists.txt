cmake_minimum_required(VERSION 2.8.3)
project(barrett_model)

find_package(catkin REQUIRED COMPONENTS xacro)

catkin_package(CATKIN_DEPENDS xacro)

# NB: There are 2 URDFs for WAM 7 with different origins. Only building
set(xacro_files
    ${CMAKE_CURRENT_SOURCE_DIR}/robots/wam4.urdf.xacro
    ${CMAKE_CURRENT_SOURCE_DIR}/robots/wam7.urdf.xacro
    ${CMAKE_CURRENT_SOURCE_DIR}/robots/wam7_bhand.urdf.xacro
)

xacro_add_files(${xacro_files} INSTALL DESTINATION robots)

install(DIRECTORY models robots
        DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION})
