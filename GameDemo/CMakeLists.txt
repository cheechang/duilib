#Cmake file for GameDemo
#Author: Qi Gao(monkgau@gmail.com)
#Created: 2012/9/17

set(source_files GameDemo.cpp MiniDumper.cpp stdAfx.cpp)
include_directories(${CMAKE_CURRENT_SOURCE_DIR})

set(EXECUTABLE_OUTPUT_PATH ${PROJECT_BINARY_DIR}/bin)
add_executable(GameDemo ${source_files})
add_dependencies(GameDemo duilib)
target_link_libraries(GameDemo duilib)
set_target_properties(GameDemo PROPERTIES LINK_FLAGS "/SUBSYSTEM:WINDOWS")

install(
  TARGETS GameDemo
  RUNTIME DESTINATION bin
  LIBRARY DESTINATION lib
  ARCHIVE DESTINATION lib
)
