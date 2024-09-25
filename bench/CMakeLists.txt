find_package(OpenSSL REQUIRED)

add_executable(bench bench.c md5.c)

set_target_properties(bench PROPERTIES C_STANDARD 90)

target_link_libraries(bench PRIVATE OpenSSL::Crypto)
