# $OpenBSD: Makefile,v 1.48 2019/12/28 10:08:17 ajacoutot Exp $

COMMENT=	multimedia player

DISTNAME=	xine-ui-0.99.12
REVISION=	0
CATEGORIES=	multimedia
MASTER_SITES=	${MASTER_SITE_SOURCEFORGE:=xine/}
EXTRACT_SUFX=	.tar.xz

HOMEPAGE=	https://www.xine-project.org/

# GPLv2+
PERMIT_PACKAGE=	Yes

WANTLIB += X11 Xext Xft Xinerama Xss Xtst Xv Xxf86vm c curl iconv
WANTLIB += intl jpeg m curses png pthread readline xine z

RUN_DEPENDS=	devel/desktop-file-utils \
		misc/shared-mime-info \
		x11/gtk+3,-guic
LIB_DEPENDS=	graphics/jpeg \
		graphics/png \
		multimedia/xine-lib \
		net/curl

MAKE_FLAGS=	V=1

USE_GMAKE=	Yes
CONFIGURE_STYLE= gnu
CONFIGURE_ARGS+=--disable-lirc \
		--disable-nvtvsimple \
		--disable-vdr-keys \
		--without-aalib \
		--without-caca
CONFIGURE_ENV=	CPPFLAGS="-I${X11BASE}/include -I${LOCALBASE}/include" \
		LDFLAGS="-L${X11BASE}/lib -L${LOCALBASE}/lib" \
		ac_cv_header_execinfo_h=no

.include <bsd.port.mk>
