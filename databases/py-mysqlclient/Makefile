# $OpenBSD: Makefile,v 1.16 2020/12/11 16:11:42 sthen Exp $

COMMENT =		Python interface to MySQL

MODPY_EGG_VERSION =	2.0.2
DISTNAME =		mysqlclient-${MODPY_EGG_VERSION}
PKGNAME =		py-${DISTNAME}

CATEGORIES =		databases

# https://github.com/PyMySQL/mysqlclient-python/
HOMEPAGE =		https://mysqlclient.readthedocs.io/

# GPLv2+
PERMIT_PACKAGE =	Yes

WANTLIB += ${MODPY_WANTLIB} mariadb pthread

MASTER_SITES =		${MASTER_SITE_PYPI:=m/mysqlclient/}

MODULES =		lang/python
MODPY_SETUPTOOLS =	Yes
MODPY_PYTEST =		Yes

FLAVORS =		python3
FLAVOR =		python3

LIB_DEPENDS =		databases/mariadb

# You must setup a default.cnf file config and a MySQL server
TEST_IS_INTERACTIVE =	Yes
TEST_DEPENDS =		databases/mariadb \
			devel/py-mock${MODPY_FLAVOR}

.include <bsd.port.mk>
