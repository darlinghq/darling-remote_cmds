project(telnetd)

set(telnetd_sources
	global.c
	slc.c
	state.c
	sys_term.c
	telnetd.c
	termstat.c
	utility.c
)

add_darling_executable(telnetd ${telnetd_sources})
target_link_libraries(telnetd telnet ncurses)

target_compile_definitions(telnetd PRIVATE
	__FBSDID=__RCSID

	NO_UTMP
	LINEMODE
	KLUDGELINEMODE
	USE_TERMIO
	DIAGNOSTICS
	OLD_ENVIRON
	ENV_HACK
	INET6
)

target_compile_options(telnetd PRIVATE
	-fPIE
)

target_link_options(telnetd PRIVATE
	-Wl,-dead_strip
	-Wl,-pie
)

install(TARGETS telnetd DESTINATION libexec/darling/usr/libexec)
install(FILES telnetd.8 DESTINATION libexec/darling/usr/share/man/man8)
#install(FILES telnet-darling.plist DESTINATION libexec/darling/System/Library/LaunchDaemons)

