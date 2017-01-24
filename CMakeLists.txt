cmake_minimum_required(VERSION 3.4)

set(LIB_SOURCES
	client.cpp
	ip_port.cpp
	protocol.cpp
	server.cpp)
set(LIB_HEADERS
	client.hpp
	ip_port.hpp
	protocol.hpp
	server.hpp)

add_library(udp-discovery STATIC ${LIB_SOURCES} ${LIB_HEADERS})

set(DISCOVERY_EXAMPLE_SOURCES
	discovery_example.cpp)
set(DISCOVERY_EXAMPLE_LIBS
	udp-discovery)

add_executable(udp-discovery-example ${DISCOVERY_EXAMPLE_SOURCES})
target_link_libraries(udp-discovery-example ${DISCOVERY_EXAMPLE_LIBS})