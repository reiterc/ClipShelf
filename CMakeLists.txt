cmake_minimum_required(VERSION 3.16)
project(ClipShelf LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

find_package(OpenGL REQUIRED)
find_package(glfw3 CONFIG REQUIRED)

set(SOURCE_FILES "")

# update when files are stable
file(GLOB_RECURSE SOURCE_FILES
     "${CMAKE_CURRENT_SOURCE_DIR}/src/*.cpp"
     "${CMAKE_CURRENT_SOURCE_DIR}/src/*.h")

add_executable(clip-shelf ${SOURCE_FILES})

# Link libraries
target_link_libraries(clip-shelf PRIVATE ${OPENGL_LIBRARIES}
                                         glfw
										 )
										 
target_include_directories(clip-shelf PRIVATE ${CMAKE_SOURCE_DIR}/src
										 )