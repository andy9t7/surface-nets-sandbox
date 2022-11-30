cmake_minimum_required(VERSION 3.16)

#-------------------------------------------------------------------------------
# Project name and version

project(SurfaceNets VERSION 1.0.0)

#-------------------------------------------------------------------------------
# Compilers

# Require C++ standard and disable compiler-specific extensions
set(CMAKE_CXX_STANDARD 17) 
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

#-------------------------------------------------------------------------------
# Find and Setup Qt5

set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTOUIC ON)
set(CMAKE_AUTORCC ON)

message(STATUS "Finding Qt5...")
find_package(Qt5 REQUIRED COMPONENTS Core Widgets Gui OpenGL)
message(STATUS "Found Qt5: ${Qt5_DIR} (version ${Qt5_VERSION})")

#-------------------------------------------------------------------------------
# Project Library

add_library(SNLib STATIC
	Source/SNLib/MMCellFlag.cpp
	Source/SNLib/MMCellMap.cpp
	Source/SNLib/MMGeometryGL.cpp
	Source/SNLib/MMGeometryOBJ.cpp
	Source/SNLib/MMSurfaceNet.cpp
)	

target_include_directories(SNLib PUBLIC
	Source/SNLib
)

#-------------------------------------------------------------------------------
# Project Executables

add_executable(${PROJECT_NAME}
	Source/Application/main.cpp
	Source/Application/appWindow.cpp
	Source/Application/glView.cpp
	Source/Application/mainWindow.cpp
	Source/Application/materialTable.cpp
	Source/Application/openModelFileDialog.cpp
	Source/Application/setValueGroup.cpp
	Source/Application/newModelDialog.cpp
	
)

target_link_libraries(${PROJECT_NAME} PUBLIC 
	SNLib
	Qt5::Core
	Qt5::Widgets
	Qt5::Gui
	Qt5::OpenGL
)





