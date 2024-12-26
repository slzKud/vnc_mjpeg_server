project(mjpeg_server C)
cmake_minimum_required(VERSION 3.2)

set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} ${CMAKE_CURRENT_SOURCE_DIR}/cmake)

find_package(Pixman REQUIRED)
find_package(JPEG REQUIRED)
find_package(AML REQUIRED)
find_package(NeatVNC REQUIRED)

message(STATUS "pixman_INCLUDE_DIRS = ${PIXMAN_INCLUDE_DIRS}")
message(STATUS "pixman_LIBS = ${PIXMAN_LIBRARIES}")
message(STATUS "JPEG_INCLUDE_DIRS = ${JPEG_INCLUDE_DIRS}")
message(STATUS "JPEG_LIBRARIES = ${JPEG_LIBRARIES}")
message(STATUS "AML_INCLUDE_DIRS = ${AML_INCLUDE_DIRS}")
message(STATUS "AML_LIBS = ${AML_LIBRARIES}")
message(STATUS "NeatVNC_INCLUDE_DIRS = ${NeatVNC_INCLUDE_DIRS}")
message(STATUS "NeatVNC_LIBS = ${NeatVNC_LIBRARIES}")

set(SRCS mjpeg-server.c jpgfb.c)
include_directories(${PIXMAN_INCLUDE_DIRS} ${JPEG_INCLUDE_DIRS} ${NeatVNC_INCLUDE_DIRS})
add_executable(mjpeg_server ${SRCS})
target_link_libraries(mjpeg_server rt pthread ${PIXMAN_LIBRARIES} ${AML_LIBRARIES} ${JPEG_LIBRARIES} ${NeatVNC_LIBRARIES})


