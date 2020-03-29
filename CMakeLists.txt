cmake_minimum_required (VERSION 3.15)

Project ("Lua")

if (NOT WIN32)
    message (WARNING "The CMakeLists here have only been tested on windows...")
endif ()

if (MSVC)
    add_compile_options(/MP)
endif ()

if ("${CMAKE_BUILD_TYPE}" STREQUAL "Debug")
    add_compile_definitions (LUA_DEBUG)
endif ()

add_subdirectory ("src")