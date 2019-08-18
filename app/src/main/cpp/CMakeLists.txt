
cmake_minimum_required(VERSION 3.4.1)
add_library(
        native-lib
        SHARED
        native-lib.cpp)
include_directories(src/main/cpp/include)
set(CMAKE_CXX_FLAGS  "${CMAKE_CXX_FLAGS} -L ../../../../libs/${ANDROID_ABI}")
find_library(
        log-lib
        log)


target_link_libraries(
        native-lib
        avcodec avfilter avformat avutil swresample swscale
        ${log-lib})