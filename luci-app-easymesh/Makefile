include $(TOPDIR)/rules.mk

PKG_NAME:=luci-app-easymesh
PKG_VERSION:=3.8.17
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/torguardvpn/luci-app-easymesh.git
PKG_SOURCE_VERSION:=fe1999e6c3391fa4a1862dbef3755e97b4491e15
PKG_MIRROR_HASH:=3ac6de6c1282335b98f2631a8e8a7382418d493d58a37321bb6a4fc5c92f48d0

PKG_MAINTAINER:=TorGuard <admin@torguard.net>

include $(INCLUDE_DIR)/package.mk

define Package/luci-app-easymesh
  SECTION:=luci
  CATEGORY:=LuCI
  SUBMENU:=3. Applications
  TITLE:=LuCI Support for EasyMesh
  DEPENDS:=+kmod-cfg80211 +batctl-default +kmod-batman-adv +bash +luci-lua-runtime +luci-compat +libiwinfo-lua +luci-proto-batman-adv
  PKGARCH:=all
endef

define Package/luci-app-easymesh/description
  LuCI interface for configuring 802.11s mesh networking with batman-adv.
endef

define Build/Compile
endef

define Package/luci-app-easymesh/install
	$(INSTALL_DIR) $(1)/usr/lib/lua/luci
	$(CP) $(PKG_BUILD_DIR)/luasrc/* $(1)/usr/lib/lua/luci/
	$(CP) $(PKG_BUILD_DIR)/root/* $(1)/
endef

$(eval $(call BuildPackage,$(PKG_NAME)))
