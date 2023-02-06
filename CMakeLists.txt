cmake_minimum_required(VERSION 3.11.3)

set(CMAKE_CXX_STANDARD 17)

project(Membot)

find_package(wxWidgets REQUIRED COMPONENTS core base)
include(${wxWidgets_USE_FILE})

file(GLOB project_SRCS src/*.cpp)

add_executable(membot ${project_SRCS})
target_link_libraries(membot ${wxWidgets_LIBRARIES})
target_include_directories(membot PRIVATE ${wxWidgets_INCLUDE_DIRS})

# enable debugger own
# -O0 = optimization level 0 = turn off optimizations = all debugging info
# -ggdb = g*** debugging information format gdb = debugger for gcc
target_compile_options(membot PRIVATE -Wall -Wextra -O0 -ggdb)

# enable debugger according udacity mentor
# set( CMAKE_CXX_FLAGS "-g " )