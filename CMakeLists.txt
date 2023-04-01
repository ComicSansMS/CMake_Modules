cmake_minimum_required(VERSION 3.26)

set(CMAKE_EXPERIMENTAL_CXX_MODULE_CMAKE_API "2182bf5c-ef0d-489a-91da-49dbc3090d2a")
set(CMAKE_EXPERIMENTAL_CXX_MODULE_DYNDEP ON)

project(modules-example)

set(CMAKE_CXX_STANDARD 20)

add_executable(demo)
target_sources(demo
    PUBLIC
    main.cpp
)
target_sources(demo
  PUBLIC
    FILE_SET all_my_modules TYPE CXX_MODULES FILES
    a.cppm
)

set_property(DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR} PROPERTY VS_STARTUP_PROJECT demo)
