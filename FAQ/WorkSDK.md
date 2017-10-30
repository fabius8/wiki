[[_TOC_]]

# 工作划分
## patch3 文本修改
### changes_data_src_patch3.diff

#### [Data]
```
+++ make.common	2016-11-08 15:13:25.000000000 -0800
+++ hostTools/scripts/defconfig-bcm.template	2016-11-08 15:14:04.000000000 -0800
+++ hostTools/scripts/gendefconfig.d/15general.conf	2016-11-08 15:14:04.000000000 -0800
+++ hostTools/scripts/gendefconfig.d/20usbhost.conf	2016-11-08 15:13:22.000000000 -0800
+++ bcmdrivers/opensource/char/rdpa_gpl/impl1/include/rdpa_dhd_helper_basic.h	2016-11-08 15:14:28.000000000 -0800 [rdpa_gpl D]
+++ bcmdrivers/opensource/char/rdpa_gpl/impl1/include/rdpa_ucast.h	2016-11-08 15:14:28.000000000 -0800
+++ bcmdrivers/opensource/char/rdpa_gpl/impl1/include/autogen/rdpa_ag_egress_tm.h	2016-11-08 15:14:28.000000000 -0800
+++ bcmdrivers/opensource/char/rdpa_gpl/impl1/include/autogen/rdpa_ag_l2_ucast.h	2016-11-08 15:14:28.000000000 -0800
+++ bcmdrivers/opensource/char/rdpa_gpl/impl1/include/autogen/rdpa_ag_dhd_helper.h	2016-11-08 15:14:28.000000000 -0800
+++ bcmdrivers/opensource/net/enet/impl5/bcmgmac.c	2016-11-08 15:13:18.000000000 -0800  [enet D]
+++ bcmdrivers/opensource/net/enet/impl5/bcmsw.c	2016-11-08 15:13:18.000000000 -0800
+++ bcmdrivers/opensource/net/enet/impl5/bcmenet.c	2016-11-08 15:13:18.000000000 -0800
+++ bcmdrivers/opensource/net/enet/shared/bcmenet_dma_inline.h	2016-11-08 15:13:18.000000000 -0800
+++ bcmdrivers/broadcom/char/pktrunner/impl2/pktrunner_host.c	2016-11-08 15:13:05.000000000 -0800 [pktrunner D]
+++ bcmdrivers/broadcom/char/pktrunner/impl2/pktrunner_host.h	2016-11-08 15:13:05.000000000 -0800
+++ bcmdrivers/broadcom/char/pktrunner/impl2/Makefile	2016-11-08 15:13:05.000000000 -0800  [rdpa D]
+++ bcmdrivers/broadcom/char/rdpa/impl1/rdpa_int.h	2016-11-08 15:14:28.000000000 -0800
+++ bcmdrivers/broadcom/char/rdpa/impl1/rdpa_ucast.c	2016-11-08 15:14:28.000000000 -0800
+++ bcmdrivers/broadcom/char/rdpa/impl1/rdpa_dhd_helper.c	2016-11-08 15:14:28.000000000 -0800
+++ bcmdrivers/broadcom/char/rdpa/impl1/platform/dsl/rdpa_system_hw_cfg.c	2016-11-08 15:14:28.000000000 -0800
+++ bcmdrivers/broadcom/char/pktflow/impl1/fcachehw.c	2016-11-08 15:13:05.000000000 -0800  [pktflow D]
+++ bcmdrivers/broadcom/char/pktflow/impl1/fcachedrv.c	2016-11-08 15:13:05.000000000 -0800
+++ shared/opensource/drv/dpi/bcm63138_data_path_init.c	2016-11-08 15:14:28.000000000 -0800   [D]
+++ shared/broadcom/rdp/impl2/rdd/rdd_legacy_conv.h	2016-11-08 15:14:28.000000000 -0800  [rdp D]
+++ shared/broadcom/rdp/impl2/rdd/rdd_dhd_helper.c	2016-11-08 15:14:27.000000000 -0800
+++ shared/broadcom/rdp/impl2/rdd/rdd_dhd_helper.h	2016-11-08 15:14:27.000000000 -0800
+++ shared/broadcom/rdp/impl2/rdd/rdd_runner_defs_auto.h	2016-11-08 15:14:28.000000000 -0800
+++ shared/broadcom/rdp/impl2/rdd/rdd_init.c	2016-11-08 15:14:28.000000000 -0800
+++ shared/broadcom/rdp/impl2/rdd/dhd_defs.h	2016-11-08 15:14:27.000000000 -0800
+++ shared/broadcom/rdp/impl2/rdd/rdd_common.c	2016-11-08 15:14:28.000000000 -0800
+++ shared/broadcom/rdp/impl2/rdd/rdd_runner_defs.h	2016-11-08 15:14:28.000000000 -0800
+++ shared/broadcom/rdp/impl2/rdd/rdd_common.h	2016-11-08 15:14:28.000000000 -0800
+++ shared/broadcom/rdp/impl2/rdd/rdd_data_structures_auto.h	2016-11-08 15:14:28.000000000 -0800
+++ shared/broadcom/rdp/impl2/rdd/rdd_init.h	2016-11-08 15:14:28.000000000 -0800
+++ shared/broadcom/rdp/impl2/rdd/generated/dsl_63148/rdd_runner_reg_dump.h	2016-11-08 15:14:28.000000000 -0800
+++ shared/broadcom/rdp/impl2/rdd/generated/dsl_63148/rdd_runner_c_labels.h	2016-11-08 15:14:28.000000000 -0800
+++ shared/broadcom/rdp/impl2/rdd/generated/dsl_63148/rdd_runner_reg_dump.c	2016-11-08 15:14:28.000000000 -0800
+++ shared/broadcom/rdp/impl2/rdd/generated/dsl_63148/rdd_runner_reg_dump_addrs.c	2016-11-08 15:14:28.000000000 -0800
+++ shared/broadcom/rdp/impl2/rdd/generated/dsl_63148/rdd_runner_reg_dump_addrs.h	2016-11-08 15:14:28.000000000 -0800
+++ shared/broadcom/rdp/impl2/rdd/generated/dsl_63148/rdd_runner_d_labels.h	2016-11-08 15:14:28.000000000 -0800
+++ shared/broadcom/rdp/impl2/rdd/generated/dsl_63148/rdd_runner_a_labels.h	2016-11-08 15:14:28.000000000 -0800
+++ shared/broadcom/rdp/impl2/rdd/generated/dsl_63138/rdd_runner_reg_dump.h	2016-11-08 15:14:28.000000000 -0800
+++ shared/broadcom/rdp/impl2/rdd/generated/dsl_63138/rdd_runner_c_labels.h	2016-11-08 15:14:28.000000000 -0800
+++ shared/broadcom/rdp/impl2/rdd/generated/dsl_63138/rdd_runner_reg_dump.c	2016-11-08 15:14:28.000000000 -0800
+++ shared/broadcom/rdp/impl2/rdd/generated/dsl_63138/rdd_runner_reg_dump_addrs.c	2016-11-08 15:14:28.000000000 -0800
+++ shared/broadcom/rdp/impl2/rdd/generated/dsl_63138/rdd_runner_reg_dump_addrs.h	2016-11-08 15:14:28.000000000 -0800
+++ shared/broadcom/rdp/impl2/rdd/generated/dsl_63138/rdd_runner_d_labels.h	2016-11-08 15:14:28.000000000 -0800
+++ shared/broadcom/rdp/impl2/rdd/generated/dsl_63138/rdd_runner_a_labels.h	2016-11-08 15:14:28.000000000 -0800
+++ shared/broadcom/rdp/impl1/rdd/rdd_dhd_helper.c	2016-11-08 15:14:27.000000000 -0800
+++ shared/broadcom/rdp/impl1/rdd/rdd_data_structures.h	2016-11-08 15:14:28.000000000 -0800
+++ shared/broadcom/rdp/impl1/rdd/rdd_dhd_helper.h	2016-11-08 15:14:27.000000000 -0800
+++ shared/broadcom/rdp/impl1/rdd/rdd_init.c	2016-11-08 15:14:28.000000000 -0800
+++ shared/broadcom/rdp/impl1/rdd/dhd_defs.h	2016-11-08 15:14:27.000000000 -0800
+++ shared/broadcom/rdp/impl1/rdd/rdd_common.c	2016-11-08 15:14:28.000000000 -0800
+++ shared/broadcom/rdp/impl1/rdd/rdd_cpu.h	2016-11-08 15:14:28.000000000 -0800
+++ kernel/linux-3.4rt/include/net/netfilter/nf_conntrack_extend.h	2016-11-08 15:13:24.000000000 -0800 [D]
+++ kernel/linux-3.4rt/net/ipv4/tcp_input.c	2016-11-08 15:13:24.000000000 -0800  [net D]
+++ kernel/linux-3.4rt/net/ipv4/netfilter/nf_conntrack_l3proto_ipv4_compat.c	2016-11-08 15:13:24.000000000 -0800
+++ kernel/linux-3.4rt/net/core/dev.c	2016-11-08 15:13:54.000000000 -0800
+++ kernel/linux-3.4rt/net/core/blog.c	2016-11-08 15:13:24.000000000 -0800
+++ kernel/linux-3.4rt/net/ipv6/netfilter.c	2016-11-08 15:13:24.000000000 -0800
+++ kernel/linux-3.4rt/net/netfilter/nf_conntrack_core.c	2016-11-08 15:13:54.000000000 -0800
+++ kernel/linux-3.4rt/net/netfilter/nf_conntrack_proto_udp.c	2016-11-08 15:13:24.000000000 -0800
+++ kernel/linux-3.4rt/net/bridge/br_input.c	2016-11-08 15:13:24.000000000 -0800
+++ targets/config.in	2016-11-08 15:14:04.000000000 -0800
+++ targets/963148BGW/963148BGW	2016-11-08 15:14:04.000000000 -0800
+++ targets/963138GW/963138GW	2016-11-08 15:24:05.000000000 -0800
+++ targets/963148GW/963148GW	2016-11-08 15:14:04.000000000 -0800
+++ targets/96318GW/96318GW	2016-11-08 15:14:04.000000000 -0800
+++ targets/963381GW/963381GW	2016-11-08 15:14:04.000000000 -0800
+++ targets/963138BGW/963138BGW	2016-11-08 15:14:04.000000000 -0800
+++ targets/arch/GFAST.arch	2016-11-08 15:13:30.000000000 -0800
+++ targets/96328GW/96328GW	2016-11-08 15:14:04.000000000 -0800
+++ targets/963268B5GW/963268B5GW	2016-11-08 15:14:04.000000000 -0800
+++ targets/963268GW/963268GW	2016-11-08 15:14:04.000000000 -0800
+++ targets/96362GW/96362GW	2016-11-08 15:14:04.000000000 -0800

```

