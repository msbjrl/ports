# $OpenBSD: Makefile,v 1.50 2020/10/03 15:40:00 ajacoutot Exp $

COMMENT=	library for gnome keyring integration

GNOME_PROJECT=	libgnome-keyring
GNOME_VERSION=	3.12.0
REVISION=	8

SHARED_LIBS +=  gnome-keyring        7.0      # 2.0

# GPLv2/LGPLv2
PERMIT_PACKAGE=	Yes

WANTLIB += dbus-1 ffi gcrypt glib-2.0 gmodule-2.0 gobject-2.0
WANTLIB += gpg-error pcre pthread iconv intl

MODULES=	x11/gnome

MODGNOME_TOOLS=	gobject-introspection vala
MODPY_VERSION=	${MODPY_DEFAULT_VERSION_3}

LIB_DEPENDS=	security/libgcrypt \
		x11/dbus \
		devel/glib2

# XXX circular dependency, see x11/gnome/keyring
# org.freedesktop.secrets
#RUN_DEPENDS +=		x11/gnome/keyring

CONFIGURE_STYLE=	gnu

# regression tests call 'env python'
MODULES +=		lang/python
TEST_DEPENDS +=		${MODPY_RUN_DEPENDS} \
			devel/py-gobject3${MODPY_FLAVOR} #test-gi.py
MODPY_RUNDEP=		No
MODPY_BUILDDEP=		No
pre-test:
	ln -sf ${MODPY_BIN} ${WRKDIR}/bin/python

.include <bsd.port.mk>
