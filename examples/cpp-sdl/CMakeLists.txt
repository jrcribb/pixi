cmake_minimum_required(VERSION 3.7)
project(sdl_example)

find_package(SDL2 REQUIRED)

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/bin")

add_executable(${PROJECT_NAME} src/main.cc)

if (MSVC)
    set_target_properties(${PROJECT_NAME} PROPERTIES WIN32_EXECUTABLE TRUE)
endif()

target_link_libraries(
    ${PROJECT_NAME} PRIVATE
    SDL2::SDL2
    SDL2::SDL2main
)
