
include_directories(${SDL_INCLUDE_DIR})
include_directories(${OPENGL_INCLUDE_DIR})
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/..)
include_directories(${CMAKE_CURRENT_BINARY_DIR}/..)
add_executable(darktable-viewer main.c)

set_target_properties(darktable-viewer PROPERTIES CMAKE_BUILD_WITH_INSTALL_RPATH TRUE)
set_target_properties(darktable-viewer PROPERTIES CMAKE_INSTALL_RPATH_USE_LINK_PATH FALSE)
set_target_properties(darktable-viewer PROPERTIES INSTALL_RPATH $ORIGIN/../${LIB_INSTALL}/darktable)
set_target_properties(darktable-viewer PROPERTIES LINKER_LANGUAGE C)
target_link_libraries(darktable-viewer lib_darktable ${SDL_LIBRARY} ${OPENGL_LIBRARIES})
install(TARGETS darktable-viewer DESTINATION bin)
