cmake_minimum_required(VERSION 2.8)

project(mpp_linux_cpp)


set(CMAKE_CXX_STANDARD 11)
include_directories(include)

set(SOURCE_FILES main.cpp
        mpp/Codec.cpp
        thread/Thread.cpp
        rkrga/RGA.cpp
        rkdrm/bo.c
        rkdrm/dev.c
        rkdrm/modeset.c)

add_executable(mpp_linux_cpp ${SOURCE_FILES})
target_link_libraries(mpp_linux_cpp rockchip_mpp pthread drm)
install(TARGETS mpp_linux_cpp  DESTINATION bin)
