include $(TOPDIR)/rules.mk

PKG_NAME:=mcjoin
PKG_VERSION:=2.12
PKG_RELEASE:=1
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://github.com/troglobit/$(PKG_NAME)/releases/download/v$(PKG_VERSION)
PKG_HASH:=feaf5c7eef884ba98bbc20bbeba133fb6c5ee6c9251dbe05531788094014abda
PKG_LICENSE:=ISC
PKG_MAINTAINER:=Joachim Wiberg
PKG_BUILD_PARALLEL:=1

include $(INCLUDE_DIR)/package.mk

PKG_BUILD_DIR := $(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)

define Build/Compile
	$(MAKE) -C $(PKG_BUILD_DIR)
endef

define Package/$(PKG_NAME)
  SECTION:=utils
  CATEGORY:=Utilities
  TITLE:=Simple multicast testing application
endef

define Package/$(PKG_NAME)/description
  MCJOIN is a simple and easy-to-use tool to test IPv4 and IPv6 multicast.
endef

define Package/$(PKG_NAME)/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/src/$(PKG_NAME) $(1)/usr/sbin/$(PKG_NAME)
endef

$(eval $(call BuildPackage,$(PKG_NAME)))

