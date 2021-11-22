
add_executable(g2o_test main.cpp)
# target_link_libraries(g2o_test ${G2O_LIBS})
target_link_libraries(g2o_test cxsparse g2o_stuff g2o_core g2o_solver_cholmod g2o_solver_csparse g2o_csparse_extension g2o_types_slam3d )
