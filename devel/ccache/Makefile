# $OpenBSD: Makefile,v 1.65 2020/11/15 14:40:50 jca Exp $

COMMENT =	compiler cache

V =		3.7.12
DISTNAME =	ccache-$V

CATEGORIES =	devel

HOMEPAGE =	https://ccache.dev/

# GPLv3+
PERMIT_PACKAGE =	 Yes

WANTLIB += c m z

MASTER_SITES =	https://github.com/ccache/ccache/releases/download/v$V/

CONFIGURE_STYLE =	gnu

DEBUG_PACKAGES =	${BUILD_PACKAGES}

# This port should not have build/run dependencies.
NO_CCACHE =		Yes
DWZ =			:

# Failure in cpp1 test suite appears to be due to an embedded filename
# in a .o file present in one file, and not present in the file being
# compared with.
TEST_DEPENDS =		shells/bash \
			sysutils/coreutils

pre-test:
	ln -fs ${LOCALBASE}/bin/gseq ${WRKDIR}/bin/seq

.include <bsd.port.mk>
