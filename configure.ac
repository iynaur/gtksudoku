AC_INIT(GTK Sudoku, 0.7, https://github.com/ramsdell/gtksudoku, gtksudoku)

AC_CONFIG_SRCDIR(src/gtksudoku.c)

AM_INIT_AUTOMAKE

AM_CONFIG_HEADER(src/config.h)

AC_PROG_CC
AM_PROG_CC_C_O
AC_STDC_HEADERS

# Add warning when using GCC
if test "X$GCC" = Xyes ; then
  CFLAGS="$CFLAGS -Wall"
# The program was developed with:
# CFLAGS="$CFLAGS -Wall -std=iso9899:1999 -Wstrict-prototypes -Wpointer-arith"
fi

AC_PROG_RANLIB

# windres

AC_ARG_VAR([WINDRES], [Path to the windres when available])
AC_PATH_PROG([WINDRES], [windres])
AM_CONDITIONAL([HAVE_WINDRES], [test -n "$WINDRES"])

AM_PATH_GTK_3_0(3.4.0,, [AC_MSG_ERROR([Cannot find GTK+])])

AC_CONFIG_FILES([Makefile gtksudoku.spec src/Makefile
			  debian/Makefile debian/changelog.Debian
			  nsis/Makefile nsis/gtksudoku.nsi])

AC_OUTPUT
