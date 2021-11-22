add_executable(create_sphere
  create_sphere.cpp
)

set_target_properties(create_sphere PROPERTIES OUTPUT_NAME create_sphere${EXE_POSTFIX})
target_link_libraries(create_sphere g2o_core g2o_types_slam3d g2o_stuff)
