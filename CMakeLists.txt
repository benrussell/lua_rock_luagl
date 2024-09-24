cmake_minimum_required(VERSION 3.17)
project(lua_rock_luagl)

set(CMAKE_CXX_STANDARD 20)



set( LNK_LIN third_party/libs/linux )
LINK_DIRECTORIES( ${LNK_LIN} )

link_libraries(
        luajit
)


set( LUAGL_SRC
        luagl_src/luagl.c
        luagl_src/luagl.h
        luagl_src/luagl_const.c
        luagl_src/luagl_const.h
        luagl_src/luagl_util.c
        luagl_src/luagl_util.h
        )

include_directories( third_party/LuaJIT-2.1/src )

add_library(luagl SHARED ${LUAGL_SRC} )
SET_TARGET_PROPERTIES(luagl PROPERTIES PREFIX  "" )

subdirs(
        cmake_glu

)
