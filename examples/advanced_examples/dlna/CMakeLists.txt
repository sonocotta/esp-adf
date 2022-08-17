# The following lines of boilerplate have to be in your project's
# CMakeLists in this exact order for cmake to work correctly
cmake_minimum_required(VERSION 3.5)

set(EXTRA_COMPONENT_DIRS ./components)

if(NOT DEFINED $ENV{ADF_PATH})
    set(ENV{ADF_PATH} $ENV{IDF_PATH}/..)
endif()

message(IDF_PATH = $ENV{IDF_PATH})
message(ADF_PATH = $ENV{ADF_PATH})

include($ENV{ADF_PATH}/CMakeLists.txt)
include($ENV{IDF_PATH}/tools/cmake/project.cmake)

project(dlna_example)

target_add_binary_data(dlna_example.elf "./components/esp_dlna/xml/rootDesc.xml" TEXT)
target_add_binary_data(dlna_example.elf "./components/esp_dlna/xml/rootDescLogo.xml" TEXT)
target_add_binary_data(dlna_example.elf "./components/esp_dlna/xml/rootDescService.xml" TEXT)
target_add_binary_data(dlna_example.elf "./components/esp_dlna/xml/SoapResponseErr.xml" TEXT)
target_add_binary_data(dlna_example.elf "./components/esp_dlna/xml/SoapResponseOk.xml" TEXT)
target_add_binary_data(dlna_example.elf "./components/esp_dlna/xml/devicelist.xml" TEXT)