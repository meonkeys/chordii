# This file is part of Chordii.
#
# Chordii is free software: you can redistribute it and/or modify
# it under the terms of the GNU General Public License as published by
# the Free Software Foundation, either version 3 of the License, or
# (at your option) any later version.
#
# Chordii is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
# GNU General Public License for more details.
#
# You should have received a copy of the GNU General Public License
# along with Chordii.  If not, see <http://www.gnu.org/licenses/>.

AC_INIT([Chordii], [4.5.3b], [jvromans@users.sourceforge.net])

AM_INIT_AUTOMAKE

AC_CONFIG_HEADER([src/config.h])

# Checks for programs.
AC_PROG_CC

# Checks for libraries.

# Checks for header files.
AC_FUNC_ALLOCA
AC_HEADER_STDC
AC_CHECK_HEADERS([stdlib.h string.h unistd.h getopt.h])

# Checks for typedefs, structures, and compiler characteristics.
AC_C_CONST

# Checks for library functions.
AC_CHECK_FUNCS([strdup])

# Do we need this one?
AC_REPLACE_FUNCS

# Enforce programmer sanity.
if test "$CC" = "gcc"; then
  CFLAGS="$CFLAGS -Wall -pedantic -g"
fi
AC_SUBST(CFLAGS)

# --enable-latin2 configure option.
AC_MSG_CHECKING([whether to use ISO-8895.2 (Latin-2) for input data])
AC_ARG_ENABLE(latin2,
  AC_HELP_STRING([--enable-latin2], [use ISO-8859.2 (Latin-2) for input data]),
  [if test "${enable_latin2}" = "yes" ; then
    AC_DEFINE(WITH_LATIN2, 1, Use ISO-8859.2 (Latin-2) encoding for input data)
    AC_MSG_RESULT([yes])
   else
    AC_MSG_RESULT([no])
   fi],
   # Default value for configure
   AC_MSG_RESULT([no])
)

# Desired output files.
AC_CONFIG_FILES([
  Makefile 
  src/Makefile
  man/Makefile
  chordii.spec
  windows/config.h
])
AC_OUTPUT
