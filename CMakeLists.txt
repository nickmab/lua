cmake_minimum_required (VERSION 3.15)

Project ("Lua")

if (WIN32)
    add_compile_definitions (LUA_USE_WINDOWS)
else ()
    message (WARNING "The CMakeLists here have only been tested on windows...")
endif ()

add_subdirectory ("src")