# $OpenBSD: Makefile,v 1.38 2020/10/28 17:52:16 kirby Exp $

COMMENT =		seafile client

GH_ACCOUNT =		haiwen
GH_PROJECT =		seafile-client
# upstream keep on sliding tags to pull in new commits
# this commit is from the "v7.0.10" tag
GH_COMMIT =		5722c864659a142193cc45737fa7118f9782504f
DISTNAME =		seafile-client-7.0.10pl20201026

WANTLIB += Qt5Core Qt5DBus Qt5Gui Qt5Network Qt5Widgets c
WANTLIB += crypto event_core event_extra gio-2.0 glib-2.0 gobject-2.0
WANTLIB += intl jansson m pthread seafile searpc sqlite3 ssl z
WANTLIB += ${COMPILER_LIBCXX}

MODULES =		devel/cmake x11/qt5
LIB_DEPENDS =		net/seafile/seafile \
			databases/sqlite3
RUN_DEPENDS =		devel/desktop-file-utils \
			x11/gtk+3,-guic

NO_TEST =		Yes

post-configure:
	cd ${WRKSRC}/i18n/ && ${MODQT_LRELEASE} *.ts

.include <bsd.port.mk>
