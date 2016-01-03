include $(TOPDIR)/rules.mk

PKG_NAME:=gluon-announce
PKG_VERSION:=1
PKG_RELEASE:=1

PKG_BUILD_DIR := $(BUILD_DIR)/$(PKG_NAME)
PKG_BUILD_DEPENDS := respondd

include $(INCLUDE_DIR)/package.mk

define Package/gluon-announce
  SECTION:=gluon
  CATEGORY:=Gluon
  DEPENDS:=+gluon-core +libplatforminfo +libgluon
  TITLE:=Lua scripts announcing various information
endef

define Build/Prepare
	mkdir -p $(PKG_BUILD_DIR)
	$(CP) ./src/* $(PKG_BUILD_DIR)/
endef

define Package/gluon-announce/install
	$(CP) ./files/* $(1)/

	$(INSTALL_DIR) $(1)/lib/gluon/announce
	$(CP) $(PKG_BUILD_DIR)/announce.so $(1)/lib/gluon/announce/announce.so
endef

$(eval $(call BuildPackage,gluon-announce))
