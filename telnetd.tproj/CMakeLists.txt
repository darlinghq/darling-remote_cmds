project(telnetd)

include_directories(${CMAKE_SOURCE_DIR}/src/external)

add_definitions(-DUSE_TERMIO -DTERMCAP)

set(telnetd_sources
	authenc.c
	global.c
	slc.c
	state.c
	strlcpy.c
	sys_term.c
	telnetd.c
	termstat.c
	utility.c
	vasprintf.c
)

add_darling_executable(telnetd ${telnetd_sources})
target_link_libraries(telnetd telnet ncurses)

install(TARGETS telnetd DESTINATION libexec/darling/usr/sbin)
install(FILES telnet.8 DESTINATION libexec/darling/usr/share/man/man8)

