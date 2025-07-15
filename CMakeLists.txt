cmake_minimum_required(VERSION 3.30)

set(CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}/cmake")

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED True)

project(ArrowVortex)

set(CMAKE_CONFIGURATION_TYPES Debug Release)

include_directories("${PROJECT_SOURCE_DIR}/src")

## libmad, vorbis, ogg, freetype are provided via submodules
## be sure to run git submodule update --init --recursive before building
## idk what to do about openGL yet, using system package for now
## vorbis-tools are not used yet, so no need to build them, but they should be replacing oggenc2
find_package(OpenGL REQUIRED)

add_subdirectory(src/Core)
add_subdirectory(src/Dialogs)
add_subdirectory(src/Editor)
add_subdirectory(src/Managers)
add_subdirectory(src/Simfile)
add_subdirectory(src/System)

install(TARGETS ArrowVortex RUNTIME)
install(DIRECTORY bin/assets DESTINATION bin)
install(DIRECTORY bin/noteskins DESTINATION bin)
install(DIRECTORY bin/settings DESTINATION bin)
