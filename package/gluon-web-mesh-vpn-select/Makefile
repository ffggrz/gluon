include $(TOPDIR)/rules.mk

PKG_NAME:=gluon-web-mesh-vpn-select
PKG_VERSION:=1
PKG_RELEASE:=1

include ../gluon.mk

define Package/gluon-web-mesh-vpn-select
  TITLE:=gluon-web module to select the type of mesh VPN
  DEPENDS:=+gluon-web-admin +gluon-mesh-vpn-fastd +gluon-mesh-vpn-tunneldigger
endef

$(eval $(call BuildPackageGluon,gluon-web-mesh-vpn-select))
