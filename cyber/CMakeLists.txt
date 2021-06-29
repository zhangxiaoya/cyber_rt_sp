cmake_minimum_required(VERSION 3.5)
project(CyberCore)

add_library(cyber_core cyber.cc)

add_library(cyber_init init.cc)
target_link_libraries(cyber_init
    ${Glog_LIBRARY}
    Cyber::service_manager
    Cyber::async_logger
    Cyber::task_manager
    Cyber::timing_wheel
    Cyber::state
    Cyber::global_data
    Cyber::sysmo
    Cyber::topology_manager)

add_library(cyber_binary binary.cc)
add_library(cyber_state state.cc)
# add_library(cyber_binary INTERFACE)

add_library(Cyber::binary ALIAS cyber_binary)
add_library(Cyber::core ALIAS cyber_core)
add_library(Cyber::init ALIAS cyber_init)
add_library(Cyber::state ALIAS cyber_state)

file(GLOB HEADERS *.h)

install(FILES ${HEADERS}
    DESTINATION ${CYBER_INSTALL_INCLUDE_DIR}/cyber/
    )

install(TARGETS
    cyber_core cyber_init cyber_state
    DESTINATION  ${CYBER_INSTALL_LIB_DIR}
    )

install(DIRECTORY
    conf
    DESTINATION  ${CYBER_INSTALL_DIR}
    )

install(FILES
    setup.bash
    DESTINATION  ${CYBER_INSTALL_DIR}
    )


    # set(TARGET_NAME cyber)
    # file(GLOB H_FILES *.h)
    # file(GLOB HPP_FILES *.hpp)
    # set(${TARGET_NAME}_hdrs ${H_FILES} ${HPP_FILES})
    # file(GLOB ${TARGET_NAME}_srcs *.cc)
    
    # add_subdirectory(base)
    # add_subdirectory(blocker)
    # add_subdirectory(class_loader)
    # add_subdirectory(common)
    # add_subdirectory(component)
    # add_subdirectory(conf)
    # add_subdirectory(croutine)
    # add_subdirectory(data)
    # add_subdirectory(event)
    # add_subdirectory(examples)
    # # add_subdirectory(io)
    # add_subdirectory(logger)
    # add_subdirectory(mainboard)
    # add_subdirectory(message)
    # add_subdirectory(node)
    # add_subdirectory(parameter)
    # add_subdirectory(proto)
    # add_subdirectory(record)
    # add_subdirectory(scheduler)
    # add_subdirectory(service)
    # add_subdirectory(service_discovery)
    # add_subdirectory(task)
    # add_subdirectory(time)
    # add_subdirectory(timer)
    # add_subdirectory(tools)
    # add_subdirectory(transport)
    # add_subdirectory(monitor)
    # add_subdirectory(sysmo)
    # add_subdirectory(noartd)
    
    # add_library(${TARGET_NAME} SHARED ${${TARGET_NAME}_srcs}
    #   $<TARGET_OBJECTS:cyber_blocker>
    #   $<TARGET_OBJECTS:cyber_class_loader>
    #   $<TARGET_OBJECTS:cyber_common>
    #   $<TARGET_OBJECTS:cyber_component>
    #   $<TARGET_OBJECTS:cyber_croutine>
    #   $<TARGET_OBJECTS:cyber_event>
    #   # $<TARGET_OBJECTS:cyber_io>
    #   $<TARGET_OBJECTS:cyber_logger>
    #   $<TARGET_OBJECTS:cyber_message>
    #   $<TARGET_OBJECTS:cyber_node>
    #   $<TARGET_OBJECTS:cyber_parameter>
    #   $<TARGET_OBJECTS:cyber_proto>
    #   $<TARGET_OBJECTS:cyber_record>
    #   $<TARGET_OBJECTS:cyber_scheduler>
    #   $<TARGET_OBJECTS:cyber_service_discovery>
    #   $<TARGET_OBJECTS:cyber_task>
    #   $<TARGET_OBJECTS:cyber_time>
    #   $<TARGET_OBJECTS:cyber_timer>
    #   $<TARGET_OBJECTS:cyber_transport>
    #   $<TARGET_OBJECTS:cyber_inner_monitor>
    #   $<TARGET_OBJECTS:cyber_sysmo>
    #   $<TARGET_OBJECTS:cyber_noartd>
    #   )
    
    # target_link_libraries(${TARGET_NAME}
    #   ${${PROJECT_NAME}_lib}
    #   )
    # set_target_properties(${TARGET_NAME} PROPERTIES VERSION ${PROJECT_VERSION} SOVERSION ${PROJECT_VERSION})
    # install(TARGETS ${TARGET_NAME}
    #   RUNTIME DESTINATION bin
    #   LIBRARY DESTINATION lib
    #   ARCHIVE DESTINATION lib
    # )
      
    # if(NOT XGO_DISABLE_STATICLIBS)
    #  add_library(${TARGET_NAME}-static STATIC ${${TARGET_NAME}_srcs}
    #   $<TARGET_OBJECTS:cyber_blocker>
    #   $<TARGET_OBJECTS:cyber_class_loader>
    #   $<TARGET_OBJECTS:cyber_common>
    #   $<TARGET_OBJECTS:cyber_component>
    #   $<TARGET_OBJECTS:cyber_croutine>
    #   $<TARGET_OBJECTS:cyber_event>
    #   # $<TARGET_OBJECTS:cyber_io>
    #   $<TARGET_OBJECTS:cyber_logger>
    #   $<TARGET_OBJECTS:cyber_message>
    #   $<TARGET_OBJECTS:cyber_node>
    #   $<TARGET_OBJECTS:cyber_parameter>
    #   $<TARGET_OBJECTS:cyber_proto>
    #   $<TARGET_OBJECTS:cyber_record>
    #   $<TARGET_OBJECTS:cyber_scheduler>
    #   $<TARGET_OBJECTS:cyber_service_discovery>
    #   $<TARGET_OBJECTS:cyber_task>
    #   $<TARGET_OBJECTS:cyber_time>
    #   $<TARGET_OBJECTS:cyber_timer>
    #   $<TARGET_OBJECTS:cyber_transport>
    #   $<TARGET_OBJECTS:cyber_inner_monitor>
    #   $<TARGET_OBJECTS:cyber_sysmo>
    #   $<TARGET_OBJECTS:cyber_noartd>
    #   )
    
    #   target_link_libraries(${TARGET_NAME}-static
    #     ${${PROJECT_NAME}_lib}
    #   )
    
    #   set_target_properties(${TARGET_NAME}-static PROPERTIES OUTPUT_NAME ${TARGET_NAME} CLEAN_DIRECT_OUTPUT 1)
    
    #   install(TARGETS ${TARGET_NAME}-static
    #     RUNTIME DESTINATION bin
    #     LIBRARY DESTINATION lib
    #     ARCHIVE DESTINATION lib
    #   )
    # endif()
    
    # add_subdirectory(python)
    # add_subdirectory(py_wrapper)
    # install(FILES ${${TARGET_NAME}_hdrs} DESTINATION include/cyber)
