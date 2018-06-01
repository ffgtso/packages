include $(TOPDIR)/rules.mk

PKG_NAME:=l3roamd
PKG_SOURCE_DATE:=2018-06-22
PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL=https://github.com/freifunk-gluon/l3roamd.git
PKG_SOURCE_VERSION:=87052d0e262e9cb2ebc975beb87279e5d7c89c59

CMAKE_OPTIONS += -DCMAKE_BUILD_TYPE:STRING=MINSIZEREL
#CMAKE_OPTIONS += -DCMAKE_BUILD_TYPE:STRING=Debug

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/cmake.mk

define Package/l3roamd
  SECTION:=net
  CATEGORY:=Network
  TITLE:=The layer 3 roaming daemon
  DEPENDS:=+libnl-tiny +kmod-tun +librt +libjson-c
endef

define Package/l3roamd/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/src/l3roamd $(1)/usr/sbin/
endef

$(eval $(call BuildPackage,l3roamd))
