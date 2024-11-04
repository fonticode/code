# Minimum CMake version required
cmake_minimum_required(VERSION 3.10)

# Project name and C++ standard
project(MySDL2Game)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED True)

# Find SDL2 package (you may need to adjust this depending on your system)
find_package(SDL2 REQUIRED)

# Include directories for SDL2
include_directories(${SDL2_INCLUDE_DIRS})

# Add the executable
add_executable(MySDL2Game Main.cpp Game.cpp)

# Link SDL2 library to the executable
target_link_libraries(MySDL2Game ${SDL2_LIBRARIES})

# Set output directory (optional)
set_target_properties(MySDL2Game PROPERTIES
    RUNTIME_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/bin"
)

