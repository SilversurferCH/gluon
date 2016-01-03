include $(TOPDIR)/rules.mk

PKG_NAME:=gluon-mesh-batman-adv-core
PKG_VERSION:=1

PKG_BUILD_DIR := $(BUILD_DIR)/$(PKG_NAME)
PKG_BUILD_DEPENDS := respondd

include $(GLUONDIR)/include/package.mk

define Package/gluon-mesh-batman-adv-core
  SECTION:=gluon
  CATEGORY:=Gluon
  TITLE:=Support for batman-adv meshing (core)
  DEPENDS:=+gluon-core +libgluon +gluon-client-bridge +firewall +libiwinfo +batman-adv-visdata
endef

define Build/Prepare
	mkdir -p $(PKG_BUILD_DIR)
	$(CP) ./src/* $(PKG_BUILD_DIR)/
endef

define Package/gluon-mesh-batman-adv-core/install
	$(CP) ./files/* $(1)/

	$(INSTALL_DIR) $(1)/lib/gluon/announce
	$(CP) $(PKG_BUILD_DIR)/announce.so $(1)/lib/gluon/announce/mesh-batman-adv-core.so
endef

define Package/gluon-mesh-batman-adv-core/postinst
#!/bin/sh
$(call GluonCheckSite,check_site.lua)
endef


$(eval $(call BuildPackage,gluon-mesh-batman-adv-core))
