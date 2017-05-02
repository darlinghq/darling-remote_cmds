project(telnet)

include_directories(${CMAKE_SOURCE_DIR}/src/external)

add_definitions(-DUSE_TERMIO -DTERMCAP)

set(telnet_sources
	authenc.c
	commands.c
	main.c
	network.c
	ring.c
	sys_bsd.c
	telnet.c
	terminal.c
	tn3270.c
	utilities.c
)

add_darling_executable(telnetexe ${telnet_sources})
target_link_libraries(telnetexe system telnet ncurses)
set_target_properties(telnetexe PROPERTIES OUTPUT_NAME telnet)

install(TARGETS telnetexe DESTINATION libexec/darling/usr/bin)
install(FILES telnet.1 DESTINATION libexec/darling/usr/share/man/man1)

