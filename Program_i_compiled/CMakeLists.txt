cmake_minimum_required(VERSION 2.6)
project(MyProject)

find_package(OpenThreads)
find_package(osg)
find_package(osgDB)
find_package(osgUtil)
find_package(osgViewer)

macro( config_project PROJNAME LIBNAME)
	include_directories( ${${LIBNAME}_INCLUDE_DIR} )
	target_link_libraries( ${PROJNAME} ${${LIBNAME}_LIBRARY})
endmacro()

add_executable( MyProject main.cpp)
config_project(MyProject OPENTHREADS)
config_project(MyProject OSG)
config_project(MyProject OSGDB)
config_project(MyProject OSGUTIL)
config_project(MyProject OSGVIEWER)
