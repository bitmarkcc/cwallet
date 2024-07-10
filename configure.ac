AC_INIT([cwallet], [1.2], [bug-automake@gnu.org])
AM_INIT_AUTOMAKE([-Wall -Werror foreign])
AC_PROG_CC
AM_PROG_CC_C_O
AC_CONFIG_HEADERS([config.h])

PKG_CHECK_MODULES([GTK2],[gtk+-2.0])

AC_CHECK_HEADERS([db.h] [openssl/bn.h] [openssl/sha.h] [openssl/ripemd.h] [openssl/ec.h] [openssl/obj_mac.h], ,AC_MSG_ERROR([*** Some required headers not found]))

AC_CHECK_LIB([dl],[dlopen],,AC_MSG_ERROR([*** libdl not found]))
AC_CHECK_LIB([pthread],[pthread_once],,AC_MSG_ERROR([*** libpthread not found]))
AC_CHECK_LIB([db],[db_create],,AC_MSG_ERROR([*** libdb not found]))
AC_CHECK_LIB([crypto],[SHA256],,AC_MSG_ERROR([*** libcrypto not found]))

LIBS="-Wl,-Bstatic $LIBS"

AC_CHECK_PROG(HAVE_QRENCODE,qrencode,true,false)

if test "x$HAVE_QRENCODE" = "xfalse"; then
   AC_MSG_ERROR([*** qrencode not found])
fi

AC_CONFIG_FILES([
 Makefile
 src/Makefile
])
AC_OUTPUT
