cmake_minimum_required(VERSION 3.26)
project(GameOfLife LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 23)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

find_package(Qt6 REQUIRED COMPONENTS Widgets)
qt_standard_project_setup()

set(SOURCE
    src/main.cpp
)

qt_add_executable(GameOfLife ${SOURCE})
target_link_libraries(GameOfLife PRIVATE Qt6::Widgets)

if(MSVC)
    set_target_properties(GameOfLife PROPERTIES WIN32_EXECUTABLE ON)
endif()