#### [Platform]
```
+++ bcmdrivers/opensource/include/bcm963xx/bcmdpi.h	2016-11-08 15:13:17.000000000 -0800   [P]
+++ bcmdrivers/opensource/char/dpi/impl1/dpi.c	2016-11-08 15:13:17.000000000 -0800    [P]
+++ bcmdrivers/opensource/char/board/bcm963xx/impl1/board.c	2016-11-08 15:13:17.000000000 -0800  [P&D]
+++ bcmdrivers/opensource/char/spudd/impl2/spu.h	2016-11-08 15:13:17.000000000 -0800 [spudd P]
+++ bcmdrivers/opensource/char/spudd/impl2/spudrv.c	2016-11-08 15:13:17.000000000 -0800
+++ bcmdrivers/opensource/char/spudd/impl2/linux/spu_hash.c	2016-11-08 15:13:17.000000000 -0800
+++ bcmdrivers/opensource/char/spudd/impl2/linux/spu.c	2016-11-08 15:13:17.000000000 -0800
+++ shared/opensource/include/bcm963xx/63268_map_part.h	2016-11-08 15:13:30.000000000 -0800   [P]
+++ shared/opensource/include/bcm963xx/6318_map_part.h	2016-11-08 15:13:30.000000000 -0800  [P]
+++ shared/opensource/flash/spinandflash.c	2016-11-08 15:13:30.000000000 -0800   [P]
+++ shared/opensource/include/bcm963xx/boardparms.h	2016-11-08 15:13:30.000000000 -0800
+++ shared/opensource/boardparms/bcm963xx/boardparms.c	2016-11-08 15:13:30.000000000 -0800  [P]
+++ shared/opensource/boardparms/bcm963xx/bp_funcs.c	2016-11-08 15:13:30.000000000 -0800   [P]
+++ kernel/linux-3.4rt/Kconfig.bcm	2016-11-08 15:14:04.000000000 -0800   [P begin]
+++ kernel/linux-3.4rt/drivers/usb/host/xhci.h	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/host/xhci-ring.c	2016-11-08 15:13:23.000000000 -0800
+++ kernel/linux-3.4rt/drivers/usb/host/pci-quirks.h	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/host/ohci-pci.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/host/ehci-q.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/host/xhci-mem.c	2016-11-08 15:13:23.000000000 -0800
+++ kernel/linux-3.4rt/drivers/usb/host/xhci-plat.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/host/ehci-hcd.c	2016-11-08 15:13:23.000000000 -0800
+++ kernel/linux-3.4rt/drivers/usb/host/ohci-hcd.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/host/xhci-pci.c	2016-11-08 15:13:23.000000000 -0800
+++ kernel/linux-3.4rt/drivers/usb/host/pci-quirks.c	2016-11-08 15:13:23.000000000 -0800
+++ kernel/linux-3.4rt/drivers/usb/host/ohci-at91.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/host/ehci-mxc.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/host/ehci-hub.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/host/isp1760-hcd.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/host/ohci-q.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/host/ehci-pci.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/host/uhci-hcd.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/host/xhci.c	2016-11-08 15:13:23.000000000 -0800
+++ kernel/linux-3.4rt/drivers/usb/host/xhci-hub.c	2016-11-08 15:13:23.000000000 -0800
+++ kernel/linux-3.4rt/drivers/usb/host/ehci-omap.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/host/uhci-pci.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/host/ehci-sched.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/host/uhci-hub.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/host/ehci-sysfs.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/renesas_usbhs/mod_gadget.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/core/devio.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/core/hcd-pci.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/core/otg_whitelist.h	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/core/inode.c	2016-11-08 15:13:23.000000000 -0800
+++ kernel/linux-3.4rt/drivers/usb/core/usb.h	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/core/hcd.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/core/config.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/core/message.c	2016-11-08 15:13:23.000000000 -0800
+++ kernel/linux-3.4rt/drivers/usb/core/hub.c	2016-11-08 15:13:23.000000000 -0800
+++ kernel/linux-3.4rt/drivers/usb/core/quirks.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/core/usb.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/core/buffer.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/core/driver.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/core/devices.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/misc/appledisplay.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/misc/adutux.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/misc/usbtest.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/misc/sisusbvga/sisusb.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/otg/otg_fsm.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/otg/Makefile	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/otg/Kconfig	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/musb/musb_gadget.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/musb/musb_core.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/musb/cppi_dma.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/gadget/dummy_hcd.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/gadget/at91_udc.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/gadget/udc-core.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/gadget/f_ecm.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/gadget/ci13xxx_udc.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/gadget/u_ether.h	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/gadget/f_midi.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/gadget/f_fs.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/gadget/f_rndis.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/gadget/inode.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/gadget/rndis.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/gadget/f_ncm.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/gadget/u_ether.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/gadget/composite.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/gadget/Makefile	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/gadget/Kconfig	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/gadget/f_eem.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/gadget/f_subset.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/gadget/f_mass_storage.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/gadget/u_serial.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/gadget/f_phonet.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/gadget/f_uvc.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/storage/unusual_cypress.h	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/storage/usual-tables.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/storage/transport.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/storage/scsiglue.c	2016-11-08 15:13:23.000000000 -0800
+++ kernel/linux-3.4rt/drivers/usb/storage/shuttle_usbat.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/storage/unusual_devs.h	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/storage/usb.c	2016-11-08 15:13:23.000000000 -0800
+++ kernel/linux-3.4rt/drivers/usb/storage/Kconfig	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/storage/cypress_atacb.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/atm/cxacru.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/wusbcore/wa-rpipe.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/wusbcore/wa-xfer.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/serial/ti_usb_3410_5052.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/serial/generic.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/serial/pl2303.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/serial/mos7840.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/serial/option.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/serial/mct_u232.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/serial/ark3116.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/serial/whiteheat.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/serial/cypress_m8.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/serial/iuu_phoenix.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/serial/ch341.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/serial/qcaux.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/serial/cp210x.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/serial/console.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/serial/qcserial.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/serial/oti6858.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/serial/ti_usb_3410_5052.h	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/serial/cypress_m8.h	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/serial/usb_wwan.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/serial/pl2303.h	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/serial/bus.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/serial/sierra.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/serial/ftdi_sio_ids.h	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/serial/io_usbvend.h	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/serial/ftdi_sio.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/serial/keyspan.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/serial/io_edgeport.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/serial/opticon.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/serial/garmin_gps.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/serial/spcp8x5.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/serial/usb-serial.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/serial/kobil_sct.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/serial/io_ti.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/serial/mos7720.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/serial/ssu100.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/serial/visor.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/class/cdc-wdm.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/class/cdc-acm.h	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/class/cdc-acm.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/dwc3/gadget.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/dwc3/ep0.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/dwc3/core.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/dwc3/core.h	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/dwc3/dwc3-pci.c	2016-07-06 16:17:06.000000000 -0700
+++ kernel/linux-3.4rt/drivers/usb/dwc3/gadget.h	2016-07-06 16:17:06.000000000 -0700 [P end]
+++ kernel/linux-3.4rt/drivers/mtd/brcmnand/brcmnand_bbt.c	2016-11-08 15:13:23.000000000 -0800 [mtd P]
+++ kernel/linux-3.4rt/drivers/mtd/nand/nand_ids.c	2016-11-08 15:13:23.000000000 -0800
+++ kernel/linux-3.4rt/drivers/mtd/nand/bcm63xx_spinand.c	2016-11-08 15:13:23.000000000 -0800
+++ kernel/linux-3.4rt/drivers/scsi/sd.c	2016-11-08 15:13:23.000000000 -0800 [P]
+++ kernel/linux-3.4rt/drivers/net/usb/usbnet.c	2016-11-08 15:13:23.000000000 -0800 [P]
+++ kernel/linux-3.4rt/fs/internal.h	2016-11-08 15:13:23.000000000 -0800  [FS P]
+++ kernel/linux-3.4rt/fs/namei.c	2016-11-08 15:13:23.000000000 -0800
+++ kernel/linux-3.4rt/fs/super.c	2016-11-08 15:13:23.000000000 -0800
+++ kernel/linux-3.4rt/fs/exec.c	2016-11-08 15:13:23.000000000 -0800
+++ kernel/linux-3.4rt/fs/open.c	2016-11-08 15:13:23.000000000 -0800
+++ kernel/linux-3.4rt/fs/file_table.c	2016-11-08 15:13:23.000000000 -0800
+++ kernel/linux-3.4rt/arch/arm/plat-bcm63xx/Makefile	2016-11-08 15:13:22.000000000 -0800  [arch P]
+++ kernel/linux-3.4rt/arch/arm/plat-bcm63xx/bcm63xx_usb.c	2016-11-08 15:13:22.000000000 -0800
+++ kernel/linux-3.4rt/mm/memory.c	2016-11-30 22:06:08.000000000 -0800 [P]
+++ kernel/linux-3.4rt/include/linux/mm.h	2016-10-31 21:32:33.000000000 -0700 [P begin]
+++ kernel/linux-3.4rt/include/linux/blog.h	2016-11-08 15:13:23.000000000 -0800
+++ kernel/linux-3.4rt/include/linux/usb.h	2016-09-08 14:46:06.000000000 -0700
+++ kernel/linux-3.4rt/include/linux/fs.h	2016-11-08 15:13:23.000000000 -0800
+++ kernel/linux-3.4rt/include/linux/usb_usual.h	2016-07-06 16:23:36.000000000 -0700
+++ kernel/linux-3.4rt/include/linux/bcm_realtime.h	2016-11-08 15:13:23.000000000 -0800
+++ kernel/linux-3.4rt/include/linux/usb/serial.h	2016-07-06 16:17:44.000000000 -0700
+++ kernel/linux-3.4rt/include/linux/usb/hcd.h	2016-07-06 16:17:44.000000000 -0700
+++ kernel/linux-3.4rt/include/linux/usb/ch9.h	2016-07-06 16:17:44.000000000 -0700
+++ kernel/linux-3.4rt/include/linux/usb/audio.h	2016-07-06 16:17:44.000000000 -0700
+++ kernel/linux-3.4rt/include/linux/usb/quirks.h	2016-07-06 16:17:44.000000000 -0700
+++ kernel/linux-3.4rt/include/scsi/scsi_device.h	2016-07-06 16:26:54.000000000 -0700 [P end]
+++ kernel/linux-3.4rt/ipc/util.c	2016-11-08 15:13:24.000000000 -0800 [P]
+++ kernel/linux-3.4rt/ipc/shm.c	2016-11-08 15:13:24.000000000 -0800
+++ kernel/linux-3.4rt/ipc/msg.c	2016-11-08 15:13:24.000000000 -0800

```

