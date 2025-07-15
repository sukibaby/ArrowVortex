file(GLOB SRC "${CMAKE_CURRENT_SOURCE_DIR}/*.cpp")
file(GLOB INC "${CMAKE_CURRENT_SOURCE_DIR}/*.h")

add_library(Editor STATIC ${SRC} ${INC})

target_include_directories(Editor PRIVATE 
	"${CMAKE_SOURCE_DIR}/submodules/libmad" 
	"${CMAKE_SOURCE_DIR}/submodules/ogg/include" 
	"${CMAKE_SOURCE_DIR}/submodules/vorbis/include"
)
target_link_libraries(Editor PRIVATE Core Dialogs 
	"${CMAKE_SOURCE_DIR}/submodules/libmad/obj/mad.lib" 
	Managers Simfile System 
	"${CMAKE_SOURCE_DIR}/submodules/libvorbis/obj/vorbisfile.lib" 
	"${CMAKE_SOURCE_DIR}/submodules/libvorbis/obj/vorbis.lib" 
	"${CMAKE_SOURCE_DIR}/submodules/ogg/obj/ogg.lib"
)
