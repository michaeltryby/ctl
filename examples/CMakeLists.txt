


set(EXAMPLE_SRC
    6502.c
    astar.c
    json.c
    postfix.c
    snow.c
)

foreach(ExampleSrc ${EXAMPLE_SRC})
    get_filename_component(
        ExampleName ${ExampleSrc} NAME_WE
    )

    add_executable(
      ${ExampleName}
        ${ExampleSrc}
    )

    target_link_libraries(
      ${ExampleName}
        ctl
    )
endforeach()
