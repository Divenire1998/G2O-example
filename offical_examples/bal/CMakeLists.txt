add_executable(bal_example bal_example.cpp)



target_link_libraries(bal_example g2o_core g2o_solver_cholmod g2o_types_sba g2o_stuff cholmod)


# if(CHOLMOD_FOUND)
#   target_link_libraries(bal_example solver_cholmod)
# else()
#   target_link_libraries(bal_example solver_eigen)
# endif()
