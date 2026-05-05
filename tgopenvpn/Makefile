include $(TOPDIR)/rules.mk

PKG_NAME:=tgopenvpn
PKG_VERSION:=25.050.05753
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/torguardvpn/tgopenvpn.git
PKG_SOURCE_VERSION:=4b42dac782df7b656740cbe262b27d66e95350f1
PKG_MIRROR_HASH:=skip

include $(INCLUDE_DIR)/package.mk

define Package/tgopenvpn
  SECTION:=luci
  CATEGORY:=LuCI
  SUBMENU:=7. TorGuard
  TITLE:=LuCI support for TorGuard OpenVPN
  DEPENDS:=+openvpn-openssl +luci-lua-runtime
  PKGARCH:=all
endef

define Package/tgopenvpn/description
  LuCI configuration interface for TorGuard OpenVPN.
endef

define Package/tgopenvpn/conffiles
/etc/config/tgopenvpn_cfg
endef

define Build/Compile
endef

define Package/tgopenvpn/install
	$(INSTALL_DIR) $(1)/usr/lib/lua/luci
	$(CP) $(PKG_BUILD_DIR)/luasrc/* $(1)/usr/lib/lua/luci/
	$(CP) $(PKG_BUILD_DIR)/root/* $(1)/
endef

$(eval $(call BuildPackage,$(PKG_NAME)))
