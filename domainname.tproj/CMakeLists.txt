project(domainname)

add_darling_executable(domainname domainname.c)

install(TARGETS domainname DESTINATION libexec/darling/usr/bin)
install(FILES domainname.1 DESTINATION libexec/darling/usr/share/man/man1)

