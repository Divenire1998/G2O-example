add_executable(ba_demo
  ba_demo.cpp
)


target_link_libraries(ba_demo g2o_core g2o_solver_cholmod g2o_types_sba g2o_stuff cholmod)


# target_link_libraries(ba_demo g2o_core g2o_types_sba )

# if(CHOLMOD_FOUND)
#   target_link_libraries(ba_demo g2o_solver_cholmod)
# else()
#   target_link_libraries(ba_demo solver_eigen)
# endif()
