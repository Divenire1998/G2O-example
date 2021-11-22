add_executable(circle_fit circle_fit.cpp)
set_target_properties(circle_fit PROPERTIES OUTPUT_NAME circle_fit${EXE_POSTFIX})
target_link_libraries(circle_fit g2o_core g2o_solver_eigen g2o_stuff)

add_executable(curve_fit curve_fit.cpp)
set_target_properties(curve_fit PROPERTIES OUTPUT_NAME curve_fit${EXE_POSTFIX})
target_link_libraries(curve_fit g2o_core g2o_solver_dense g2o_stuff)
