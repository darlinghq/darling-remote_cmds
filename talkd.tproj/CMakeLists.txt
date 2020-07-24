project(talkd)

add_darling_executable(ntalkd
	announce.c
	print.c
	process.c
	table.c
	talkd.c
	../wall.tproj/ttymsg.c
)

target_compile_definitions(ntalkd PRIVATE
	__FBSDID=__RCSID
)

target_compile_options(ntalkd PRIVATE
	-fPIE
)

target_link_options(ntalkd PRIVATE
	-Wl,-dead_strip
	-Wl,-pie
)

install(TARGETS ntalkd DESTINATION libexec/darling/usr/libexec)
install(FILES ntalkd.8 DESTINATION libexec/darling/usr/share/man/man8)
install(FILES ntalk.plist DESTINATION libexec/darling/System/Library/LaunchDaemons)
