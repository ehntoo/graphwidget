find_package(PkgConfig)
pkg_check_modules(GTKMM REQUIRED IMPORTED_TARGET gtkmm-3.0)

set(GRAPHWIDGET_SOURCES
	Graph.cpp
	)

add_library(graphwidget SHARED
	${GRAPHWIDGET_SOURCES})
target_link_libraries(graphwidget PkgConfig::GTKMM)

target_include_directories(graphwidget
PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})

install(TARGETS graphwidget LIBRARY)
