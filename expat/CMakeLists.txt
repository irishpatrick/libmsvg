cmake_minimum_required(VERSION 3.2)

project(expat)

set(expat_sources
    ${CMAKE_CURRENT_SOURCE_DIR}/xmltok/xmltok.c
    ${CMAKE_CURRENT_SOURCE_DIR}/xmltok/xmlrole.c
    ${CMAKE_CURRENT_SOURCE_DIR}/xmlparse/xmlparse.c
)

add_library(${PROJECT_NAME} STATIC ${expat_sources})
target_include_directories(${PROJECT_NAME} PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/xmltok)

