include_directories(${TCL_INCLUDE_PATH})

set(CMAKE_SWIG_FLAGS "")
set(CMAKE_SWIG_OUTDIR ${CMAKE_CURRENT_BINARY_DIR})

set(_target ctp-tcl)
set(WRAPPER_FILES ../ctp.i)
set_source_files_properties(${WRAPPER_FILES} PROPERTIES CPLUSPLUS ON)

swig_add_module(${_target} tcl ${WRAPPER_FILES})
swig_link_libraries(${_target} ${TCL_LIBRARIES} ${CTP_LIBRARIES})
