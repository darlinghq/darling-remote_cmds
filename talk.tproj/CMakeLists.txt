project(talk)

add_darling_executable(talk
	ctl_transact.c
	ctl.c
	display.c
	get_addrs.c
	get_iface.c
	get_names.c
	init_disp.c
	invite.c
	io.c
	look_up.c
	msgs.c
	talk.c
)

target_compile_options(talk PRIVATE
	-fPIE
)

target_link_options(talk PRIVATE
	-Wl,-dead_strip
	-Wl,-pie
)

target_link_libraries(talk
	ncurses
)

install(TARGETS talk DESTINATION libexec/darling/usr/bin)
install(FILES talk.1 DESTINATION libexec/darling/usr/share/man/man1)
