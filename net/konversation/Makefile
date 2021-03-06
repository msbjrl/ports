# $OpenBSD: Makefile,v 1.19 2020/11/02 17:26:09 rsadowski Exp $

COMMENT =	IRC client for KDE

V =		1.7.7
DISTNAME =	konversation-$V

CATEGORIES =	net

HOMEPAGE =	https://konversation.kde.org/

MASTER_SITES =	${MASTER_SITE_KDE:=stable/konversation/$V/src/}

WANTLIB += ${COMPILER_LIBCXX} KF5Archive KF5Auth KF5AuthCore KF5Bookmarks
WANTLIB += KF5Codecs KF5Completion KF5ConfigCore KF5ConfigGui
WANTLIB += KF5ConfigWidgets KF5CoreAddons KF5Crash KF5DBusAddons
WANTLIB += KF5Emoticons KF5GlobalAccel KF5I18n KF5IconThemes KF5IdleTime
WANTLIB += KF5ItemViews KF5JobWidgets KF5KIOCore KF5KIOFileWidgets
WANTLIB += KF5KIOGui KF5KIOWidgets KF5Notifications KF5NotifyConfig
WANTLIB += KF5Parts KF5Service KF5Solid KF5SonnetUi KF5TextWidgets
WANTLIB += KF5Wallet KF5WidgetsAddons KF5WindowSystem KF5XmlGui
WANTLIB += Qt5Concurrent Qt5Core Qt5DBus Qt5Gui Qt5Network Qt5Widgets
WANTLIB += Qt5Xml c m phonon4qt5 qca-qt5

# GPLv2+
PERMIT_PACKAGE =	Yes

MODULES =		devel/kf5 \
			lang/python

BUILD_DEPENDS +=	devel/kf5/kdoctools \
			devel/kf5/kitemmodels \
			devel/gettext,-tools

RUN_DEPENDS +=		devel/desktop-file-utils \
			devel/gettext,-runtime \
			x11/gtk+3,-guic

LIB_DEPENDS +=		security/qca-qt5 \
			devel/kf5/karchive  \
			devel/kf5/kbookmarks \
			devel/kf5/kconfigwidgets \
			devel/kf5/kcoreaddons \
			devel/kf5/kcrash \
			devel/kf5/kemoticons \
			devel/kf5/ki18n  \
			devel/kf5/kidletime \
			devel/kf5/knotifyconfig \
			devel/kf5/kio \
			devel/kf5/kparts \
			devel/kf5/solid \
			devel/kf5/kwallet \
			devel/kf5/kwidgetsaddons \
			devel/kf5/kglobalaccel \
			devel/kf5/kdbusaddons \
			devel/kf5/knotifications  \
			devel/kf5/kwindowsystem \
			devel/kf5/kiconthemes \
			devel/kf5/kitemviews \
			multimedia/phonon

post-install:
	${MODPY_BIN} ${MODPY_LIBDIR}/compileall.py \
		${PREFIX}/share/konversation/scripting_support/python/konversation

.include <bsd.port.mk>
