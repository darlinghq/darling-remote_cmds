project(tftpd)

add_darling_executable(tftpd
	tftpd.c
	../tftp.tproj/tftpsubs.c
)

target_compile_definitions(telnetd PRIVATE
	__FBSDID=__RCSID
)

target_compile_options(tftpd PRIVATE
	-fPIE
)

target_link_options(tftpd PRIVATE
	-Wl,-dead_strip
	-Wl,-pie
)

install(TARGETS tftpd DESTINATION libexec/darling/usr/libexec)
install(FILES tftpd.8 DESTINATION libexec/darling/usr/share/man/man8)
install(FILES tftp.plist DESTINATION libexec/darling/System/Library/LaunchDaemons)
