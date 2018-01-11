project(dapcash-node C)
cmake_minimum_required(VERSION 2.8)

set(CMAKE_VERBOSE_MAKEFILE ON)
set(CMAKE_COLOR_MAKEFILE   ON)


#set(CMAKE_LIBRARY_PATH ${CMAKE_LIBRARY_PATH} /opt/local/lib)
#set(CMAKE_INCLUDE_PATH ${CMAKE_INCLUDE_PATH} /opt/local/include)
add_subdirectory(submodules/libdap)
add_subdirectory(submodules/libdap-chain)

include_directories("${INCLUDE_DIRECTORIES} ${dapcore_INCLUDE_DIRS}")
include_directories("${INCLUDE_DIRECTORIES} ${dapcrypt_INCLUDE_DIRS}")
include_directories("${INCLUDE_DIRECTORIES} ${daphttp_INCLUDE_DIRS}")
include_directories("${INCLUDE_DIRECTORIES} ${dapclient_INCLUDE_DIRS}")


#set(CMAKE_C_FLAGS "${CMAKE_CXX_FLAGS} -msse4.1 -maes -march=nehalem -msse2 -msse3 -pedantic")

add_executable(dapcash-node "sources/dapcash-node.c" )
