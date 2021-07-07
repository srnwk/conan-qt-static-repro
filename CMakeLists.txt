cmake_minimum_required(VERSION 3.17)

project(example)

set(CMAKE_INCLUDE_CURRENT_DIR ON)

set(CMAKE_AUTOUIC ON)
set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

list(APPEND CMAKE_MODULE_PATH ${CMAKE_CURRENT_BINARY_DIR}/conan)

find_package(Qt6 COMPONENTS Widgets REQUIRED)

qt_add_executable(example
    MANUAL_FINALIZATION
    main.cpp
)
target_link_libraries(example PRIVATE Qt6::Widgets)
qt_finalize_executable(example)
