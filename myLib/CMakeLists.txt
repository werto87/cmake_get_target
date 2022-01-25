cmake_minimum_required(VERSION 3.22)

project(mylib VERSION 0.1 LANGUAGES CXX)

set(TARGET_NAME_LIB myLib)
add_library(${TARGET_NAME_LIB} INTERFACE)
target_include_directories(${TARGET_NAME_LIB} INTERFACE 
$<BUILD_INTERFACE:${PROJECT_SOURCE_DIR}/mylib>
$<INSTALL_INTERFACE:mylib>
)
add_subdirectory(myLib)

include(CMakePackageConfigHelpers)
write_basic_package_version_file(
    "${PROJECT_BINARY_DIR}/mylibConfigVersion.cmake"
    VERSION 0.1
    COMPATIBILITY AnyNewerVersion
)

install(TARGETS ${TARGET_NAME_LIB}
    EXPORT mylibTargets
    LIBRARY DESTINATION lib COMPONENT Runtime
    ARCHIVE DESTINATION lib COMPONENT Development
    RUNTIME DESTINATION bin COMPONENT Runtime
    PUBLIC_HEADER DESTINATION include COMPONENT Development
    BUNDLE DESTINATION bin COMPONENT Runtime
)

include(CMakePackageConfigHelpers)
configure_package_config_file(
    "${PROJECT_SOURCE_DIR}/cmake/mylibConfig.cmake.in"
    "${PROJECT_BINARY_DIR}/mylibConfig.cmake"
    INSTALL_DESTINATION lib/cmake/mylib
)

install(EXPORT mylibTargets DESTINATION lib/cmake/mylib)
install(FILES "${PROJECT_BINARY_DIR}/mylibConfigVersion.cmake"
              "${PROJECT_BINARY_DIR}/mylibConfig.cmake"
        DESTINATION lib/cmake/mylib)
install(DIRECTORY ${PROJECT_SOURCE_DIR}/myLib/ DESTINATION include)
