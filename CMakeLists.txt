cmake_minimum_required (VERSION 3.5)

include("cmake/HunterGate.cmake")
HunterGate(
  URL "https://github.com/ruslo/hunter/archive/v0.16.3.tar.gz"
  SHA1 "9a9ef7e83c822f95de7b32f44114fa1b1edda5d0"
)
project (4K_displaywall_bench)

hunter_add_package(glfw)
find_package(glfw3 REQUIRED)

hunter_add_package(glm)
find_package(glm REQUIRED)

add_executable (4K_displaywall_bench main.cpp Scene.cpp png/lodepng.cpp glad/glad.c)
target_include_directories(4K_displaywall_bench PRIVATE "${CMAKE_CURRENT_SOURCE_DIRECTORY}")
target_compile_definitions(4K_displaywall_bench PRIVATE _USE_MATH_DEFINES)

target_link_libraries(4K_displaywall_bench glfw glm)
