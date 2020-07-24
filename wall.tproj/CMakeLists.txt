project(wall)

add_darling_executable(wall
	ttymsg.c
	wall.c
)

target_compile_definitions(wall PRIVATE
	__FBSDID=__RCSID
)

target_compile_options(wall PRIVATE
	-mdynamic-no-pic
)

target_link_options(wall PRIVATE
	-Wl,-dead_strip
)

install(TARGETS wall DESTINATION libexec/darling/usr/bin)
install(FILES wall.1 DESTINATION libexec/darling/usr/share/man/man1)
