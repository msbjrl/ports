# $OpenBSD: Makefile,v 1.28 2020/05/14 19:44:34 rsadowski Exp $

COMMENT =	desktop screenshot utility (make image)
CATEGORIES =	graphics x11

GH_ACCOUNT =	naelstrof
GH_PROJECT =	maim
GH_TAGNAME =	v5.6.3

MAINTAINER =	Rafael Sadowski <rsadowski@openbsd.org>

# GPLv3+
PERMIT_PACKAGE =	Yes

WANTLIB += ${COMPILER_LIBCXX} GL ICE SM X11 Xcomposite Xext Xfixes
WANTLIB += Xrandr Xrender c icuuc jpeg m png slopy z

MODULES =		devel/cmake

COMPILER =		base-clang ports-gcc

BUILD_DEPENDS =		graphics/glm

LIB_DEPENDS +=		graphics/jpeg \
			graphics/png \
			graphics/slop \
			textproc/icu4c

CONFIGURE_ARGS +=	-DCMAKE_INSTALL_MANDIR="${LOCALBASE}/man" \
			-DCMAKE_INSTALL_PREFIX=${LOCALBASE}

NO_TEST =	Yes

.include <bsd.port.mk>
