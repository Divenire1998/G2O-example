add_executable(gicp_demo
  gicp_demo.cpp
)

add_executable(gicp_sba_demo
  gicp_sba_demo.cpp
)

set_target_properties(gicp_sba_demo PROPERTIES OUTPUT_NAME gicp_sba_demo${EXE_POSTFIX})

target_link_libraries(gicp_demo g2o_core g2o_types_sba g2o_types_slam3d g2o_types_icp ${OPENGL_LIBRARIES} g2o_solver_eigen g2o_stuff)
target_link_libraries(gicp_sba_demo g2o_core g2o_types_sba g2o_types_slam3d g2o_types_icp ${OPENGL_LIBRARIES} g2o_solver_eigen g2o_stuff)
