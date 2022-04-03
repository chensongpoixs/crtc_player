cmake_minimum_required(VERSION 3.5)

project(YUV420Player LANGUAGES CXX)

set(CMAKE_INCLUDE_CURRENT_DIR ON)
SET(CMAKE_VERBOSE_MAKEFILE ON)
set(CMAKE_AUTOUIC ON)
set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# QtCreator supports the following variables for Android, which are identical to qmake Android variables.
# Check http://doc.qt.io/qt-5/deployment-android.html for more information.
# They need to be set before the find_package(Qt5 ...) call.




#if(ANDROID)
#    set(ANDROID_PACKAGE_SOURCE_DIR "${CMAKE_CURRENT_SOURCE_DIR}/android")
#    if (ANDROID_ABI STREQUAL "armeabi-v7a")
#        set(ANDROID_EXTRA_LIBS
#            ${CMAKE_CURRENT_SOURCE_DIR}/path/to/libcrypto.so
#            ${CMAKE_CURRENT_SOURCE_DIR}/path/to/libssl.so)
#    endif()
#endif()
# Qt 的库
find_package(Qt5 COMPONENTS Widgets REQUIRED)
find_package(Qt5 COMPONENTS Core REQUIRED)
find_package(Qt5 COMPONENTS Gui REQUIRED)
find_package(Qt5 COMPONENTS Multimedia REQUIRED)
find_package(Qt5 COMPONENTS OpenGL REQUIRED)
# core gui multimedia opengl
#SET(EXECUTABLE_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/bin)
#SET(LIBRARY_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/lib )
#set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY_DEBUG ${PROJECT_SOURCE_DIR}/out)
#set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY_RELEASE ${PROJECT_SOURCE_DIR}/out)



file(GLOB ALL_C_SRCS
         PlayerMainForm.cpp 
    main.cpp 
    QVideoRenderWidget.cpp
    QtConfigParameterDig.cpp
    Slider.cpp
	PlayerMainForm.h 
    QVideoRenderWidget.h
    QtConfigParameterDig.h
    Slider.h
	PlayerMainForm.ui
    QtConfigParameterDig.ui
    YuvPlayerGlobal.h
        )


if(ANDROID)
  add_library(${PROJECT_NAME} SHARED  ${ALL_C_SRCS}  )
else()
  add_executable(${PROJECT_NAME} ${ALL_C_SRCS} )
endif()



set(ALL_LIB  	Qt5::Widgets
                Qt5::Core
                Qt5::Gui
                Qt5::Multimedia
                Qt5::OpenGL
                )

target_link_libraries(${PROJECT_NAME} PRIVATE ${ALL_LIB})