#### [DSL]
```
+++ bcmdrivers/opensource/net/xtmrt/impl5/xtmrt_runner.c	2016-11-08 15:13:18.000000000 -0800 [xtmrt ??]
+++ bcmdrivers/opensource/net/xtmrt/impl5/bcmxtmrt.c	2016-11-08 15:13:18.000000000 -0800
+++ bcmdrivers/opensource/net/xtmrt/impl5/xtmrt_dma.h	2016-11-08 15:13:18.000000000 -0800
+++ bcmdrivers/opensource/net/xtmrt/impl5/xtmrt_runner.h	2016-11-08 15:13:18.000000000 -0800
+++ bcmdrivers/opensource/net/xtmrt/impl5/xtmrt_dma.c	2016-11-08 15:13:18.000000000 -0800
+++ bcmdrivers/opensource/net/xtmrt/impl5/bcmxtmrtbond.c	2016-11-08 15:13:18.000000000 -0800
+++ bcmdrivers/broadcom/include/bcm963xx/AdslMibDef.h	2016-11-08 15:13:06.000000000 -0800
+++ bcmdrivers/broadcom/char/bpm/impl1/bpm.c	2016-11-08 15:13:04.000000000 -0800
+++ bcmdrivers/broadcom/char/xtmcfg/impl2/xtmconnection.cpp	2016-11-08 15:13:06.000000000 -0800   [xtmcfg DSL]
+++ bcmdrivers/broadcom/char/xtmcfg/impl2/xtmautosense.cpp	2016-11-08 15:13:06.000000000 -0800
+++ bcmdrivers/broadcom/char/xtmcfg/impl2/xtmcfgimpl.h	2016-11-08 15:13:06.000000000 -0800
+++ bcmdrivers/broadcom/char/xtmcfg/impl2/xtmcfgmain.cpp	2016-11-08 15:13:06.000000000 -0800
+++ bcmdrivers/broadcom/char/xtmcfg/impl2/xtmoslinux.c	2016-11-08 15:13:06.000000000 -0800
+++ bcmdrivers/broadcom/char/xtmcfg/impl2/xtmprocessor.cpp	2016-11-08 15:13:06.000000000 -0800
+++ bcmdrivers/broadcom/char/adsl/impl1/adsl.c	2016-11-08 15:13:04.000000000 -0800           [adsl DSL]
+++ bcmdrivers/broadcom/char/adsl/impl1/BcmAdslCore.c	2016-11-08 15:13:04.000000000 -0800
+++ bcmdrivers/broadcom/char/adsl/impl1/AdslCore.c	2016-11-08 15:13:04.000000000 -0800
+++ bcmdrivers/broadcom/char/adsl/impl1/BcmAdslDiagLinux.c	2016-11-08 15:13:04.000000000 -0800
+++ bcmdrivers/broadcom/char/adsl/impl1/BcmOs.c	2016-11-08 15:13:04.000000000 -0800
+++ bcmdrivers/broadcom/char/adsl/impl1/BcmOs.h	2016-11-08 15:13:04.000000000 -0800
+++ bcmdrivers/broadcom/char/adsl/impl1/AdslSelfTest.c	2016-11-08 15:13:04.000000000 -0800
+++ bcmdrivers/broadcom/char/adsl/impl1/AdslDrvVersion.h	2016-11-08 15:13:04.000000000 -0800
+++ bcmdrivers/broadcom/char/adsl/impl1/BcmAdslCore.h	2016-11-08 15:13:04.000000000 -0800
+++ bcmdrivers/broadcom/char/adsl/impl1/BcmAdslDiagCommon.c	2016-11-08 15:13:04.000000000 -0800
+++ bcmdrivers/broadcom/char/adsl/impl1/AdslPhyBld.c	2016-11-08 15:13:04.000000000 -0800
+++ bcmdrivers/broadcom/char/adsl/impl1/AdslCore.h	2016-11-08 15:13:04.000000000 -0800
+++ bcmdrivers/broadcom/char/adsl/impl1/AdslFile.c	2016-11-08 15:13:04.000000000 -0800
+++ bcmdrivers/broadcom/char/adsl/impl1/Makefile	2016-11-08 15:14:22.000000000 -0800
+++ bcmdrivers/broadcom/char/adsl/impl1/adsldrv.c	2016-11-08 15:13:04.000000000 -0800
+++ bcmdrivers/broadcom/char/adsl/impl1/adslcore63138/adsl_defs.h	2016-11-08 15:13:04.000000000 -0800
+++ bcmdrivers/broadcom/char/adsl/impl1/adslcore63138/adsl_lmem.h	2016-11-08 15:13:04.000000000 -0800
+++ bcmdrivers/broadcom/char/adsl/impl1/adslcore63138/adsl_sdram.h	2016-11-08 15:13:04.000000000 -0800
+++ bcmdrivers/broadcom/char/adsl/impl1/softdsl/SoftDslG993p2.h	2016-11-08 15:13:04.000000000 -0800
+++ bcmdrivers/broadcom/char/adsl/impl1/softdsl/SoftDsl.h	2016-11-08 15:13:04.000000000 -0800
+++ bcmdrivers/broadcom/char/adsl/impl1/softdsl/SoftModemTypes.h	2016-11-08 15:13:04.000000000 -0800
+++ bcmdrivers/broadcom/char/adsl/impl1/softdsl/AdslMib.c	2016-11-08 15:13:04.000000000 -0800
+++ bcmdrivers/broadcom/char/adsl/impl1/softdsl/BlockUtil.c	2016-11-08 15:13:04.000000000 -0800
+++ bcmdrivers/broadcom/char/adsl/impl1/softdsl/G992p3OvhMsg.c	2016-11-08 15:13:04.000000000 -0800
+++ bcmdrivers/broadcom/char/adsl/impl1/softdsl/AdslMib.h	2016-11-08 15:13:04.000000000 -0800
+++ bcmdrivers/broadcom/char/adsl/impl1/softdsl/AdslMib.gh	2016-11-08 15:13:04.000000000 -0800
+++ bcmdrivers/broadcom/char/adsl/impl1/softdsl/AdslCoreDefs.h	2016-11-08 15:13:04.000000000 -0800
+++ shared/opensource/drivers/bcm_misc_hw_init_impl1.c	2016-11-08 15:13:30.000000000 -0800
+++ shared/opensource/drivers/bcm_ethsw_impl2.c	2016-11-08 15:13:30.000000000 -0800
```

