# $OpenBSD: Makefile,v 1.11 2020/08/17 20:47:34 sebastia Exp $

COMMENT=		validators for Ruby OptionParser lib

DISTNAME=		opt_parse_validator-1.9.2
CATEGORIES=		devel

HOMEPAGE=		https://github.com/wpscanteam/OptParseValidator
MAINTAINER=		Sebastian Reitenbach <sebastia@openbsd.org>

# MIT
PERMIT_PACKAGE=	Yes

MODULES=		lang/ruby

CONFIGURE_STYLE=	gem

BUILD_DEPENDS=		${RUN_DEPENDS}
RUN_DEPENDS=		devel/ruby-activesupport,${MODRUBY_FLAVOR}>=5.1.2,<6.1 \
			www/ruby-addressable,${MODRUBY_FLAVOR}>=2.5,<2.8

.include <bsd.port.mk>
