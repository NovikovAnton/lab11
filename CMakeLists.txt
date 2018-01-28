cmake_minimum_required(VERSION 3.0)

set(CMAKE_CXX_STANDARD 11)

include(cmake/HunterGate.cmake)

HunterGate(URL "https://github.com/NovikovAnton/hunter/archive/v0.19.137.1.tar.gz" SHA1 "702d4455ddd76871b2ec74c2244a09a029621df1")

project(demo)

hunter_add_package(print)
find_package(print)

add_executable(demo ${CMAKE_CURRENT_SOURCE_DIR}/sources/demo.cpp)
target_link_libraries(demo print)

install(TARGETS demo RUNTIME DESTINATION bin)
