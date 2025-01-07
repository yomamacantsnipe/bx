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

set_target_properties(bx PROPERTIES LINKER_LANGUAGE CXX)
set_target_properties(bx PROPERTIES CXX_STANDARD 20)
set_target_properties(bx PROPERTIES CXX_STANDARD_REQUIRED ON)
set_target_properties(bx PROPERTIES CXX_EXTENSIONS OFF)

if (WIN32)
    target_compile_options(bx PRIVATE /Zc:__cplusplus /Zc:preprocessor)
    include_directories(../bx/include/compat/msvc)
endif()