# $OpenBSD: Makefile,v 1.15 2020/08/10 14:52:11 bket Exp $

# using bundled c-ares which is patched for TTL support
COMMENT =		python interface for c-ares

MODPY_EGG_VERSION =	3.1.1
REVISION =		0
DISTNAME =		pycares-${MODPY_EGG_VERSION}
PKGNAME =		py-cares-${MODPY_EGG_VERSION}
CATEGORIES =		net

# MIT
PERMIT_PACKAGE =	Yes

WANTLIB += pthread ${MODPY_WANTLIB}

MODULES =		lang/python

MODPY_PI =		Yes
MODPY_SETUPTOOLS =	Yes
MODPY_PYTEST =		Yes
MODPY_PYTEST_ARGS =	tests/tests.py

USE_GMAKE =		Yes

FLAVORS =		python3
FLAVOR =		python3

RUN_DEPENDS =		devel/py-cffi${MODPY_FLAVOR}
BUILD_DEPENDS =		${RUN_DEPENDS}
TEST_DEPENDS =		${FULLPKGNAME}:${BUILD_PKGPATH}

.include <bsd.port.mk>
