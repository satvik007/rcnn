cmake_minimum_required(VERSION 3.19)
project(rcnn)
set(CMAKE_CXX_STANDARD 14)

find_package( OpenCV REQUIRED )
set(CMAKE_PREFIX_PATH "/home/satvik/Software/libtorch")

find_package(Torch REQUIRED)
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} ${TORCH_CXX_FLAGS}")

include_directories( ${OpenCV_INCLUDE_DIRS} )

add_executable(rcnn main.cpp)
target_link_libraries( rcnn ${OpenCV_LIBS} )
target_link_libraries( rcnn ${TORCH_LIBRARIES} )
