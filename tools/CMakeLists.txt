# The tools are not shared libraries
add_definitions(-DCPL_DISABLE_DLL)

set(TOOL_TARGETS commander ctb  ${CMAKE_THREAD_LIBS_INIT})

# Add the `ctb-tile` executable
add_executable(spc-tile ctb-tile.cpp)
target_link_libraries(spc-tile ${TOOL_TARGETS})

# Add the `ctb-export` executable
add_executable(spc-export ctb-export.cpp)
target_link_libraries(spc-export ${TOOL_TARGETS})

# Add the `ctb-info` executable
add_executable(spc-info ctb-info.cpp)
target_link_libraries(spc-info ${TOOL_TARGETS})

# Add the `ctb-extents` executable
add_executable(spc-extents ctb-extents.cpp)
target_link_libraries(spc-extents ${TOOL_TARGETS})

# Install the tools
set(TOOLS spc-tile spc-export spc-info spc-extents)
install(TARGETS ${TOOLS} DESTINATION bin)
