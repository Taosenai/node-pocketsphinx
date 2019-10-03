project(node-pocketsphinx)
cmake_minimum_required(VERSION 3.1)
set (CMAKE_CXX_STANDARD 11)

find_package(SWIG 3.0.7 REQUIRED)

set (DEP_DIR "${CMAKE_CURRENT_SOURCE_DIR}/deps" CACHE STRING "Path to folder containg sphinxbase and pocketsphinx source code folders")
set (SB_DATADIR ${DEP_DIR}/sphinxbase/)
set (SB_INCLUDE_DIRS
        ${DEP_DIR}/sphinxbase/include/
        ${DEP_DIR}/sphinxbase/include/win32/
)
set (SB_LIBRARY_DIRS
    ${DEP_DIR}/sphinxbase/bin/Release/x64/
)
set (SB_LIBRARIES
    ${DEP_DIR}/sphinxbase/bin/Release/x64/sphinxbase.lib
)

set (PS_DATADIR ${DEP_DIR}/pocketsphinx/)
set (PS_INCLUDE_DIRS
        ${DEP_DIR}/pocketsphinx/include/
)
set (PS_LIBRARY_DIRS
    ${DEP_DIR}/pocketsphinx/bin/Release/x64/
)
set (PS_LIBRARIES
    ${DEP_DIR}/pocketsphinx/bin/Release/x64/pocketsphinx.lib
    ${DEP_DIR}/sphinxbase/bin/Release/x64/sphinxbase.lib
)

add_subdirectory(sphinxbase)
add_subdirectory(pocketsphinx)
