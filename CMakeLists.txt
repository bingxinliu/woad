# cmake needs this line

cmake_minimum_required(VERSION 3.1)



# Enable C++11

set(CMAKE_CXX_STANDARD 11)

set(CMAKE_CXX_STANDARD_REQUIRED TRUE)



# Define project name

project(woad)



# Find OpenCV, you may need to set OpenCV_DIR variable

# to the absolute path to the directory containing OpenCVConfig.cmake file

# via the command line or GUI

set(OpenCV_DIR /home/lbx/opencv_4.5/opencv/build)

find_package(OpenCV REQUIRED)



# If the package has been found, several variables will

# be set, you can find the full list with descriptions

# in the OpenCVConfig.cmake file.

# Print some message showing some of them

message(STATUS "OpenCV library status:")

message(STATUS "    config: ${OpenCV_DIR}")

message(STATUS "    version: ${OpenCV_VERSION}")

message(STATUS "    libraries: ${OpenCV_LIBS}")

message(STATUS "    include path: ${OpenCV_INCLUDE_DIRS}")



# Declare the executable target built from your sources

#add_executable(parameters_with_postfilter parameters_with_postfilter.cpp)
#add_executable(woad_cuda woad_cuda.cpp)
#add_executable(woad_sgbm woad_sgbm.cpp)
add_executable(woad_sgm woad_sgm.cpp)



# Link your application with OpenCV libraries

#target_link_libraries(parameters_with_postfilter LINK_PRIVATE ${OpenCV_LIBS})
#target_link_libraries(woad_cuda LINK_PRIVATE ${OpenCV_LIBS})
#target_link_libraries(woad_sgbm LINK_PRIVATE ${OpenCV_LIBS})
target_link_libraries(woad_sgm LINK_PRIVATE ${OpenCV_LIBS})

