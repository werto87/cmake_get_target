target_sources(${TARGET_NAME_LIB}
   INTERFACE
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/calc.hxx>
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/calc.cxx>
        $<INSTALL_INTERFACE:/calc.hxx>
        $<INSTALL_INTERFACE:/calc.cxx>
        
      #   PUBLIC
      # calc.cxx
      )