


cmake_minimum_required (VERSION 3.0)


if("${CMAKE_BINARY_DIR}" STREQUAL "${CMAKE_SOURCE_DIR}")
    message(FATAL_ERROR "In-source builds are disabled.")
endif()


project(
  ctl
    VERSION
        3.0.0
    LANGUAGES
        C
        CXX
)

add_subdirectory(
    ctl
)

enable_testing()
add_subdirectory(
    tests
)
