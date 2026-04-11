if (NOT ENABLE_SPICE)
  return()
endif()

add_executable(spice2xyzv "spice2xyzv.cpp")
target_link_libraries(spice2xyzv CSPICE::CSPICE)

install(
  TARGETS spice2xyzv
  RUNTIME DESTINATION "${CMAKE_INSTALL_BINDIR}"
  COMPONENT tools
)

install(
  FILES naif0012.tls
  DESTINATION "${DATADIR}"
  COMPONENT tools
)
