cmake_minimum_required(VERSION 3.3.2)
set(CMAKE_VERBOSE_MAKEFILE ON)

# HPX requires this since HPX is in a custom directory in this case called "libs"  yes. bad name.
set(CMAKE_PREFIX_PATH = /home/grostig/libs)

# below line seems to be required by QtCreator when editing *.cpp files and using HPX headers.
include_directories(/home/grostig/libs/include)

project(binomial_hpx_cmake)
find_package(HPX REQUIRED)
add_executable(${PROJECT_NAME} "main.cpp" COMPONENT_DEPENDENCIES iostreams)
# add_executable(${PROJECT_NAME} "main.cpp" )
