# $OpenBSD: Makefile,v 1.51 2020/11/19 15:17:48 ajacoutot Exp $

PKG_ARCH=	*

COMMENT=	utilities for manipulating PostScript documents

V=		2.04
DISTNAME=	psutils-${V}

CATEGORIES=	print

HOMEPAGE=	https://github.com/rrthomas/psutils

MAINTAINER=	Antoine Jacoutot <ajacoutot@openbsd.org>

# BSD-like (${WRKSRC}/LICENSE)
PERMIT_PACKAGE=	Yes

MASTER_SITES=	https://github.com/rrthomas/psutils/releases/download/v${V}/

MODULES=	perl

RUN_DEPENDS=	devel/p5-IPC-Run3 \
		print/ghostscript/gnu \
		print/libpaper

USE_GMAKE=	Yes

CONFIGURE_STYLE=gnu

NO_TEST=	Yes

.include <bsd.port.mk>
