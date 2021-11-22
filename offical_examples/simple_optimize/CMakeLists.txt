add_executable(simple_optimize
  simple_optimize.cpp
)

set_target_properties(simple_optimize PROPERTIES OUTPUT_NAME simple_optimize${EXE_POSTFIX})

target_link_libraries(simple_optimize g2o_core g2o_solver_eigen g2o_types_slam2d g2o_types_slam3d g2o_stuff)
