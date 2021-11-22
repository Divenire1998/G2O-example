add_library(g2o_interactive_library SHARED
  g2o_slam_interface.cpp g2o_slam_interface.h
  graph_optimizer_sparse_online.cpp graph_optimizer_sparse_online.h
  types_online.cpp
)

include_directories(${CMAKE_CURRENT_SOURCE_DIR}/../)

set_target_properties(g2o_interactive_library PROPERTIES OUTPUT_NAME ${LIB_PREFIX}interactive)
target_link_libraries(g2o_interactive_library g2o_core g2o_types_slam2d g2o_types_slam3d g2o_solver_cholmod g2o_stuff parser_library interface_library )

add_executable(g2o_online_application g2o_online.cpp)
target_link_libraries(g2o_online_application g2o_interactive_library)
set_target_properties(g2o_online_application PROPERTIES OUTPUT_NAME g2o_online${EXE_POSTFIX})

#add_executable(generate_commands_application generate_commands.cpp)
#target_link_libraries(generate_commands_application g2o_interactive_library)
#set_target_properties(generate_commands_application PROPERTIES OUTPUT_NAME generate_commands)

install(TARGETS g2o_interactive_library g2o_online_application
  RUNTIME DESTINATION ${RUNTIME_DESTINATION}
  LIBRARY DESTINATION ${LIBRARY_DESTINATION}
  ARCHIVE DESTINATION ${ARCHIVE_DESTINATION}
)

file(GLOB headers "${CMAKE_CURRENT_SOURCE_DIR}/*.h" "${CMAKE_CURRENT_SOURCE_DIR}/*.hpp")
install(FILES ${headers} DESTINATION ${INCLUDES_INSTALL_DIR}/examples/interactive_slam/g2o_interactive)
