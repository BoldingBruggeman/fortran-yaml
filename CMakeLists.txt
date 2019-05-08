cmake_minimum_required(VERSION 2.8.8)

if(POLICY CMP0048)
  cmake_policy(SET CMP0048 NEW)
endif()

# Create main project.
project(yaml Fortran)

add_library(yaml
            yaml_types.F90
            yaml.F90
           )

add_executable(test_yaml EXCLUDE_FROM_ALL
               test_yaml.F90
              )
target_link_libraries(test_yaml PRIVATE yaml)
