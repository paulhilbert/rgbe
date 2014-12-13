cmake_minimum_required(VERSION 2.8.8)
project(rgbe)

set (rgbe_VERSION_MAJOR 0)
set (rgbe_VERSION_MINOR 1)

include_directories("${PROJECT_SOURCE_DIR}")
include_directories("${PROJECT_BINARY_DIR}")
include_directories("${PROJECT_SOURCE_DIR}/include")


file (GLOB_RECURSE obj RELATIVE "${PROJECT_SOURCE_DIR}" "src/*.c")
add_library(rgbe SHARED ${obj})
target_link_libraries(rgbe "dl")

# install binary
install (TARGETS rgbe DESTINATION lib)
# install header
install (DIRECTORY include/ DESTINATION include/rgbe)
