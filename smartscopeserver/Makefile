include $(TOPDIR)/rules.mk

PKG_NAME:=smartscopeserver
PKG_VERSION:=1.0
PKG_RELEASE:=1
PKG_INSTALL:=1
PKG_BUILD_DIR:=$(BUILD_DIR)/smartscopeserver-$(PKG_VERSION)

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL=git://github.com/louiecaulfield/DeviceInterface.CXX
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_VERSION=master
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.bz2

PKG_MAINTAINER:=Jasper van Bourgognie <jasper@lab-nation.com>

PKG_LICENSE:=GPL
PKG_LICENSE_FILES:=COPYING

#PKG_FIXUP:=autoreconf
#PKG_REMOVE_FILES:=conftools/libtool.m4

$(eval $(echo blabl))

include $(INCLUDE_DIR)/package.mk

define Package/smartscopeserver
  SECTION:=utils
  CATEGORY:=Utilities
  DEPENDS:=+libusb-1.0 +libavahi-client +libpthread +libstdcpp
  TITLE:=SmartScope network server
  URL:=http://www.lab-nation.com/
endef

define Package/smartscopeserver/description
 A server to connect to the smartscope over IP
endef

define Package/smartscopeserver/install
	$(INSTALL_DIR) $(1)/etc/init.d
	$(INSTALL_BIN) ./smartscope.init $(1)/etc/init.d/smartscope
	$(INSTALL_DIR) $(1)/usr/bin
	$(CP) $(PKG_BUILD_DIR)/smartscopeserver $(1)/usr/bin/
endef

$(eval $(call BuildPackage,smartscopeserver))
