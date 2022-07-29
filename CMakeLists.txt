cmake_minimum_required(VERSION 3.16)
project(GPC LANGUAGES C)
add_library(GPC gpc.c gpc.h)
add_library(${PROJECT_NAME}::GPC ALIAS GPC)

# Installation:
install(TARGETS GPC EXPORT ${PROJECT_NAME}Targets INCLUDES DESTINATION include)
install(FILES gpc.h TYPE INCLUDE)
install(EXPORT ${PROJECT_NAME}Targets DESTINATION
  lib/cmake/${PROJECT_NAME} NAMESPACE ${PROJECT_NAME}:: FILE
  ${PROJECT_NAME}Config.cmake)

export(EXPORT ${PROJECT_NAME}Targets NAMESPACE ${PROJECT_NAME}:: FILE
  ${PROJECT_NAME}Config.cmake)
