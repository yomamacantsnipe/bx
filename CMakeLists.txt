CMAKE_MINIMUM_REQUIRED(VERSION 2.8)

project(BX CXX)

set(SRC src/amalgamated.cpp)

include_directories(
        include

        # Dependencies ini
        3rdparty
)

add_definitions(-DBX_CONFIG_DEBUG=0)

set(CMAKE_CXX_STANDARD 20)

add_library(bx STATIC ${SRC})