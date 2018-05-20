include $(TOPDIR)/rules.mk

PKG_NAME:=smartscope-wifi
PKG_VERSION:=1.0
PKG_RELEASE:=1
PKG_INSTALL:=1

PKG_MAINTAINER:=Jasper van Bourgognie <jasper@lab-nation.com>

PKG_LICENSE:=GPL
PKG_LICENSE_FILES:=COPYING

include $(INCLUDE_DIR)/package.mk

define Package/smartscope-wifi
  SECTION:=utils
  CATEGORY:=Utilities
  TITLE:=SmartScope wifi config
  URL:=http://www.lab-nation.com/
  MENU:=1
endef

define Package/smartscope-wifi/description
 Enable wifi by default and set ssid to SmartScope XXXX
endef

define Package/smartscope-wifi/config
	config SMARTSCOPE_WIFI_SSID
		depends on PACKAGE_smartscope-wifi
		string "SSID"
		default "SmartScope `strings /dev/mtd1|grep SSID1|cut -d '_' -f 2`"
endef

define Package/smartscope-wifi/install
	$(INSTALL_DIR) $(1)/etc/uci-defaults
	sed ./25_enable_wireless.template 's/SSID=/SSID=$(SMARTSCOPE_WIFI_SSID)/g' > ./25_enable_wireless
	$(INSTALL_DATA) ./25_enable_wireless $(1)/etc/uci-defaults/25_enable_wireless
endef

define Build/Compile
endef

define Build/Install
endef


$(eval $(call BuildPackage,smartscope-wifi))

