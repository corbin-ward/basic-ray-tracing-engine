cmake_minimum_required ( VERSION 3.1.0...4.0.0 )

project ( RTWeekend LANGUAGES CXX )

# Set to C++11
set ( CMAKE_CXX_STANDARD          11 )
set ( CMAKE_CXX_STANDARD_REQUIRED ON )
set ( CMAKE_CXX_EXTENSIONS        OFF )

# Source files
set ( SOURCES
    main.cpp
    vec3.h
    color.h
    ray.h
    hittable.h
    sphere.h
    hittable_list.h
    rte.h
    interval.h
)

# Executables
add_executable(rayTracingEngine ${SOURCES})

# Compiler warnings
if (CMAKE_CXX_COMPILER_ID STREQUAL "MSVC")
    add_compile_options("/W4" "/we4265" "/we5204" "/wd4100")
elseif (CMAKE_CXX_COMPILER_ID STREQUAL "GNU" OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
    add_compile_options(-Wnon-virtual-dtor -Wreorder -Wunused-variable)
endif()