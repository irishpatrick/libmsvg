cmake_minimum_required(VERSION 3.2)

project(msvg)

set(msvg_sources
    ${CMAKE_CURRENT_SOURCE_DIR}/src/attribut.c
    ${CMAKE_CURRENT_SOURCE_DIR}/src/cokdims.c
    ${CMAKE_CURRENT_SOURCE_DIR}/src/content.c
    ${CMAKE_CURRENT_SOURCE_DIR}/src/cook2raw.c
    ${CMAKE_CURRENT_SOURCE_DIR}/src/element.c
    ${CMAKE_CURRENT_SOURCE_DIR}/src/find.c
    ${CMAKE_CURRENT_SOURCE_DIR}/src/gradnorm.c
    ${CMAKE_CURRENT_SOURCE_DIR}/src/manielem.c
    ${CMAKE_CURRENT_SOURCE_DIR}/src/paintctx.c
    ${CMAKE_CURRENT_SOURCE_DIR}/src/path2ply.c
    ${CMAKE_CURRENT_SOURCE_DIR}/src/printree.c
    ${CMAKE_CURRENT_SOURCE_DIR}/src/raw2cook.c
    ${CMAKE_CURRENT_SOURCE_DIR}/src/rdsvgf.c
    ${CMAKE_CURRENT_SOURCE_DIR}/src/scanpath.c
    ${CMAKE_CURRENT_SOURCE_DIR}/src/serializ.c
    ${CMAKE_CURRENT_SOURCE_DIR}/src/tables.c
    ${CMAKE_CURRENT_SOURCE_DIR}/src/tcookel.c
    ${CMAKE_CURRENT_SOURCE_DIR}/src/tmatrix.c
    ${CMAKE_CURRENT_SOURCE_DIR}/src/util.c
    ${CMAKE_CURRENT_SOURCE_DIR}/src/wtsvgf.c
)

add_subdirectory(${CMAKE_CURRENT_SOURCE_DIR}/expat)

add_library(${PROJECT_NAME} STATIC ${msvg_sources})
target_include_directories(${PROJECT_NAME} PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/expat/xmlparse)
target_link_libraries(${PROJECT_NAME} PRIVATE expat)

