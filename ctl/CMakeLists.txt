


add_library(
  ctl
    INTERFACE
)

target_include_directories(
  ctl
    INTERFACE
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}>
)
