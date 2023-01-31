


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

if(CMAKE_INSTALL_PREFIX_INITIALIZED_TO_DEFAULT)
    set(CMAKE_INSTALL_PREFIX
            ${CMAKE_BINARY_DIR}/install
        CACHE PATH "..." FORCE)
endif()

 include(GNUInstallDirs)
 include(CMakePackageConfigHelpers)


add_subdirectory(
    ctl
)

add_subdirectory(
    examples
)

enable_testing()
add_subdirectory(
    tests
)


set(versionFile
    ctlConfigVersion.cmake
)
write_basic_package_version_file(
  ${versionFile}
     VERSION
        ${CMAKE_PROJECT_VERSION}
     COMPATIBILITY
        AnyNewerVersion
     ARCH_INDEPENDENT
 )

 install(
     FILES
        ${PROJECT_BINARY_DIR}/${versionFile}
     DESTINATION
        ${CMAKE_INSTALL_PREFIX}
 )
