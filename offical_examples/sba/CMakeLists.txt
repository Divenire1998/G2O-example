add_executable(sba_demo sba_demo.cpp)
target_link_libraries(sba_demo g2o_core g2o_types_icp g2o_types_sba g2o_stuff cholmod)
set_target_properties(sba_demo PROPERTIES OUTPUT_NAME sba_demo${EXE_POSTFIX})

# Link CHOLMOD if available, CSparse otherwise
if(CHOLMOD_FOUND)
  target_link_libraries(sba_demo g2o_solver_cholmod)
else()
  target_link_libraries(sba_demo g2o_solver_eigen)
endif()
