cmake_minimum_required(VERSION 3.7)

project(volt_ge_mod)

# Setup Conan
include(${CMAKE_BINARY_DIR}/conanbuildinfo.cmake)
conan_basic_setup()
message(STATUS "Libs: ${CONAN_LIBS}")

# Add in volt_gfx
add_subdirectory(${CMAKE_CURRENT_SOURCE_DIR}/volt_mod/)

# Setup Dyygen
# find_package(Doxygen)
# if (DOXYGEN_FOUND)
#     set(DOXYGEN_IN ${CMAKE_CURRENT_SOURCE_DIR}/Doxyfile.in)
#     set(DOXYGEN_OUT ${CMAKE_CURRENT_BINARY_DIR}/Doxyfile)

#     configure_file(${DOXYGEN_IN} ${DOXYGEN_OUT} @ONLY)
#     message("Doxygen build started")

#     add_custom_target( doc_doxygen_volt_net ALL
#         COMMAND ${DOXYGEN_EXECUTABLE} ${DOXYGEN_OUT}
#         WORKING_DIRECTORY ${CMAKE_CURRENT_BINARY_DIR}
#         COMMENT "Generating API documentation with Doxygen"
#         VERBATIM )
# else (DOXYGEN_FOUND)
#     message("Doxygen need to be installed to generate the doxygen documentation")
# endif ()

enable_testing()

# Add in tests
add_subdirectory(${CMAKE_CURRENT_SOURCE_DIR}/tests/load_formats/)
