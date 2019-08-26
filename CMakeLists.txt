cmake_minimum_required(VERSION 3.13)
project(matplotcpp)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_EXE_LINKER_FLAGS "-Xlinker -export-dynamic")

include_directories(ext/plot/ /opt/share/.pyenv/versions/3.7.3/include/python3.7m)
link_directories(/opt/share/.pyenv/versions/3.7.3/lib/python3.7/config-3.7m-x86_64-linux-gnu /opt/share/.pyenv/versions/3.7.3/lib)

add_executable(matplotcpp main.cpp matplotlibcpp.h)

target_link_libraries(matplotcpp python3.7m pthread crypt dl util m opencv_core opencv_imgproc)