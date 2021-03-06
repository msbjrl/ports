# $OpenBSD: Makefile,v 1.444 2020/11/17 16:07:07 landry Exp $

COMMENT =	Firefox web browser
ONLY_FOR_ARCHS =	amd64 i386 aarch64

# Don't forget to bump www/firefox-i18n after updates.

MOZILLA_VERSION =	83.0
MOZILLA_BRANCH =	release
MOZILLA_PROJECT =	firefox
MOZILLA_CODENAME =	browser

WRKDIST =	${WRKDIR}/${MOZILLA_DIST}-${MOZILLA_DIST_VERSION:C/b[0-9]*//}
HOMEPAGE =	https://www.mozilla.org/firefox/
SO_VERSION =	97.0
# NOTE: Must bump minor version if any shlib's are removed from the
# components dir to avoid pkg_add -r issues.
MOZILLA_LIBS =	mozavcodec mozavutil mozgtk xul clearkey lgpllibs mozsqlite3

CATEGORIES =	www

# mozilla public license
PERMIT_PACKAGE=	Yes

# lots of logic in mozilla.port.mk
MODULES =	www/mozilla lang/python

MODPY_RUNDEP =	No
MODPY_VERSION =	${MODPY_DEFAULT_VERSION_3}

COMPILER =	ports-clang
MODCLANG_ARCHS =	amd64 i386

# 63 requires node because why not #1483595
BUILD_DEPENDS +=	lang/node
# 63 requires cbindgen #1478813
BUILD_DEPENDS +=	devel/cbindgen>=0.15.0
#1670807
BUILD_DEPENDS +=	devel/m4

# uses pledge()
WANTLIB += X11-xcb Xcursor Xi intl xcb xcb-shm harfbuzz ${COMPILER_LIBCXX}

# Regression tests are too hard to adapt to run here
NO_TEST =	Yes

CONFIGURE_STYLE =	simple
CONFIGURE_ARGS +=	--prefix=${PREFIX}
MAKE_ENV +=		BUILD_VERBOSE_LOG="1" CARGOFLAGS="-j${MAKE_JOBS}"
CONFIGURE_ENV +=	M4=/usr/local/bin/gm4

CONFIGURE_ARGS +=	--enable-release #1386371
CONFIGURE_ARGS +=	--enable-sandbox
CONFIGURE_ARGS +=	--with-libclang-path=${LOCALBASE}/lib

# XXX badly formed debug ?
DWZ = :
DEBUG_PACKAGES =	${BUILD_PACKAGES}
DEBUG_CONFIGURE_ARGS +=	--enable-debug-symbols \
			--disable-install-strip

show-commit:
	@curl -s https://releases.mozilla.org/pub/mozilla.org/firefox/releases/${MOZILLA_VERSION}/SOURCE| awk -F / '/^https:\/\/hg/ {print $$7 }'

post-install:
	${SUBST_MAN} ${FILESDIR}/mozilla-firefox.1 \
		${PREFIX}/man/man1/firefox.1
	# install prefs
	${INSTALL_DATA_DIR} ${PREFIX}/lib/${MOZILLA_PROJECT}/browser/defaults/preferences
	${SUBST_DATA} ${FILESDIR}/all-openbsd.js \
		${PREFIX}/lib/${MOZILLA_PROJECT}/browser/defaults/preferences/all-openbsd.js
	# install distribution.ini file
	${INSTALL_DATA_DIR} ${PREFIX}/lib/${MOZILLA_PROJECT}/distribution
	echo "[Global]\nid=OpenBSD\nversion=${OSREV}\nabout=Packaged by ${MAINTAINER}\n" > \
		${PREFIX}/lib/${MOZILLA_PROJECT}/distribution/distribution.ini
	# install desktop file
	${INSTALL_DATA_DIR} ${PREFIX}/share/applications/
	${SUBST_DATA} ${WRKSRC}/taskcluster/docker/firefox-snap/${MOZILLA_PROJECT}.desktop \
		${PREFIX}/share/applications/${MOZILLA_PROJECT}.desktop

	# install icon for desktop file
	${INSTALL_DATA_DIR} ${PREFIX}/share/pixmaps/
	${INSTALL_DATA} ${PREFIX}/lib/${MOZILLA_PROJECT}/browser/chrome/icons/default/default128.png \
		${PREFIX}/share/pixmaps/${MOZILLA_PROJECT}.png

	# link default48.png to default.png to be used by default by non-icccm compliant wm
	ln -f ${PREFIX}/lib/${MOZILLA_PROJECT}/browser/chrome/icons/default/default{48,}.png

.for f in unveil.content unveil.gpu unveil.main pledge.content pledge.gpu pledge.main
	${INSTALL_DATA} ${FILESDIR}/${f} ${PREFIX}/lib/${MOZILLA_PROJECT}/browser/defaults/preferences/
.endfor

.include <bsd.port.mk>
