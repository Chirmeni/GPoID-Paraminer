AC_INIT([ParaMiner], [1.0], [Benjamin.Negrevergne@cs.kuleuven.be])
: ${CFLAGS=-O3}
: ${CXXFLAGS=-O3}
AM_INIT_AUTOMAKE([-Wall -Werror foreign])
AC_PROG_CXX
AC_CHECK_LIB([pthread],[pthread_create], [], [
	  echo "pthread library is required for this program."
	  exit -1])

AC_ARG_ENABLE(debug,
AS_HELP_STRING([--enable-debug],
               [enable debugging, default: no]),
[case "${enableval}" in
             yes) debug=true ;;
             no)  debug=false ;;
             *)   AC_MSG_ERROR([bad value ${enableval} for --enable-debug]) ;;
esac],
[debug=false])
AM_CONDITIONAL(DEBUG, test x"$debug" = x"true")

AC_ARG_ENABLE(prof,
AS_HELP_STRING([--enable-prof],
               [enable profiling, default: no]),
[case "${enableval}" in
             yes) prof=true ;;
             no)  prof=false ;;
             *)   AC_MSG_ERROR([bad value ${enableval} for --enable-prof]) ;;
esac],
[prof=false])
AM_CONDITIONAL(PROF, test x"$prof" = x"true")

AC_CONFIG_HEADERS([config.h])
AC_CONFIG_FILES([
 Makefile
 src/Makefile
 data/Makefile
 tests/Makefile
 scripts/Makefile
 tests/tests-env.sh
])

AC_CONFIG_SUBDIRS([melinda])
AC_OUTPUT