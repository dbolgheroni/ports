# $OpenBSD: Makefile,v 1.31 2020/03/26 08:36:26 ajacoutot Exp $

COMMENT=		osinfo database files

V=			20200325
DISTNAME=		osinfo-db-${V}
EXTRACT_SUFX=		.tar.xz

PKG_ARCH=		*
NO_BUILD=		Yes
NO_TEST=		Yes

USE_GMAKE=		No

BUILD_DEPENDS=		misc/osinfo/osinfo-db-tools

CONFIGURE_STYLE=	# empty

do-install:
	osinfo-db-import --root ${WRKINST} --dir ${TRUEPREFIX}/share/osinfo \
		${FULLDISTDIR}/${DISTFILES}

# Adding a new OpenBSD release
# ============================
# - fork+clone https://gitlab.com/libosinfo/osinfo-db
# cd osinfo-db/data/os/openbsd.org/
# cp openbsd-X.Y.xml.in openbsd-X.Y+1.xml.in
# - substitute X.Y => X.Y+1, XY => XY+1, XY-2 => XY-1 etc.
# cd ../../../tests/isodata/openbsd/
# mkdir openbsdX.Y+1 && cd openbsdX.Y+1
# - fetch i386 and amd64 install and boot-only ISOs
# isoinfo -d -i cd66.iso >openbsd-6.6-amd64-bootonly.txt
# isoinfo -d -i install66.iso >openbsd-6.6-amd64.txt
# isoinfo -d -i cd66.iso >openbsd-6.6-i386-bootonly.txt
# isoinfo -d -i install66.iso >openbsd-6.6-i386.txt

.include <bsd.port.mk>
