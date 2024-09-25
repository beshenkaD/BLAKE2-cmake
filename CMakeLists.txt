cmake_minimum_required(VERSION 3.20)

project(
  BLAKE2
  VERSION 1.0
  DESCRIPTION "A set of cryptographic hash functions"
  LANGUAGES C)

option(BLAKE2_REF "Build reference library" ON)
option(BLAKE2_SSE "Build SSE version" OFF)
option(BLAKE2_NEON "Build NEON version" OFF)
option(BLAKE2_POWER8 "Build power8 version" OFF)
option(BLAKE2_BENCH "Build bench" OFF)
option(BLAKE2_B2SUM "Build b2sum" OFF)

set(CMAKE_C_EXTENSIONS OFF)
set_property(GLOBAL PROPERTY USE_FOLDERS ON)

if(BLAKE2_REF)
  add_subdirectory(${CMAKE_SOURCE_DIR}/ref)
endif()

if(BLAKE2_SSE)
  add_subdirectory(${CMAKE_SOURCE_DIR}/sse)
endif()

if(BLAKE2_NEON)
  add_subdirectory(${CMAKE_SOURCE_DIR}/neon)
endif()

if(BLAKE2_POWER8)
  add_subdirectory(${CMAKE_SOURCE_DIR}/power8)
endif()

if(BLAKE2_BENCH)
  add_subdirectory(${CMAKE_SOURCE_DIR}/bench)
endif()

if(BLAKE2_B2SUM)
  add_subdirectory(${CMAKE_SOURCE_DIR}/b2sum)
endif()
