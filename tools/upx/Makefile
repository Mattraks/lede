#
# Copyright (C) 2011-2020 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#
include $(TOPDIR)/rules.mk

PKG_NAME:=upx
PKG_VERSION:=4.0.0

PKG_SOURCE_PROTO:=git
PKG_SOURCE_VERSION:=51f69a20e0287904398bbf4c72ba2f809a0b0850
PKG_SOURCE_URL:=https://github.com/upx/upx.git
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION)-src.tar.gz

include $(INCLUDE_DIR)/host-build.mk

define Host/Compile
	UPX_UCLDIR=$(STAGING_DIR_HOST) \
	$(MAKE) -C $(HOST_BUILD_DIR)/src \
		CXXFLAGS_WERROR="" LDFLAGS="$(HOST_LDFLAGS)" \
		CXX="$(HOSTCXX)"
endef

define Host/Install
	$(CP) $(HOST_BUILD_DIR)/src/upx.out $(STAGING_DIR_HOST)/bin/upx
endef

define Host/Clean
	rm -f $(STAGING_DIR_HOST)/bin/upx
endef

$(eval $(call HostBuild))