### changes_data_src_patch3_2.diff

#### [Data]
```
+++ bcmdrivers/broadcom/char/pktflow/impl1/fcachedrv.c	2016-11-29 17:01:13.000000000 -0800 [D]
+++ kernel/linux-3.4rt/include/linux/blog.h	2016-11-29 17:01:21.000000000 -0800 [D]
+++ kernel/linux-3.4rt/net/core/blog.c	2016-11-29 17:01:22.000000000 -0800 [D]
```

## patch4 文本修改

### changes_data_src_patch4.diff

#### [Data]
```
+++ hostTools/scripts/defconfig-bcm.template	2017-03-23 00:07:10.000000000 -0700
+++ bcmdrivers/opensource/include/bcm963xx/bcmxtmcfg.h	2017-03-23 00:06:40.000000000 -0700
+++ bcmdrivers/opensource/include/bcm963xx/bcmnet.h	2017-03-23 00:06:40.000000000 -0700
+++ bcmdrivers/opensource/char/rdpa_drv/impl1/rdpa_cmd_drv.c	2017-03-23 00:06:40.000000000 -0700
+++ bcmdrivers/opensource/char/rdpa_drv/impl1/Makefile	2017-03-23 00:06:40.000000000 -0700
+++ bcmdrivers/opensource/char/rdpa_gpl/impl1/include/rdpa_l2_ucast.h	2017-03-23 00:07:33.000000000 -0700
+++ bcmdrivers/opensource/char/rdpa_gpl/impl1/include/rdpa_ip_class_basic.h	2017-03-23 00:07:33.000000000 -0700
+++ bcmdrivers/opensource/char/rdpa_gpl/impl1/include/rdpa_types.h	2017-03-23 00:07:33.000000000 -0700
+++ bcmdrivers/opensource/char/rdpa_gpl/impl1/include/rdpa_cpu.h	2017-03-23 00:07:33.000000000 -0700
+++ bcmdrivers/opensource/char/rdpa_gpl/impl1/include/autogen/rdpa_ag_bridge.h	2017-03-23 00:07:33.000000000 -0700
+++ bcmdrivers/opensource/char/rdpa_gpl/impl1/include/autogen/rdpa_ag_l2_ucast.h	2017-03-23 00:07:33.000000000 -0700
+++ bcmdrivers/opensource/char/rdpa_gpl/impl1/include/autogen/rdpa_ag_ucast.h	2017-03-23 00:07:33.000000000 -0700
+++ bcmdrivers/opensource/char/rdpa_gpl/impl1/include/autogen/rdpa_ag_dhd_helper.h	2017-03-23 00:07:32.000000000 -0700
+++ bcmdrivers/opensource/char/rdpa_gpl/impl1/include/autogen/rdpa_ag_cpu.h	2017-03-23 00:07:33.000000000 -0700
+++ bcmdrivers/opensource/net/enet/impl5/bcmenet_dma.c	2017-03-23 00:06:40.000000000 -0700
+++ bcmdrivers/opensource/net/enet/impl5/bcmenet.c	2017-03-23 00:06:40.000000000 -0700
+++ bcmdrivers/opensource/net/enet/impl5/bcmsw_runner.c	2017-03-23 00:06:40.000000000 -0700
+++ bcmdrivers/opensource/net/enet/impl5/ethsw_phy.c	2017-03-23 00:06:40.000000000 -0700
+++ bcmdrivers/opensource/net/enet/impl5/bcmenet_runner.c	2017-03-23 00:06:40.000000000 -0700
+++ bcmdrivers/opensource/net/enet/shared/bcmenet_runner.h	2017-03-23 00:06:40.000000000 -0700
+++ bcmdrivers/opensource/net/enet/shared/bcmenet_dma_inline.h	2017-03-23 00:06:40.000000000 -0700
+++ bcmdrivers/opensource/net/enet/shared/bcmenet_dma.h	2017-03-23 00:06:40.000000000 -0700
+++ bcmdrivers/opensource/net/enet/shared/bcmenet_runner_inline.h	2017-03-23 00:06:40.000000000 -0700
+++ bcmdrivers/broadcom/char/pktrunner/impl2/pktrunner_proto.c	2017-03-23 00:06:35.000000000 -0700
+++ bcmdrivers/broadcom/char/fap/impl1/fap_mcast.c	2017-03-23 00:06:35.000000000 -0700 [???]
+++ bcmdrivers/broadcom/char/ingqos/impl1/ingqos.c	2017-03-23 00:06:35.000000000 -0700 [ingqos ???]
+++ bcmdrivers/broadcom/char/ingqos/impl1/Makefile	2017-03-23 00:06:35.000000000 -0700
+++ bcmdrivers/broadcom/char/vlan/impl1/bcm_vlan_rule.c	2017-03-23 00:06:35.000000000 -0700
+++ bcmdrivers/broadcom/char/rdpa/impl1/make.proj_flags_DSL_63148	2017-03-23 00:07:33.000000000 -0700
+++ bcmdrivers/broadcom/char/rdpa/impl1/rdpa_rdd_inline.h	2017-03-23 00:07:33.000000000 -0700
+++ bcmdrivers/broadcom/char/rdpa/impl1/rdpa_ucast.c	2017-03-23 00:07:33.000000000 -0700
+++ bcmdrivers/broadcom/char/rdpa/impl1/rdpa_l2_ucast.c	2017-03-23 00:07:33.000000000 -0700
+++ bcmdrivers/broadcom/char/rdpa/impl1/make.proj_flags_DSL_63138	2017-03-23 00:07:33.000000000 -0700
+++ bcmdrivers/broadcom/char/rdpa/impl1/rdpa_types.c	2017-03-23 00:07:33.000000000 -0700
+++ bcmdrivers/broadcom/char/rdpa/impl1/rdpa_cpu.c	2017-03-23 00:07:33.000000000 -0700
+++ bcmdrivers/broadcom/char/rdpa/impl1/rdpa_port.c	2017-03-23 00:07:33.000000000 -0700
+++ bcmdrivers/broadcom/char/rdpa/impl1/platform/dsl/rdpa_system_hw_cfg.c	2017-03-23 00:07:33.000000000 -0700
+++ shared/opensource/include/rdp/rdp_cpu_ring_inline.h	2017-03-23 00:07:32.000000000 -0700
+++ shared/broadcom/rdp/impl2/rdd/rdd_shell.c	2017-03-23 00:07:33.000000000 -0700
+++ shared/broadcom/rdp/impl2/rdd/rdd_data_structures.h	2017-03-23 00:07:33.000000000 -0700
+++ shared/broadcom/rdp/impl2/rdd/rdd_cpu.c	2017-03-23 00:07:33.000000000 -0700
+++ shared/broadcom/rdp/impl2/rdd/rdd_runner_defs_auto.h	2017-03-23 00:07:33.000000000 -0700
+++ shared/broadcom/rdp/impl2/rdd/rdd_router.c	2017-03-23 00:07:33.000000000 -0700
+++ shared/broadcom/rdp/impl2/rdd/rdd_init.c	2017-03-23 00:07:33.000000000 -0700
+++ shared/broadcom/rdp/impl2/rdd/rdd_common.c	2017-03-23 00:07:33.000000000 -0700
+++ shared/broadcom/rdp/impl2/rdd/rdd_cpu.h	2017-03-23 00:07:33.000000000 -0700
+++ shared/broadcom/rdp/impl2/rdd/rdd_runner_defs.h	2017-03-23 00:07:33.000000000 -0700
+++ shared/broadcom/rdp/impl2/rdd/rdd_defs.h	2017-03-23 00:07:33.000000000 -0700
+++ shared/broadcom/rdp/impl2/rdd/rdd_data_structures_auto.h	2017-03-23 00:07:33.000000000 -0700
+++ shared/broadcom/rdp/impl2/rdd/rdd_tm.c	2017-03-23 00:07:33.000000000 -0700
+++ shared/broadcom/rdp/impl2/rdd/rdd_l2_ucast.c	2017-03-23 00:07:33.000000000 -0700
+++ shared/broadcom/rdp/impl2/rdd/rdd_init.h	2017-03-23 00:07:33.000000000 -0700
+++ shared/broadcom/rdp/impl2/rdd/generated/dsl_63148/rdd_runner_reg_dump.h	2017-03-23 00:07:33.000000000 -0700
+++ shared/broadcom/rdp/impl2/rdd/generated/dsl_63148/rdd_runner_b_labels.h	2017-03-23 00:07:33.000000000 -0700
+++ shared/broadcom/rdp/impl2/rdd/generated/dsl_63148/rdd_runner_c_labels.h	2017-03-23 00:07:33.000000000 -0700
+++ shared/broadcom/rdp/impl2/rdd/generated/dsl_63148/rdd_runner_reg_dump.c	2017-03-23 00:07:33.000000000 -0700
+++ shared/broadcom/rdp/impl2/rdd/generated/dsl_63148/rdd_runner_reg_dump_addrs.c	2017-03-23 00:07:33.000000000 -0700
+++ shared/broadcom/rdp/impl2/rdd/generated/dsl_63148/rdd_runner_reg_dump_addrs.h	2017-03-23 00:07:33.000000000 -0700
+++ shared/broadcom/rdp/impl2/rdd/generated/dsl_63148/rdd_runner_d_labels.h	2017-03-23 00:07:33.000000000 -0700
+++ shared/broadcom/rdp/impl2/rdd/generated/dsl_63148/rdd_runner_a_labels.h	2017-03-23 00:07:33.000000000 -0700
+++ shared/broadcom/rdp/impl2/rdd/generated/dsl_63138/rdd_runner_reg_dump.h	2017-03-23 00:07:33.000000000 -0700
+++ shared/broadcom/rdp/impl2/rdd/generated/dsl_63138/rdd_runner_b_labels.h	2017-03-23 00:07:33.000000000 -0700
+++ shared/broadcom/rdp/impl2/rdd/generated/dsl_63138/rdd_runner_c_labels.h	2017-03-23 00:07:33.000000000 -0700
+++ shared/broadcom/rdp/impl2/rdd/generated/dsl_63138/rdd_runner_reg_dump.c	2017-03-23 00:07:33.000000000 -0700
+++ shared/broadcom/rdp/impl2/rdd/generated/dsl_63138/rdd_runner_reg_dump_addrs.c	2017-03-23 00:07:33.000000000 -0700
+++ shared/broadcom/rdp/impl2/rdd/generated/dsl_63138/rdd_runner_reg_dump_addrs.h	2017-03-23 00:07:33.000000000 -0700
+++ shared/broadcom/rdp/impl2/rdd/generated/dsl_63138/rdd_runner_d_labels.h	2017-03-23 00:07:33.000000000 -0700
+++ shared/broadcom/rdp/impl2/rdd/generated/dsl_63138/rdd_runner_a_labels.h	2017-03-23 00:07:33.000000000 -0700
+++ kernel/linux-3.4rt/include/linux/blog.h	2017-03-23 00:06:43.000000000 -0700
+++ kernel/linux-3.4rt/include/linux/iqos.h	2017-03-23 00:06:43.000000000 -0700
+++ kernel/linux-3.4rt/net/core/dev.c	2017-03-23 00:07:03.000000000 -0700
+++ kernel/linux-3.4rt/net/core/blog.c	2017-03-23 00:06:43.000000000 -0700
+++ kernel/linux-3.4rt/net/core/iqos.c	2017-03-23 00:06:43.000000000 -0700
+++ kernel/linux-3.4rt/net/netfilter/nf_conntrack_core.c	2017-03-23 00:07:03.000000000 -0700
+++ kernel/linux-3.4rt/net/netfilter/nf_conntrack_standalone.c	2017-03-23 00:06:43.000000000 -0700
+++ kernel/linux-3.4rt/net/bridge/br_input.c	2017-04-07 16:30:22.000000000 -0700
+++ kernel/linux-3.4rt/net/bridge/br_igmp.c	2017-03-23 00:06:43.000000000 -0700
+++ kernel/linux-3.4rt/net/bridge/br_mcast.c	2017-03-23 00:06:43.000000000 -0700
+++ kernel/linux-3.4rt/net/bridge/br_mld.c	2017-03-23 00:06:43.000000000 -0700
+++ targets/963148BGW/963148BGW	2017-03-23 00:07:10.000000000 -0700
+++ targets/963138GW/963138GW	2017-03-23 00:17:21.000000000 -0700
+++ targets/963148GW/963148GW	2017-03-23 00:07:10.000000000 -0700
+++ targets/963138BGW/963138BGW	2017-03-23 00:07:10.000000000 -0700
+++ targets/arch/NODSL.arch	2017-03-23 00:06:47.000000000 -0700
+++ targets/fs.src/etc/init.d/bcm-base-drivers.list	2017-03-23 00:06:47.000000000 -0700
```

