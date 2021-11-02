# Some config
cmake_minimum_required(VERSION 3.17)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_MODULE_PATH ${CMAKE_CURRENT_SOURCE_DIR}/raylib)

if (MSVC OR MSYS)
    #do something
endif()

if (WIN32)
    #do something
endif()

if(UNIX AND NOT APPLE)
    set(CMAKE_CXX_FLAGS "-W -Wall -Wextra -Wno-missing-field-initializers")
endif()

if(APPLE)
    set(CMAKE_CXX_FLAGS "-W -Wall -Wextra -Wno-missing-field-initializers")
endif()

# Project name
project(indie_studio VERSION 1.0)
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/include)

# Files
file(GLOB_RECURSE SRC_FILES CONFIGURE_DEPENDS
    ${CMAKE_CURRENT_SOURCE_DIR}/src/*.cpp
)
find_package(raylib REQUIRED)

# Add main project 
add_executable(bomberman ${SRC_FILES})
target_link_libraries(bomberman PUBLIC raylib)
