cmake_minimum_required(VERSION 3.10)

# Create main project.
project(yaml VERSION 0.1.0 LANGUAGES Fortran)

if(POLICY CMP0048)
  cmake_policy(SET CMP0048 NEW)
endif()

add_library(yaml
            yaml_types.F90
            yaml.F90
)
set_property(TARGET yaml PROPERTY Fortran_MODULE_DIRECTORY ${CMAKE_CURRENT_BINARY_DIR}/modules)
target_include_directories(yaml
   PUBLIC
      $<INSTALL_INTERFACE:include>
      $<BUILD_INTERFACE:${CMAKE_CURRENT_BINARY_DIR}/modules>
)

add_executable(test_yaml EXCLUDE_FROM_ALL
               test_yaml.F90
              )
target_link_libraries(test_yaml PRIVATE yaml)
