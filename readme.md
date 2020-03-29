## Lua with CMake for Windows.

This is lua 5.3 with some CMakeLists files for building various combos of the libraries, interpreter and compiler on Windows.

It _might_ work on other platforms too, since it's a pretty straightforward project, but no guarantees.

Take a look at doc/readme.html for the actual lua "getting started" readme. 

### Modifications vs. the original source tarball

Apart from adding CMakeLists files and removing Makefiles, I've uncommented the **LUA_BUILD_AS_DLL** preprocessor macro definition in order to use it to build the libs + core as a dll.

Take a look at the source files for the original licence info.

## Outputs

There are five targets defined herein:
- Lua core + libs as a static lib
- Lua core + libs as a dynamic lib
- Lua compiler executable, linked statically vs. core + libs
- Lua interpreter executable, linked statically vs. core + libs
- Lua interpreter executable, linked dynamically vs. core + libs