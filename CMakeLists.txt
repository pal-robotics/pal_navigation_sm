cmake_minimum_required(VERSION 2.8.3)
project(pal_navigation_sm)

find_package(catkin REQUIRED)

catkin_python_setup()

catkin_package()

install(
  PROGRAMS
    scripts/base_maps_symlink.sh
    scripts/cp_maps_to_home.sh
    scripts/cp_pose_to_home.sh
    scripts/map_setup.py
    scripts/navigation.sh
    scripts/pal_navigation_main_sm.py
  DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION})

foreach(dir config launch)
    install(DIRECTORY ${dir}/
        DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}/${dir})
endforeach()
