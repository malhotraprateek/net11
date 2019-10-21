cmake_minimum_required(VERSION 3.6)

PROJECT (net11)

file(GLOB net11_INCLUDE_HEADERS "${CMAKE_CURRENT_SOURCE_DIR}/net11/*.hpp" "${CMAKE_CURRENT_SOURCE_DIR}/net11/*.h")

add_library(net11 STATIC ${net11_INCLUDE_HEADERS} "net11.cpp")
add_library(net11::net11 ALIAS net11)

# Target property for include directories
target_include_directories(
net11
INTERFACE
"$<BUILD_INTERFACE:${CMAKE_CURRENT_LIST_DIR}/net11>"
"$<INSTALL_INTERFACE:${CMAKE_INSTALL_INCLUDEDIR}/net11>"
)