#### [Platform]
```
+++ bcmdrivers/opensource/char/serial/impl1/bcm63xx_cons.c	2017-03-23 00:06:40.000000000 -0700 [P]
+++ kernel/linux-3.4rt/drivers/tty/tty_ldisc.c	2017-03-23 00:06:43.000000000 -0700 [P]
+++ kernel/linux-3.4rt/drivers/net/ppp/ppp_generic.c	2017-03-23 00:06:43.000000000 -0700  [P]
+++ kernel/linux-3.4rt/fs/ioprio.c	2017-03-23 00:06:43.000000000 -0700 [P]
+++ kernel/linux-3.4rt/fs/proc/base.c	2017-03-23 00:06:43.000000000 -0700 [P]
+++ kernel/linux-3.4rt/arch/arm/mach-bcm963xx/Makefile	2017-03-23 00:06:43.000000000 -0700 [P]
+++ kernel/linux-3.4rt/block/genhd.c	2017-03-23 00:06:43.000000000 -0700 [P]
+++ kernel/linux-3.4rt/crypto/algif_hash.c	2017-03-23 00:06:43.000000000 -0700 [P]

```

#### [wifi]
```
+++ bcmdrivers/opensource/net/wfd/impl1/wfd_dev.c	2017-03-23 00:06:41.000000000 -0700 [W]
```

