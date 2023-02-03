cmake_minimum_required(VERSION 3.25)

project(pro-TBB)


find_package(PkgConfig REQUIRED)
pkg_check_modules(TBB REQUIRED tbb)

list(APPEND pro_TBB_LINK_LIBRARIES tbb)


function (tbb_executable executable sources libraries)
  #list(LENGTH "${libraries}" my_length)
  #message("function libraries = ${libraries}, length = ${my_length}")

  add_executable(${executable}
	${sources})
  target_link_libraries(${executable}
	PUBLIC
	${libraries})
endfunction ()

add_subdirectory(ch17)
