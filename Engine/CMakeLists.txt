cmake_minimum_required(VERSION 3.26)
project(Engine)

# Find dependencies
find_package(glfw3 CONFIG REQUIRED)
find_package(glad CONFIG REQUIRED)
find_package(glm CONFIG REQUIRED)
find_package(Freetype REQUIRED)
find_package(imgui CONFIG REQUIRED)

# stb does not have a CMake build, but is header-only
find_path(STB_INCLUDE_DIRS "stb.h")


add_library(Engine Test.cpp
        Window.cpp
        Window.h)


target_link_libraries(
        Engine
        PRIVATE
        glfw
        glad::glad
        glm::glm
        imgui::imgui
        Freetype::Freetype
)

install(TARGETS Engine
        LIBRARY DESTINATION lib
        ARCHIVE DESTINATION lib)