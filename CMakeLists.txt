cmake_minimum_required(VERSION 3.0)

# Create main project.
project(yaml VERSION 0.1.0 LANGUAGES Fortran)

set(GIT_COMMIT_ID ${yaml_VERSION})
set(GIT_BRANCH_NAME unknown)
configure_file(yaml_version.F90.in yaml_version.F90)

add_library(yaml
            ${CMAKE_CURRENT_BINARY_DIR}/yaml_version.F90
            yaml_types.F90
            yaml_settings.F90
            yaml.F90
)
set_property(TARGET yaml PROPERTY Fortran_MODULE_DIRECTORY "${CMAKE_CURRENT_BINARY_DIR}/modules")
target_include_directories(yaml
   PUBLIC
      $<INSTALL_INTERFACE:include>
      $<BUILD_INTERFACE:${CMAKE_CURRENT_BINARY_DIR}/modules>
)

add_executable(test_yaml EXCLUDE_FROM_ALL
               test_yaml.F90
              )
target_link_libraries(test_yaml PRIVATE yaml)

set_property(TARGET yaml test_yaml PROPERTY FOLDER yaml)

install(TARGETS yaml
        EXPORT yamlConfig
        LIBRARY DESTINATION lib
        ARCHIVE DESTINATION lib
)

install(EXPORT yamlConfig DESTINATION cmake)
