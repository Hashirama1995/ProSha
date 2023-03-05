#   Input variables:
#       NASM_VERSION_MAJOR
#       NASM_VERSION_MINOR
#       NASM_VERSION_PATCH
#       NASM_INSTALL_DIR

cmake_minimum_required (VERSION 3.0)

project(NasmDownload)

include(ExternalProject)

# NASM_URL https://www.nasm.us/pub/nasm/releasebuilds/${NASM_VERSION_MAJOR}.${NASM_VERSION_MINOR}.${NASM_VERSION_PATCH}/win64/nasm-${NASM_VERSION_MAJOR}.${NASM_VERSION_MINOR}.${NASM_VERSION_PATCH}-win64.zip
set(NASM_URL "https://www.nasm.us/pub/nasm/releasebuilds/${NASM_VERSION_MAJOR}.${NASM_VERSION_MINOR}.${NASM_VERSION_PATCH}/win64/nasm-${NASM_VERSION_MAJOR}.${NASM_VERSION_MINOR}.${NASM_VERSION_PATCH}-win64.zip")


set(NASM_INSTALL_COMMAND ${CMAKE_COMMAND} -E copy_directory . ${NASM_INSTALL_DIR})

ExternalProject_Add(
    Nasm
    URL ${NASM_URL}
    CONFIGURE_COMMAND ""
    BUILD_COMMAND ""
    BUILD_IN_SOURCE 1
    INSTALL_COMMAND ${NASM_INSTALL_COMMAND}
)
