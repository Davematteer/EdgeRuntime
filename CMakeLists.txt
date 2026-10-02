cmake_minimum_required(VERSION 3.20)
project(edgeruntime CXX)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

set(V8_ROOT "" CACHE PATH "Path to the V8 checkout (the v8/v8 directory)")
if(NOT V8_ROOT)
  message(FATAL_ERROR "V8_ROOT is not set. Configure with -DV8_ROOT=/path/to/v8/v8")
endif()

set(V8_OUT_DIR "${V8_ROOT}/out.gn/x64.release.sample")

add_executable(edgeruntime src/main.cpp)

target_include_directories(edgeruntime PRIVATE "${V8_ROOT}/include")

target_compile_definitions(edgeruntime PRIVATE
  V8_COMPRESS_POINTERS
  V8_COMPRESS_POINTERS_IN_SHARED_CAGE
  V8_31BIT_SMIS_ON_64BIT_ARCH
  V8_ENABLE_SANDBOX
)

target_link_libraries(edgeruntime PRIVATE
  "${V8_OUT_DIR}/obj/libv8_monolith.a"
  pthread
  dl
  rt
)
