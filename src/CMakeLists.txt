﻿set(target "gtmaker")
message(STATUS "${target}")

include(../cmake_imgui.txt)
include(../cmake_tinyfd.txt)

project(${target})

file(GLOB MAIN *.h *.hpp *.cpp)
source_group("main" FILES ${MAIN})

add_executable(${target} ${MAIN} ${SUB})

set_target_properties(${target} PROPERTIES
	RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin/
)

target_link_libraries(${target} ${EX_LIBS} ${OpenGL_LIBS} ${OpenCV_LIBS})

