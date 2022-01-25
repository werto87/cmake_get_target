target_sources(${TARGET_NAME_LIB}
   INTERFACE
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include/myLib/calc.hxx>
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include/myLib/calc.cxx>
        $<INSTALL_INTERFACE:include/myLib/calc.hxx>
        $<INSTALL_INTERFACE:include/myLib/calc.cxx>
      )