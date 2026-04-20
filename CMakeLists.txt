cmake_minimum_required(VERSION 3.22)
project(lc3 C)

# Create static library
add_library(lc3 STATIC
    src/attdet.c
    src/bits.c
    src/bwdet.c
    src/energy.c
    src/lc3.c
    src/ltpf.c
    src/mdct.c
    src/plc.c
    src/sns.c
    src/spec.c
    src/tables.c
    src/tns.c
)

# Set C11 standard
set_property(TARGET lc3 PROPERTY C_STANDARD 11)
set_property(TARGET lc3 PROPERTY C_STANDARD_REQUIRED ON)

# Add compiler flags
target_compile_options(lc3 PRIVATE -ffast-math)

# Set public include directory
target_include_directories(lc3 PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/include)
