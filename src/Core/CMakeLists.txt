file(GLOB SRC "${CMAKE_CURRENT_SOURCE_DIR}/*.cpp")
file(GLOB INC "${CMAKE_CURRENT_SOURCE_DIR}/*.h")

add_library(Core STATIC ${SRC} ${INC})

target_include_directories(Core PRIVATE "${CMAKE_SOURCE_DIR}/submodules/freetype/include")

#  I Don't have something to build this lib yet 
target_link_libraries(Core PRIVATE "${CMAKE_SOURCE_DIR}/submodules/freetype/obj/freetype.lib" System OpenGL::GL)
