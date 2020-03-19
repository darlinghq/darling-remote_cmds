project(remote_cmds)

add_definitions(-w -nostdinc)

add_subdirectory(logger.tproj)
add_subdirectory(domainname.tproj)
add_subdirectory(telnet.tproj)
add_subdirectory(telnetd.tproj)

