


file(GLOB
    CTL_HEADERS
        RELATIVE ${CMAKE_CURRENT_SOURCE_DIR} *.h
)

add_library(
  ctl
    INTERFACE
)

target_include_directories(
  ctl
    INTERFACE
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}>
)

install(
    TARGETS
        ctl
    EXPORT
        ctlTargets
    INCLUDES
        DESTINATION
            ${CMAKE_INSTALL_FULL_INCLUDEDIR}
)

install(
    EXPORT
        ctlTargets
    FILE
        ctlConfig.cmake
    DESTINATION
        ${CMAKE_INSTALL_PREFIX}
)

install(
    FILES
        ${CTL_HEADERS}
    DESTINATION
        ${CMAKE_INSTALL_FULL_INCLUDEDIR}
 )
