cmake_minimum_required(VERSION 3.0)

project(rs232 VERSION 0.21)

if(WIN32)
  add_library(rs232 SHARED rs232-win.c)
else()
  add_library(rs232 SHARED rs232-linux.c)
endif(WIN32)

install(TARGETS rs232
  RUNTIME DESTINATION lib
  ARCHIVE DESTINATION lib # for .lib files on Windows
  LIBRARY DESTINATION lib)

install(FILES rs232.h DESTINATION include)
