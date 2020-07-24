project(remote_cmds)

add_definitions(-w -nostdinc)

add_subdirectory(logger.tproj)
add_subdirectory(talk.tproj)
add_subdirectory(talkd.tproj)
add_subdirectory(telnet.tproj)
add_subdirectory(telnetd.tproj)
add_subdirectory(tftp.tproj)
add_subdirectory(tftpd.tproj)
add_subdirectory(wall.tproj)
