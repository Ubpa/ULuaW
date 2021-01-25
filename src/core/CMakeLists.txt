set(c_options "")
if(MSVC)
  list(APPEND c_options "/wd4309")
elseif("${CMAKE_CXX_COMPILER_ID}" STREQUAL "Clang")
  #
elseif("${CMAKE_CXX_COMPILER_ID}" STREQUAL "GNU")
  #
endif()

Ubpa_AddTarget(
  MODE STATIC
  SOURCE
    "${PROJECT_SOURCE_DIR}/include/ULuaW"
  INC
    "${PROJECT_SOURCE_DIR}/include"
  LIB
    Ubpa::ULua_core
  C_OPTION_PRIVATE
    ${c_options}
)
