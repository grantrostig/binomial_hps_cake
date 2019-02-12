cmake_minimum_required(VERSION 3.3.2)
set(CMAKE_VERBOSE_MAKEFILE ON)

# HPX requires this since HPX is in a custom directory in this case called "libs"  yes. bad name.
#set(CMAKE_PREFIX_PATH=/home/grostig/libs) # apparently no = should be used?
set(CMAKE_PREFIX_PATH /home/grostig/libs)

# below line seems to be required by QtCreator when editing *.cpp files and using HPX headers.
include_directories(/home/grostig/libs/include)

project(binomial_hpx_cmake)
find_package(HPX REQUIRED)

# here are some guesses I'm making???
# add_library( IMPORTED_LIBNAME = ??)
# target_link_libraries( )

# add_executable(${PROJECT_NAME} "main.cpp" )  # this form of "adding" makes makes QtCreator happy, but,
# when using the just "app_executable(), and the addition of "COMPONENT_DEPENDENCIES iostreams"
# causes cmake error or: Cannot find source file, and No SOURCES given to target:binomial_hpx_make
add_hpx_executable(${PROJECT_NAME} main.cpp COMPONENT_DEPENDENCIES iostreams)

