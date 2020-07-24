project(telnet)

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
set_target_properties(telnetexe PROPERTIES OUTPUT_NAME telnet)

target_link_libraries(telnetexe
	ncurses
	#krb4
	#krb5
	Kerberos # instead of krb4 and krb5
	#ipsec
	telnet
)

target_compile_definitions(telnetexe PRIVATE
	__FBSDID=__RCSID

	TERMCAP
	KLUDGELINEMODE
	USE_TERMIO
	ENV_HACK
	AUTHENTICATION
	KRB5
	SKEY
	#IPSEC
	INET6
	FORWARD 
)

target_compile_options(telnetexe PRIVATE
	-fPIE
)

target_link_options(telnetexe PRIVATE
	-Wl,-dead_strip
	-Wl,-pie
)

install(TARGETS telnetexe DESTINATION libexec/darling/usr/bin)
install(FILES telnet.1 DESTINATION libexec/darling/usr/share/man/man1)

