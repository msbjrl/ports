# $OpenBSD: Makefile,v 1.8 2020/11/08 20:12:59 rsadowski Exp $

COMMENT =	printing management for KDE
DISTNAME =	print-manager-${VERSION}
CATEGORIES =	sysutils print

HOMEPAGE =	https://kde.org/applications/utilities/org.kde.print-manager

SHARED_LIBS +=  kcupslib          62.0 # 18.18.0

WANTLIB += ${COMPILER_LIBCXX} KF5Auth KF5AuthCore KF5Codecs KF5Completion
WANTLIB += KF5ConfigCore KF5ConfigGui KF5ConfigWidgets KF5CoreAddons
WANTLIB += KF5DBusAddons KF5I18n KF5IconThemes KF5JobWidgets KF5KCMUtils
WANTLIB += KF5KIOCore KF5KIOGui KF5KIOWidgets KF5Notifications
WANTLIB += KF5Service KF5WidgetsAddons KF5WindowSystem Qt5Concurrent
WANTLIB += Qt5Core Qt5DBus Qt5Gui Qt5Network Qt5Qml Qt5Quick Qt5Widgets
WANTLIB += Qt5Xml c cups m

MODKDE5_DESKTOP_FILE = yes
MODKDE5_TRANSLATIONS = yes
MODKF5_I18N_CONFLICT = yes
MODKF5_L10N_CONFLICT = yes

BUILD_DEPENDS =	x11/qt5/qtquickcontrols \
		devel/kf5/plasma-framework

RUN_DEPENDS =	x11/qt5/qtquickcontrols \
		x11/qt5/qtquickcontrols2

LIB_DEPENDS =	devel/kf5/kauth \
		devel/kf5/kcmutils \
		devel/kf5/kcodecs \
		devel/kf5/kcompletion \
		devel/kf5/kconfig \
		devel/kf5/kconfigwidgets \
		devel/kf5/kcoreaddons \
		devel/kf5/kdbusaddons \
		devel/kf5/ki18n \
		devel/kf5/kiconthemes \
		devel/kf5/kio \
		devel/kf5/kjobwidgets \
		devel/kf5/knotifications \
		devel/kf5/kservice \
		devel/kf5/kwidgetsaddons \
		devel/kf5/kwindowsystem \
		x11/qt5/qtdeclarative \
		print/cups,-libs

.include <bsd.port.mk>
