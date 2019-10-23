cmake_minimum_required(VERSION 2.8 FATAL_ERROR)

Project (rdfind)

SET(CMAKE_MODULE_PATH "${CMAKE_CURRENT_SOURCE_DIR}/cmake")

find_package(Nettle)

set (CMAKE_CXX_STANDARD 11)

add_executable(rdfind
    Checksum.cc
    CmdlineParser.cc
    Dirlist.cc
    EasyRandom.cc
    Fileinfo.cc
    rdfind.cc
    Rdutil.cc
	UndoableUnlink.cc
)
target_include_directories(rdfind PRIVATE ${NETTLE_INCLUDE_DIR})
target_link_libraries(rdfind PRIVATE ${NETTLE_LIBRARY})