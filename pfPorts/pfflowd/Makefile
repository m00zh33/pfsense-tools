# New ports collection makefile for:   pfflowd
# Date created:        24 Feburary 2003
# Whom:                Andrew Thompson <andy@fud.org.nz>
#
# $FreeBSD: ports/net/pfflowd/Makefile,v 1.9 2005/09/14 23:26:59 pav Exp $
#

PORTNAME=	pfflowd
PORTVERSION=	0.6
CATEGORIES=	net
MASTER_SITES=	http://www.mindrot.org/files/pfflowd/
NO_STAGE=	yes

MAINTAINER=	thompsa@FreeBSD.org
COMMENT=	Convert pfsync states to NetFlow datagrams

MAN8=		pfflowd.8

PLIST_FILES=	sbin/pfflowd \
		etc/rc.d/pfflowd.sh.sample

.include <bsd.port.pre.mk>

.if ${OSVERSION} < 502106
IGNORE=		"Only for 5.3 and above"
.endif

.if ${OSVERSION} < 502119
EXTRA_PATCHES+=	${FILESDIR}/pf34-Makefile
.endif

post-patch:
	${SED} -e 's|@@PREFIX@@|${PREFIX}|g' < ${FILESDIR}/pfflowd.sh.sample \
		> ${WRKSRC}/pfflowd.sh.sample

pre-build:
	${CAT} ${FILESDIR}/pidfile.h > ${WRKSRC}/pidfile.h
	${CAT} ${FILESDIR}/pidfile.c > ${WRKSRC}/pidfile.c

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/pfflowd ${PREFIX}/sbin
	${INSTALL_MAN} ${WRKSRC}/pfflowd.8 ${PREFIX}/man/man8
	${INSTALL_SCRIPT} ${WRKSRC}/pfflowd.sh.sample ${PREFIX}/etc/rc.d/pfflowd.sh.sample

.include <bsd.port.post.mk>
