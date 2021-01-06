cmake_minimum_required(VERSION 2.8.9)
project(LSOBIA)

list(APPEND CMAKE_MODULE_PATH ${LSOBIA_SOURCE_DIR})

set(LSOBIA_LIBRARIES LSOBIA)

## Activate C++14
## by setting the cmake parameter "CMAKE_CXX_FLAGS" to "-std=c++14"
# add compile option()
add_compile_options(-std=c++14)

## cmake --help-policy CMP0072
cmake_policy(SET CMP0072 NEW)
# From:https://github.com/PointCloudLibrary/pcl/issues/3065

if(NOT OTB_SOURCE_DIR)
    find_package(OTB REQUIRED)
    include(OTBModuleExternal)
else()
    otb_module_impl()
endif()
