project(tftp)

add_darling_executable(tftp
	main.c
	tftp.c
	tftpsubs.c
)

target_compile_definitions(tftp PRIVATE
	__FBSDID=__RCSID
)

target_compile_options(tftp PRIVATE
	-fPIE
)

target_link_options(tftp PRIVATE
	-Wl,-dead_strip
	-Wl,-pie
)

target_link_libraries(tftp
	edit
)

install(TARGETS tftp DESTINATION libexec/darling/usr/libexec)
install(FILES tftp.1 DESTINATION libexec/darling/usr/share/man/man1)
