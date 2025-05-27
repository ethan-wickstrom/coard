cmake_minimum_required(VERSION 3.16)
project(coard C)

set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/build)  # *.a, *.lib
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/build)  # *.so, *.dll...
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin)    # executables

# ──────────────────────────────────────────────────────────────
# Project-wide compile & link flags
# ──────────────────────────────────────────────────────────────
add_compile_options(-O3 -save-temps)
add_link_options   (-O3)

# ──────────────────────────────────────────────────────────────
# Main program; equivalent to "bin/run" target
# ──────────────────────────────────────────────────────────────
file(GLOB_RECURSE SRC_FILES CONFIGURE_DEPENDS
        ${CMAKE_SOURCE_DIR}/src/*.c)

add_executable(run ${SRC_FILES})
target_include_directories(run PRIVATE ${CMAKE_SOURCE_DIR}/include)
target_link_directories  (run PRIVATE ${CMAKE_SOURCE_DIR}/lib)
