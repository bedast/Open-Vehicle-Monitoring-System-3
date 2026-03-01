set(srcs)
set(include_dirs)

if (CONFIG_OVMS_VEHICLE_KIANIROEV2)
  list(APPEND srcs "src/kn2_can_poll.cpp" "src/kn2_can_send.cpp" "src/kn2_commands.cpp" "src/kn2_incoming_c_can.cpp" "src/kn2_web.cpp" "src/vehicle_kianiroev2.cpp")
  list(APPEND include_dirs "src")
endif ()

# requirements can't depend on config
idf_component_register(SRCS ${srcs}
                       INCLUDE_DIRS ${include_dirs}
                       PRIV_REQUIRES "main"
                       WHOLE_ARCHIVE)
