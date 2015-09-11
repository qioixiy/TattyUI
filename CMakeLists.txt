PROJECT (TattyUI)
cmake_minimum_required(VERSION 2.6)

#head file path
INCLUDE_DIRECTORIES(
	"${CMAKE_SOURCE_DIR}/"
	"${CMAKE_SOURCE_DIR}/dependency/glfw/include/"
	"${CMAKE_SOURCE_DIR}/dependency/glew/include/"
	"${CMAKE_SOURCE_DIR}/dependency/glm"
)

# print
MESSAGE(STATUS "sssssssssssss " ${CMAKE_SOURCE_DIR})

link_directories(
	"${CMAKE_SOURCE_DIR}/dependency/glfw/lib/"
	"${CMAKE_SOURCE_DIR}/dependency/glew/lib/"
	"${CMAKE_SOURCE_DIR}/dependency/glm/Debug/"
)

#AUX_SOURCE_DIRECTORY(src DIR_SRCS)

#set envirronment variable
#SET(t3DS ${t3DS_SRCS})

#add file to ide
# entrance
FILE(GLOB MAIN "./TattyUI/*.h") 
SOURCE_GROUP("TattyUI" FILES ${MAIN})

# atom
FILE(GLOB div_h "./TattyUI/div/*.h") 
SOURCE_GROUP("TattyUI\\div" FILES ${div_h})

FILE(GLOB div_cpp "./TattyUI/div/*.cpp") 
SOURCE_GROUP("TattyUI\\div" FILES ${div_cpp})

# common
FILE(GLOB common_h "./TattyUI/common/*.h") 
SOURCE_GROUP("TattyUI\\common" FILES ${common_h})

FILE(GLOB common_cpp "./TattyUI/common/*.cpp") 
SOURCE_GROUP("TattyUI\\common" FILES ${common_cpp})

# render
# tattyRenderer
FILE(GLOB t2_render_h "./TattyUI/render/*.h") 
SOURCE_GROUP("TattyUI\\render" FILES ${t2_render_h})

FILE(GLOB t2_render_cpp "./TattyUI/render/*.cpp") 
SOURCE_GROUP("TattyUI\\render" FILES ${t2_render_cpp})

# nanovg
FILE(GLOB render_h "./TattyUI/render/nanovg/src/*.h" ) 
SOURCE_GROUP("TattyUI\\render\\nanovg" FILES ${render_h})

FILE(GLOB renderer_cpp "./TattyUI/render/nanovg/src/*.cpp") 
SOURCE_GROUP("TattyUI\\render\\nanovg" FILES ${render_cpp})

FILE(GLOB render_c "./TattyUI/render/nanovg/src/*.c") 
SOURCE_GROUP("TattyUI\\render\\nanovg" FILES ${render_c})

# widget
#FILE(GLOB widget_h "./TattyUI/widget/*.h") 
#SOURCE_GROUP("widget" FILES ${widget_h})

#FILE(GLOB widget_cpp "./TattyUI/widget/*.cpp") 
#SOURCE_GROUP("widget" FILES ${widget_cpp})

# script
FILE(GLOB script_h "./TattyUI/script/*.h") 
SOURCE_GROUP("TattyUI\\script" FILES ${script_h})

FILE(GLOB script_cpp "./TattyUI/script/*.cpp") 
SOURCE_GROUP("TattyUI\\script" FILES ${script_cpp})

FILE(GLOB script_h "./TattyUI/script/css/*.h") 
SOURCE_GROUP("TattyUI\\script\\css" FILES ${script_h})

FILE(GLOB script_cpp "./TattyUI/script/css/*.cpp") 
SOURCE_GROUP("TattyUI\\script\\css" FILES ${script_cpp})

# event
FILE(GLOB event_h "./TattyUI/controller/event/*.h") 
SOURCE_GROUP("TattyUI\\controller\\event" FILES ${event_h})

FILE(GLOB event_cpp "./TattyUI/controller/event/*.cpp") 
SOURCE_GROUP("TattyUI\\controller\\event" FILES ${event_cpp})

# # layout
# FILE(GLOB layout_h "./TattyUI/layout/*.h") 
# SOURCE_GROUP("layout" FILES ${layout_h})

# FILE(GLOB layout_cpp "./TattyUI/layout/*.cpp") 
# SOURCE_GROUP("layout" FILES ${layout_cpp})

# main and test
FILE(GLOB test_h "./TattyUI/test/*.h") 
SOURCE_GROUP("test" FILES ${test_h})

FILE(GLOB test_cpp "./TattyUI/test/*.cpp") 
SOURCE_GROUP("test" FILES ${test_cpp})

#add executable file
ADD_EXECUTABLE(TattyUI ${MAIN} 
	${div_h} ${div_cpp}
	${common_h} ${common_cpp} 
	${render_h} ${render_cpp} ${render_c}
	${t2_render_h} ${t2_render_cpp}
	${test_h} ${test_cpp}
	${event_h} ${event_cpp}
	${script_h} ${script_cpp})


	# ${layout_h} ${layout_cpp}
	
	# $(widget_h) $(widget_cpp)

# # dependency
TARGET_LINK_LIBRARIES(TattyUI glfw3)  
TARGET_LINK_LIBRARIES(TattyUI glew32s)
TARGET_LINK_LIBRARIES(TattyUI glm)
TARGET_LINK_LIBRARIES(TattyUI OpenGL32)