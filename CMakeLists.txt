project(fire_wasm_sdl)
cmake_minimum_required(VERSION 2.8)

# Point to our own cmake modules
list(APPEND CMAKE_MODULE_PATH ${CMAKE_SOURCE_DIR}/CMakeModules)

# Find SDL2
find_package(SDL2 REQUIRED)

# Add global definitions
add_definitions("-Wall")
include_directories(${SDL2_INCLUDE_DIR})

add_executable(fire_wasm_sdl hsltorgb.c main.c)
install(TARGETS fire_wasm_sdl DESTINATION bin)
target_link_libraries(fire_wasm_sdl ${SDL2_LIBRARIES})
