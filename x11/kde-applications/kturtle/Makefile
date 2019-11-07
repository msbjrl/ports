# $OpenBSD: Makefile,v 1.1.1.1 2019/11/07 10:15:28 rsadowski Exp $

COMMENT =	KDE educational Logo programming environment
DISTNAME =	kturtle-${VERSION}
CATEGORIES =	games

HOMEPAGE =	https://www.kde.org/applications/games/kturtle


WANTLIB += ${COMPILER_LIBCXX} KF5Attica KF5Auth KF5Codecs KF5ConfigCore
WANTLIB += KF5ConfigGui KF5ConfigWidgets KF5CoreAddons KF5Crash
WANTLIB += KF5I18n KF5KIOCore KF5NewStuff KF5NewStuffCore KF5Service
WANTLIB += KF5SonnetUi KF5TextWidgets KF5WidgetsAddons KF5XmlGui
WANTLIB += Qt5Concurrent Qt5Core Qt5DBus Qt5Gui Qt5Network Qt5PrintSupport
WANTLIB += Qt5Svg Qt5Widgets Qt5Xml c m

MODKDE5_DESKTOP_FILE = yes
MODKDE5_ICON_CACHE = yes
MODKDE5_TRANSLATIONS = yes
MODKDE5_DOCS = yes

MODULES +=	x11/kde-applications

LIB_DEPENDS +=	devel/kf5/attica \
		devel/kf5/kauth \
		devel/kf5/kcodecs \
		devel/kf5/kconfig \
		devel/kf5/kconfigwidgets \
		devel/kf5/kcoreaddons \
		devel/kf5/kcrash \
		devel/kf5/ki18n \
		devel/kf5/kio \
		devel/kf5/knewstuff \
		devel/kf5/ktextwidgets \
		devel/kf5/kxmlgui \
		devel/kf5/sonnet \
		x11/qt5/qtsvg

.include <bsd.port.mk>