target_sources(${TARGET_NAME_LIB}
   INTERFACE
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include/myLib/lobby.hxx>
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include/myLib/lobby.cxx>
        $<INSTALL_INTERFACE:include/myLib/lobby.hxx>
        $<INSTALL_INTERFACE:include/myLib/lobby.cxx>
      )