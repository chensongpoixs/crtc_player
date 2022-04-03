project(WebRTC)
CMAKE_MINIMUM_REQUIRED(VERSION 2.8)

MESSAGE(STATUS "#########################")

set(CMAKE_INCLUDE_CURRENT_DIR ON)
SET(CMAKE_VERBOSE_MAKEFILE ON)
set(CMAKE_AUTOUIC ON)
set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)


find_package(Qt5 COMPONENTS Widgets REQUIRED)
find_package(Qt5 COMPONENTS Core REQUIRED)
find_package(Qt5 COMPONENTS Gui REQUIRED)
find_package(Qt5 COMPONENTS Multimedia REQUIRED)
find_package(Qt5 COMPONENTS OpenGL REQUIRED)

add_subdirectory(YUV420Player)
add_subdirectory(WebRTCDemo)
#SET(CMAKE_BUILD_TYPE Release)
#ADD_DEFINITIONS(-std=c++11 -g -Wall )
#
#if (APPLE)
#	SET(EXTRA_INC_DIR "/Users/mac/Work/dep")
#else()
#	SET(EXTRA_INC_DIR "/home/ext")
##    ${EXTRA_INC_DIR}/boost/lib
#endif()




#if (NOT APPLE)
#	set(C_INCLUDE ${EXTRA_INC_DIR}/boost/lib)
#else()
#	set(C_INCLUDE "")
#endif()
#
#INCLUDE_DIRECTORIES( 
#					#/usr/local/include
##					if (NOT APPLE)
##							${EXTRA_INC_DIR}/boost/include
##					endif()
#					${C_INCLUDE}
#					${EXTRA_INC_DIR}/jsoncpp/include
#					${EXTRA_INC_DIR}/protobuf/include
##		${EXTRA_INC_DIR}/openssl/include
##		/usr/local/Cellar/openssl/1.0.2q/include
#		/usr/local/opt/openssl@1.1/include
##		/usr/local/Cellar/openssl/1.0.2q/include
#					#${EXTRA_INC_DIR}/include/mysql
#					${PROJECT_SOURCE_DIR}/clib
#					${PROJECT_SOURCE_DIR}/common
#					${PROJECT_SOURCE_DIR}/common/cmsg
#					${PROJECT_SOURCE_DIR}/common/cclient_msg
#					${PROJECT_SOURCE_DIR}/common/crobot_msg
#					${PROJECT_SOURCE_DIR}/common/cmessage
#					#${PROJECT_SOURCE_DIR}/Robot
#					)
#
#
#
##target_link_libraries(your_project_name OpenSSL::SSL)
#
#				
#
##thread asio regex locale
#
#LINK_DIRECTORIES(
#
##			    /usr/local/lib
##		/usr/local/opt/icu4c/lib
##		/usr/local/Cellar/openssl/1.0.2q/lib
#				${PROJECT_SOURCE_DIR}/linux/lib
##		/usr/local/Cellar/openssl/1.0.2q/lib
#		/usr/local/opt/openssl@1.1/lib
#				${EXTRA_INC_DIR}/jsoncpp/lib
#				${EXTRA_INC_DIR}/protobuf/lib
#				)
#
##查找openssl是否安装
##find_package(OpenSSL QUIET)
##if (OPENSSL_FOUND AND ENABLE_OPENSSL)
##	message(STATUS "found library:${OPENSSL_LIBRARIES},ENABLE_OPENSSL defined")
##	include_directories(${OPENSSL_INCLUDE_DIR})
##	add_definitions(-DENABLE_OPENSSL)
##	list(APPEND LINK_LIB_LIST ${OPENSSL_LIBRARIES})
##else()
##	message(WARNING "openssl未找到，rtmp将不支持flash播放器，https/wss/rtsps/rtmps也将失效")
##endif ()
#
#if (APPLE)
##	find_package(OpenSSL REQUIRED)
##	include_directories(${OpenSSL_INCLUDE_DIRS})
#	find_package(Boost 1.60.0 COMPONENTS   system filesystem    REQUIRED)
#	include_directories(${Boost_INCLUDE_DIRS})
#	SET(EXECUTABLE_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/bin)
#else()
#	SET(EXECUTABLE_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/linux)
#endif()
#
#SET(LIBRARY_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/linux/lib )
#add_subdirectory(clib)
#add_subdirectory(common)
#add_subdirectory(Robot)
#add_subdirectory(gateway)




