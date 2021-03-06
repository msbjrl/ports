# $OpenBSD: Makefile,v 1.16 2020/11/06 07:40:16 ajacoutot Exp $

COMMENT=		generic spell checking library

V=			2.2.13
DISTNAME=		enchant-${V}
PKGNAME=		enchant2-${V}

SHARED_LIBS +=  enchant-2            0.1      # 4.13

CATEGORIES=		textproc

HOMEPAGE=		https://abiword.github.io/enchant/

MAINTAINER=		Antoine Jacoutot <ajacoutot@openbsd.org>

# LGPLv2.1
PERMIT_PACKAGE=	Yes

WANTLIB += ${COMPILER_LIBCXX} aspell c curses glib-2.0 gmodule-2.0
WANTLIB += hunspell-1.7 iconv intl m pcre

MASTER_SITES =		https://github.com/AbiWord/enchant/releases/download/v${V}/

# c++11
COMPILER =		base-clang ports-gcc

LIB_DEPENDS=		devel/glib2 \
			textproc/aspell/core \
			textproc/hunspell

AUTOCONF_VERSION=	2.69
CONFIGURE_STYLE=	autoconf

CONFIGURE_ENV=		CPPFLAGS="-I${LOCALBASE}/include" \
			LDFLAGS="-L${LOCALBASE}/lib" \
			ac_cv_prog_VALGRIND=

CONFIGURE_ARGS=		--without-applespell \
			--without-voikko \
			--without-zemberek \
			--without-nuspell

DEBUG_PACKAGES=		${BUILD_PACKAGES}

# prevent conflict with textproc/enchant
MAKE_FLAGS=		pkgdatadir=${TRUEPREFIX}/share/enchant-2
FAKE_FLAGS=		pkgdatadir=${PREFIX}/share/enchant-2

post-install:
	rm ${PREFIX}/lib/enchant-2/*.{a,la}

.include <bsd.port.mk>
