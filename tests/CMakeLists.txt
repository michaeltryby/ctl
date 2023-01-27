


# Setting up tests to run from build tree
set(TEST_BIN_DIRECTORY "${CMAKE_BINARY_DIR}/tests")



set(
    TEST_SRCS
        func/test_std_headers.c
        func/test_c11.c
        func/test_container_composing.cc
        func/test_deq.cc
        func/test_lst.cc
        func/test_str.cc
        func/test_pqu.cc
        func/test_que.cc
        func/test_set.cc
        func/test_ust.cc
        func/test_stk.cc
        func/test_vec_capacity.cc
        func/test_vec.cc
)


foreach(TestSrc ${TEST_SRCS})
    get_filename_component(
        TestName ${TestSrc} NAME_WE
    )

    add_executable(
      ${TestName}
        ${TestSrc}
    )

    target_compile_features(
      ${TestName}
        PRIVATE
            cxx_std_11
    )

    target_link_libraries(
      ${TestName}
        ctl
    )

    add_test(
        NAME
            ${TestName}
        COMMAND
            "${TEST_BIN_DIRECTORY}/${TestName}"
    )
endforeach()
