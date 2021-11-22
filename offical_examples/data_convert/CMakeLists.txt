add_executable(convert_sba_slam3d
  convert_sba_slam3d.cpp
)


set_target_properties(convert_sba_slam3d PROPERTIES OUTPUT_NAME convert_sba_slam3d${EXE_POSTFIX})
target_link_libraries(convert_sba_slam3d g2o_core g2o_types_slam3d g2o_types_sba g2o_stuff)
