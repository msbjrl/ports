# $OpenBSD: Makefile,v 1.4 2020/11/03 16:12:34 rsadowski Exp $

COMMENT =	KDE development helper scripts
DISTNAME =	kde-dev-scripts-${VERSION}
CATEGORIES =	devel

HOMEPAGE =	https://kde.org/applications/development/

# At build time
MODKDE5_DOCS = yes

MODULES +=	lang/python \
		perl

RUN_DEPENDS =	math/graphviz

MODPERL_ADJ_FILES = \
	colorsvn \
	cvs-clean \
	cvsblame \
	cvscheck \
	fixkdeincludes \
	fixuifiles \
	extend_dmalloc \
	cxxmetric \
	cvslastchange \
	extractattr \
	extractrc \
	svnintegrate \
	svnlastchange \
	svn-clean \
	png2mng.pl \
	noncvslist \
	kdemangen.pl \
	includemocs \
	krazy-licensecheck

MODPY_ADJ_FILES = \
	grantlee_strings_extractor.py \
	kde-systemsettings-tree.py \
	kde_generate_export_header \
	kdelnk2desktop.py \
	reviewboard-am \
	zonetab2pot.py \

.include <bsd.port.mk>
