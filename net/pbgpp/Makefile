# $OpenBSD: Makefile,v 1.6 2020/07/03 21:13:00 sthen Exp $

COMMENT =	pcap bgp parser

MODPY_EGG_VERSION =	0.2.22
DISTNAME =	pbgpp-${MODPY_EGG_VERSION}
REVISION =	0

CATEGORIES =	net

MAINTAINER =	Peter Hessler <phessler@openbsd.org>

# Apache 2.0
PERMIT_PACKAGE =	Yes

MODULES =		lang/python
MODPY_PI =		Yes
MODPY_SETUPTOOLS =	Yes
MODPY_VERSION =		${MODPY_DEFAULT_VERSION_3}

RUN_DEPENDS =		net/py-pcapy${MODPY_FLAVOR}
BUILD_DEPENDS +=	${RUN_DEPENDS}

# tests depend on a running kafka
NO_TEST =		Yes

.include <bsd.port.mk>
