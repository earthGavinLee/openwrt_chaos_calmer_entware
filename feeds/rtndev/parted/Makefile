#
# Copyright (C) 2011-2015 Entware
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=parted
PKG_VERSION:=3.2
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.xz
PKG_SOURCE_URL:=@GNU/$(PKG_NAME)
PKG_MD5SUM:=0247b6a7b314f8edeb618159fa95f9cb

PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/parted
	SECTION:=utils
	CATEGORY:=Utilities
	SUBMENU:=disc
	DEPENDS:=+libblkid
	TITLE:=manipulates partition tables
	URL:=http://www.gnu.org/software/parted/
	MAINTAINER:=Entware team, entware.wl500g.info
endef

define Package/parted/description
 GNU Parted manipulates partition tables. This is useful for creating space for
 new operating systems, reorganizing disk usage, copying data on hard disks and
 disk imaging.
endef

CONFIGURE_ARGS += \
	--disable-device-mapper \
	--without-readline

define Package/parted/install
	$(INSTALL_DIR) $(1)/opt/sbin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/opt/sbin/part{ed,probe} $(1)/opt/sbin
	$(INSTALL_DIR) $(1)/opt/lib
	$(CP) $(PKG_INSTALL_DIR)/opt/lib/libparted.so* $(1)/opt/lib
endef

$(eval $(call BuildPackage,parted))
