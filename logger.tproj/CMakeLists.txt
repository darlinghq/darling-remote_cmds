project(logger)

add_darling_executable(logger logger.c)
install(TARGETS logger DESTINATION libexec/darling/usr/bin)
install(FILES logger.1 DESTINATION libexec/darling/usr/share/man/man1)

