project(logger)

add_darling_executable(logger logger.c)

target_compile_definitions(logger PRIVATE
	__FBSDID=__RCSID
)

target_compile_options(logger PRIVATE
	-mdynamic-no-pic
)

target_link_options(logger PRIVATE
	-Wl,-dead_strip
)

install(TARGETS logger DESTINATION libexec/darling/usr/bin)
install(FILES logger.1 DESTINATION libexec/darling/usr/share/man/man1)
