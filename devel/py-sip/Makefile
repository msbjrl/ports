# $OpenBSD: Makefile,v 1.51 2020/07/03 21:12:49 sthen Exp $

COMMENT=	automatically generate Python bindings for C and C++ libs

# XXX  py-sip updates FREQUENTLY break other ports
# XXX  BE ESPECIALLY CAREFUL WHEN TESTING UPDATES!

MODPY_EGG_VERSION =	4.19.19
EPOCH=		0
DISTNAME=	sip-${MODPY_EGG_VERSION}
PKGNAME=	py-${DISTNAME}
CATEGORIES=	devel
REVISION=	0

HOMEPAGE=	https://www.riverbankcomputing.com/software/sip/intro

# SIP license (Python like)
PERMIT_PACKAGE=	Yes

WANTLIB=	m c ${COMPILER_LIBCXX}

COMPILER =		base-clang ports-gcc base-gcc

MASTER_SITES=	https://www.riverbankcomputing.com/static/Downloads/sip/${MODPY_EGG_VERSION}/

MODULES=	lang/python

FLAVORS =	python3
FLAVOR ?=

CONFIGURE_STYLE=simple
CONFIGURE_SCRIPT=${MODPY_BIN} configure.py
CONFIGURE_ARGS=	-b ${PREFIX}/bin \
		-d ${MODPY_SITEPKG} \
		-e ${MODPY_INCDIR} \
		-v ${PREFIX}/share/sip \
		INCDIR=${LOCALBASE}/include \
		LIBDIR=${LOCALBASE}/lib \
		CC=${CC} CXX=${CXX} \
		CFLAGS="${CFLAGS}" \
		CXXFLAGS="${CXXFLAGS}"

NO_TEST=	Yes

SUBST_VARS +=	MODPY_LIB_SUFFIX
pre-configure:
	${SUBST_CMD} ${WRKSRC}/configure.py

# mk_distinfo.py tries to open sip_bin but it hasnt been renamed yet
.if ${FLAVOR:Mpython3}
pre-fake:
	cd ${PREFIX}/bin && ln -sf sip sip${MODPY_BIN_SUFFIX}
.endif

post-install:
	${MODPY_BIN} ${MODPY_LIBDIR}/compileall.py ${WRKINST}${MODPY_SITEPKG}
	${INSTALL_DATA_DIR} ${PREFIX}/share/doc/${MODPY_PY_PREFIX}sip
	${INSTALL_DATA} ${WRKSRC}/doc/html/_sources/* ${PREFIX}/share/doc/${MODPY_PY_PREFIX}sip
	mv -f ${PREFIX}/bin/sip ${PREFIX}/bin/sip${MODPY_BIN_SUFFIX}

.include <bsd.port.mk>
