# New ports collection makefile for:	php5
# Date created:				Tue Feb 18 11:17:13 CET 2003
# Whom:					Alex Dupre <sysadmin@alexdupre.com>
#
# $FreeBSD: ports/lang/php5/Makefile,v 1.126 2008/05/02 08:52:07 ale Exp $
#

PORTNAME=	php5
PORTVERSION=	5.2.6
PORTREVISION?=	0
CATEGORIES?=	lang devel www
DISTNAME=	php-${PORTVERSION}
NO_STAGE=	yes

all:	build

build:
	mkdir -p /usr/local/lib/php/20060613
	mkdir -p /usr/local/lib/php/extensions/no-debug-non-zts-20060613/
	[ ! -f /usr/local/lib/php/extensions/no-debug-non-zts-20060613/* ] || \
		cp /usr/local/lib/php/extensions/no-debug-non-zts-20060613/* /usr/local/lib/php/20060613/
	cp /usr/local/bin/php-cgi /usr/local/bin/php
	chmod a+rx /usr/local/bin/php

install:
	mkdir -p /usr/local/lib/php/20060613
	mkdir -p /usr/local/lib/php/extensions/no-debug-non-zts-20060613/	
	[ ! -f /usr/local/lib/php/extensions/no-debug-non-zts-20060613/* ] || \
		cp /usr/local/lib/php/extensions/no-debug-non-zts-20060613/* /usr/local/lib/php/20060613/
	cp /usr/local/bin/php-cgi /usr/local/bin/php
	chmod a+rx /usr/local/bin/php

clean:

deinstall:

distclean:

build-depends-list:
