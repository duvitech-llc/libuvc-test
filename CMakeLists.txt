cmake_minimum_required(VERSION 3.10)

project(libuvctest VERSION 1.0)

# specify the C++ standard
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED True)

find_package(JPEG REQUIRED)
find_package(libuvc REQUIRED)


add_executable(libuvctest libuvc_test.cxx)

configure_file(libuvc_test.h.in libuvc_test.h)

target_include_directories(libuvctest PUBLIC
                           "${PROJECT_BINARY_DIR}"
                           )

target_link_libraries (libuvctest uvc)
