cmake_minimum_required (VERSION 3.15)

set (CORE_SRC
     lapi.c 
     lcode.c
     lctype.c
     ldebug.c
     ldo.c
     ldump.c
     lfunc.c
     lgc.c
     llex.c
     lmem.c
     lobject.c
     lopcodes.c
     lparser.c
     lstate.c
     lstring.c
     ltable.c
     ltm.c
     lundump.c
     lvm.c
     lzio.c)
	
set (LIB_SRC
     lauxlib.c
     lbaselib.c
     lbitlib.c
     lcorolib.c
     ldblib.c
     liolib.c	    
     lmathlib.c
     loslib.c
     lstrlib.c
     ltablib.c
     lutf8lib.c
     loadlib.c
     linit.c)

set (INTERPRETER_SRC lua.c)

add_library (lua_static_lib STATIC ${CORE_SRC} ${LIB_SRC})

add_executable (lua_compiler luac.c)
target_link_libraries(lua_compiler lua_static_lib)

add_library (lua_dynamic_lib SHARED ${CORE_SRC} ${LIB_SRC})
target_compile_definitions (lua_dynamic_lib PUBLIC LUA_BUILD_AS_DLL)

add_executable (lua_interpreter_dynamic lua.c)
target_link_libraries(lua_interpreter_dynamic lua_dynamic_lib)

add_executable (lua_interpreter_static lua.c)
target_link_libraries(lua_interpreter_static lua_static_lib)
