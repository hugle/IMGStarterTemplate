# CMakeList.txt : CMake project for VisQuantRepo, include source and define
# project specific logic here.
#
cmake_minimum_required (VERSION 3.8)

project ("VisQuant")

add_executable (VisQuant "VisQuant/GUI/vqui.cpp" "VisQuant/GUI/vqui.h" "VisQuant/GUI/guisample.cpp")

find_package(glad CONFIG REQUIRED)
target_link_libraries(VisQuant PRIVATE glad::glad)

find_package(glfw3 CONFIG REQUIRED)
target_link_libraries(VisQuant PRIVATE glfw)

find_package(imgui CONFIG REQUIRED)
target_link_libraries(VisQuant PRIVATE imgui::imgui)

if (CMAKE_VERSION VERSION_GREATER 3.12)
  set_property(TARGET VisQuant PROPERTY CXX_STANDARD 20)
endif()
