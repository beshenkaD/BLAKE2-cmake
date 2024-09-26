set(LIB_TYPE power8)
set(LIB_NAME "BLAKE2_${LIB_TYPE}_LIB")

file(GLOB HEADER_LIST CONFIGURE_DEPENDS "${BLAKE2_SOURCE_DIR}/${LIB_TYPE}/*.h")

add_library(
  ${LIB_NAME} STATIC
  blake2b.c
  blake2bp.c
  blake2s.c
  blake2sp.c
  blake2xb.c
  blake2xs.c
  ${HEADER_LIST})

target_include_directories(${LIB_NAME} PUBLIC "${BLAKE2_SOURCE_DIR}/${LIB_TYPE}")

set_target_properties(${LIB_NAME} PROPERTIES C_STANDARD 90)

source_group(
    TREE "${PROJECT_SOURCE_DIR}/${LIB_TYPE}"
    PREFIX "Header Files"
    FILES ${HEADER_LIST}
)