#### [DSL]
```
+++ bcmdrivers/opensource/net/xtmrt/impl5/bcmxtmrt.c	2017-03-23 00:06:41.000000000 -0700  [xtmrt ???]
+++ bcmdrivers/broadcom/include/bcm963xx/AdslMibDef.h	2017-03-23 00:06:35.000000000 -0700
+++ bcmdrivers/broadcom/include/bcm963xx/DiagDef.h	2017-03-23 00:06:35.000000000 -0700
+++ bcmdrivers/broadcom/char/xtmcfg/impl2/xtmconnection.cpp	2017-03-23 00:06:35.000000000 -0700
+++ bcmdrivers/broadcom/char/xtmcfg/impl2/xtmcfgimpl.h	2017-03-23 00:06:35.000000000 -0700
+++ bcmdrivers/broadcom/char/xtmcfg/impl2/xtmprocessor.cpp	2017-03-23 00:06:35.000000000 -0700
+++ bcmdrivers/broadcom/char/adsl/impl1/BcmAdslCore.c	2017-03-23 00:06:34.000000000 -0700
+++ bcmdrivers/broadcom/char/adsl/impl1/AdslCore.c	2017-03-23 00:06:34.000000000 -0700
+++ bcmdrivers/broadcom/char/adsl/impl1/BcmOs.c	2017-03-23 00:06:34.000000000 -0700
+++ bcmdrivers/broadcom/char/adsl/impl1/AdslDrvVersion.h	2017-03-23 00:06:34.000000000 -0700
+++ bcmdrivers/broadcom/char/adsl/impl1/BcmAdslCore.h	2017-03-23 00:06:34.000000000 -0700
+++ bcmdrivers/broadcom/char/adsl/impl1/BcmAdslDiagCommon.c	2017-03-23 00:06:34.000000000 -0700
+++ bcmdrivers/broadcom/char/adsl/impl1/AdslCore.h	2017-03-23 00:06:34.000000000 -0700
+++ bcmdrivers/broadcom/char/adsl/impl1/adsldrv.c	2017-03-23 00:06:34.000000000 -0700
+++ bcmdrivers/broadcom/char/adsl/impl1/softdsl/G997.h	2017-03-23 00:06:34.000000000 -0700
+++ bcmdrivers/broadcom/char/adsl/impl1/softdsl/G992p3OvhMsg.h	2017-03-23 00:06:34.000000000 -0700
+++ bcmdrivers/broadcom/char/adsl/impl1/softdsl/G997.c	2017-03-23 00:06:34.000000000 -0700
+++ bcmdrivers/broadcom/char/adsl/impl1/softdsl/SoftDsl.h	2017-03-23 00:06:35.000000000 -0700
+++ bcmdrivers/broadcom/char/adsl/impl1/softdsl/AdslMib.c	2017-03-23 00:06:34.000000000 -0700
+++ bcmdrivers/broadcom/char/adsl/impl1/softdsl/G992p3OvhMsg.c	2017-03-23 00:06:34.000000000 -0700
+++ bcmdrivers/broadcom/char/adsl/impl1/softdsl/AdslMib.h	2017-03-23 00:06:34.000000000 -0700
+++ bcmdrivers/broadcom/char/adsl/impl1/softdsl/AdslMib.gh	2017-03-23 00:06:34.000000000 -0700
```