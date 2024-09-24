cmake_minimum_required(VERSION 3.17)
project(lua_rock_luaglu)

set(CMAKE_CXX_STANDARD 20)




set( LNK_LIN third_party/libs/linux )
LINK_DIRECTORIES( ${LNK_LIN} )

link_libraries(
        luajit
)




include_directories( ../third_party/LuaJIT-2.1/src )

set( LUAGLU_SRC
        ../luagl_src/luaglu.c
        ../luagl_src/luaglu.h
        ../luagl_src/luagl_const.c
        ../luagl_src/luagl_const.h
        ../luagl_src/luagl_util.c
        ../luagl_src/luagl_util.h
        )


add_library(luaglu SHARED ${LUAGLU_SRC} )
SET_TARGET_PROPERTIES(luaglu PROPERTIES PREFIX  "" )