# CMakeLists.txt

cmake_minimum_required(VERSION 3.10)
project(MyProject)

# Set the C++ standard
set(CMAKE_CXX_STANDARD 11)

# Find the package using pkg-config
find_package(PkgConfig REQUIRED)
pkg_check_modules(REDIS3M REQUIRED /usr/local/pkgconfig/redis3m.pc)

# Include directories
include_directories(${REDIS3M_INCLUDE_DIRS})

# Add the executable
add_executable(main main.cpp)

# Link libraries
target_link_libraries(main ${REDIS3M_LIBRARIES})
