if(WIN32)
    message(FATAL_ERROR "Can't build b2sum on windows")
endif()

add_executable(b2sum b2sum.c)

set_target_properties(b2sum PROPERTIES C_STANDARD 90)
