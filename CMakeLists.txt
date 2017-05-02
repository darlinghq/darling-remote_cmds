project(remote_cmds)

set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -nostdinc")

add_subdirectory(domainname.tproj)
add_subdirectory(telnet.tproj)
add_subdirectory(telnetd.tproj)

