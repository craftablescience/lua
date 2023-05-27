cmake_minimum_required(VERSION 3.16)
project(lua LANGUAGES C)
set(CMAKE_C_STANDARD 11)

file(GLOB LUA_SOURCES "${CMAKE_CURRENT_SOURCE_DIR}/*.c" "${CMAKE_CURRENT_SOURCE_DIR}/*.h")
add_library(${PROJECT_NAME} STATIC ${LUA_SOURCES})

target_link_libraries(${PROJECT_NAME} PRIVATE m)

target_include_directories(${PROJECT_NAME}
        PUBLIC
        "${CMAKE_CURRENT_SOURCE_DIR}")

add_library(lua::lua ALIAS lua)
