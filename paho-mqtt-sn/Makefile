include $(TOPDIR)/rules.mk

PKG_NAME:=paho-mqtt-sn
PKG_VERSION:=2019-01-16
PKG_RELEASE=$(PKG_SOURCE_VERSION)

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.bz2
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_URL:=https://github.com/pszkotak/paho.mqtt-sn.embedded-c.git
PKG_SOURCE_PROTO:=git
PKG_SOURCE_VERSION:=e2df5c432f3b0d93fc6da238891903c9d8ee2236
PKG_USE_MIPS16:=0
PKG_LICENSE:=EDL

include $(INCLUDE_DIR)/package.mk

define Package/paho-mqtt-sn
	SECTION:=net
	CATEGORY:=Network
	DEPENDS:=+libopenssl +libstdcpp
	TITLE:=paho
endef

define Package/paho-mqtt-sn/description
	MQTT-SN gateway provided by the Eclipse Paho.
endef

define Build/Configure
	$(call Build/Configure/Default)
endef

MAKE_PATH:=MQTTSNGateway

define Build/Compile
	$(call Build/Compile/Default)
endef

define Package/paho-mqtt-sn/install
	$(INSTALL_DIR) $(1)/usr/bin/
	$(INSTALL_DIR) $(1)/etc/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/$(MAKE_PATH)/Build/MQTT-SNGateway $(1)/usr/bin/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/$(MAKE_PATH)/Build/MQTT-SNLogmonitor $(1)/usr/bin/
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/$(MAKE_PATH)/gateway.conf $(1)/etc/paho-mqtt-sn-gateway.conf
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/$(MAKE_PATH)/clients.conf $(1)/etc/paho-mqtt-sn-clients.conf
endef

$(eval $(call BuildPackage,paho-mqtt-sn))
