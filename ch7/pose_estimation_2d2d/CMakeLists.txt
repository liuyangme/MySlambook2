cmake_minimum_required(VERSION 3.21)
project(pose_estimation_2d2d)

set(CMAKE_CXX_STANDARD 14)

# OpenCV
find_package(OpenCV REQUIRED)
include_directories(${OpenCV_INCLUDE_DIRS})

# Ceres
find_package(Ceres REQUIRED)
include_directories(${CERES_INCLUDE_DIRS})

# g2o
list( APPEND CMAKE_MODULE_PATH /home/liuyang/MySLAM/SLAMProgramming/MySlambook2/ch7/orb_cv/cmake )
set(G2O_ROOT /usr/local/include/g2o)
find_package(G2O REQUIRED)
include_directories(${G2O_INCLUDE_DIRS})

# Eigen
include_directories("/usr/include/eigen3")

add_executable(pose_estimation_2d2d main.cpp)
target_link_libraries(pose_estimation_2d2d ${OpenCV_LIBS})
