# $OpenBSD: Makefile,v 1.30 2020/12/10 09:09:52 benoit Exp $

COMMENT=	fast shared data cache using memory mapped files

MODULES=	cpan
DISTNAME =	Cache-FastMmap-1.53
CATEGORIES=	devel

# perl
PERMIT_PACKAGE=	Yes

WANTLIB += c perl

TEST_DEPENDS =	devel/p5-Test-Deep

.include <bsd.port.mk>
