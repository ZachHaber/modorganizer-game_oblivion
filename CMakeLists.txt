CMAKE_MINIMUM_REQUIRED(VERSION 2.8)

SET(PROJ_NAME game_oblivion)

PROJECT(${PROJ_NAME})

SET(DEPENDENCIES_DIR CACHE PATH "")

# hint to find qt in dependencies path
LIST(APPEND CMAKE_PREFIX_PATH ${DEPENDENCIES_DIR}/qt5/lib/cmake)
LIST(APPEND CMAKE_PREFIX_PATH ${DEPENDENCIES_DIR}/lz4/dll)

FILE(GLOB_RECURSE BOOST_ROOT ${DEPENDENCIES_DIR}/boost*/project-config.jam)
GET_FILENAME_COMPONENT(BOOST_ROOT ${BOOST_ROOT} DIRECTORY)

ADD_SUBDIRECTORY(src)
