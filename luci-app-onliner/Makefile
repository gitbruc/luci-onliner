# SPDX-License-Identifier: GPL-3.0-or-later
#
# Copyright (C) 2016 Openwrt.org
# Copyright (C) 2024 gitbruc <nobody3@duck.com>
# This is free software, licensed under the Apache License, Version 2.0 .
#

include $(TOPDIR)/rules.mk

LUCI_TITLE:=LuCI support arp online
LUCI_DEPENDS:= 
LUCI_PKGARCH:=all
PKG_NAME:=luci-app-onliner
PKG_VERSION:=1.1
PKG_RELEASE:=6

define Package/luci-app-onliner/install
    $(INSTALL_DIR) $(1)/usr/lib/lua/luci
	cp -pR ./luasrc/* $(1)/usr/lib/lua/luci
	$(INSTALL_DIR) $(1)/
	cp -pR ./root/* $(1)/
endef

define Package/luci-app-onliner/postinst
#!/bin/sh
	rm -f /tmp/luci-indexcache
	rm -f /tmp/luci-modulecache/*
	chmod -R 755 /usr/share/onliner/*
exit 0
endef
include $(TOPDIR)/feeds/luci/luci.mk

# call BuildPackage - OpenWrt buildroot signature
