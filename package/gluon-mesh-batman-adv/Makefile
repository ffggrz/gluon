include $(TOPDIR)/rules.mk

PKG_NAME:=gluon-mesh-batman-adv
PKG_VERSION:=1

include ../gluon.mk

define Package/gluon-mesh-batman-adv-common
  TITLE:=Gluon scripts for batman-adv and batman-adv-legacy
  DEPENDS:= \
	+gluon-core \
	+libgluonutil \
	+gluon-client-bridge \
	+gluon-ebtables \
	+firewall \
	+libiwinfo \
	+kmod-dummy \
	+libnl-tiny \
	+libbatadv \
	+batctl \
	+@GLUON_SPECIALIZE_KERNEL:KERNEL_DUMMY \
	+@GLUON_SPECIALIZE_KERNEL:KERNEL_CRC16 \
	+@GLUON_SPECIALIZE_KERNEL:KERNEL_LIBCRC32C
endef

define Package/gluon-mesh-batman-adv-14
  PROVIDES:=gluon-mesh-batman-adv
  TITLE:=Support for batman-adv meshing (compat level 14)
  DEPENDS+= \
	+gluon-mesh-batman-adv-common \
	+kmod-batman-adv-legacy
endef

define Package/gluon-mesh-batman-adv-15
  PROVIDES:=gluon-mesh-batman-adv
  TITLE:=Support for batman-adv meshing (compat level 15)
  DEPENDS+= \
	+gluon-mesh-batman-adv-common \
	+kmod-batman-adv
endef

define Package/gluon-mesh-batman-adv-common/install
	$(Gluon/Build/Install)
endef

define Package/gluon-mesh-batman-adv-14/install
	$(INSTALL_DIR) $(1)/lib/gluon/mesh-batman-adv
	touch $(1)/lib/gluon/mesh-batman-adv/compat-14
endef
#
define Package/gluon-mesh-batman-adv-15/install
	$(INSTALL_DIR) $(1)/lib/gluon/mesh-batman-adv
	touch $(1)/lib/gluon/mesh-batman-adv/compat-15
endef

$(eval $(call BuildPackageGluon,gluon-mesh-batman-adv-common))
$(eval $(call BuildPackageGluon,gluon-mesh-batman-adv-14))
$(eval $(call BuildPackageGluon,gluon-mesh-batman-adv-15))
