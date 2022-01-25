cmake_minimum_required(VERSION 3.22)
project(project VERSION 1.0.0
  DESCRIPTION project
  LANGUAGES CXX
  ) 
set(CMAKE_INCLUDE_CURRENT_DIR_IN_INTERFACE ON)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)
add_executable(project main.cxx)
find_package(myLib CONFIG REQUIRED)
target_link_libraries(project myLib) # installed include/ path automatically added






             