[[_TOC_]]

# patch 1
## APP 未打
```
+++ userspace/private/apps/tmctl/tmctl_cmds.c	2016-04-13 19:15:15.000000000 -0700
+++ userspace/private/apps/ethctl/ethctl_cmd.c	2016-04-13 19:15:16.000000000 -0700
+++ userspace/private/apps/swmdk/swmdk.c	2016-04-13 19:15:16.000000000 -0700
+++ userspace/private/include/tmctl_api.h	2016-04-13 19:15:20.000000000 -0700
+++ userspace/private/libs/cms_core/linux/rut_qos_queue.c	2016-04-13 19:15:23.000000000 -0700
+++ userspace/private/libs/tmctl/tmctl_rdpa.c	2016-04-13 19:15:26.000000000 -0700
```
## SDK
```
+++ shared/opensource/drivers/bcm_ethsw_impl2.c	2016-04-13 19:11:29.000000000 -0700
+++ shared/broadcom/rdp/impl2/rdd/rdd_runner_defs.h	2016-04-13 19:15:53.000000000 -0700
+++ shared/broadcom/rdp/impl2/rdd/rdd_init.c	2016-04-13 19:15:53.000000000 -0700
+++ shared/broadcom/rdp/impl2/rdd/rdd_runner_defs_auto.h	2016-04-13 19:15:53.000000000 -0700
+++ shared/broadcom/rdp/impl2/rdd/rdd_data_structures_auto.h	2016-04-13 19:15:53.000000000 -0700
+++ shared/broadcom/rdp/impl2/rdd/generated/dsl_63148/rdd_runner_reg_dump_addrs.h	2016-04-13 19:15:53.000000000 -0700
+++ shared/broadcom/rdp/impl2/rdd/generated/dsl_63148/rdd_runner_reg_dump_addrs.c	2016-04-13 19:15:53.000000000 -0700
+++ shared/broadcom/rdp/impl2/rdd/generated/dsl_63148/rdd_runner_reg_dump.c	2016-04-13 19:15:53.000000000 -0700
+++ shared/broadcom/rdp/impl2/rdd/generated/dsl_63148/rdd_runner_reg_dump.h	2016-04-13 19:15:53.000000000 -0700
+++ shared/broadcom/rdp/impl2/rdd/generated/dsl_63138/rdd_runner_reg_dump_addrs.h	2016-04-13 19:15:53.000000000 -0700
+++ shared/broadcom/rdp/impl2/rdd/generated/dsl_63138/rdd_runner_reg_dump_addrs.c	2016-04-13 19:15:53.000000000 -0700
+++ shared/broadcom/rdp/impl2/rdd/generated/dsl_63138/rdd_runner_reg_dump.c	2016-04-13 19:15:53.000000000 -0700
+++ shared/broadcom/rdp/impl2/rdd/generated/dsl_63138/rdd_runner_reg_dump.h	2016-04-13 19:15:53.000000000 -0700
+++ kernel/linux-3.4rt/net/ipv6/ip6mr.c	2016-04-13 19:11:24.000000000 -0700
+++ kernel/linux-3.4rt/net/bridge/br_ioctl.c	2016-04-13 19:11:24.000000000 -0700
+++ kernel/linux-3.4rt/net/ipv4/ipmr.c	2016-04-13 19:11:24.000000000 -0700
+++ kernel/linux-3.4rt/net/core/blog.c	2016-04-13 19:11:24.000000000 -0700
+++ kernel/linux-3.4rt/include/linux/mroute.h	2016-04-13 19:11:23.000000000 -0700
+++ bcmdrivers/opensource/char/i2c/busses/impl1/i2c_bcm6xxx.c	2016-04-13 19:11:12.000000000 -0700
+++ bcmdrivers/opensource/net/enet/impl5/bcmsw_dma.c	2016-04-13 19:11:13.000000000 -0700
+++ bcmdrivers/opensource/net/enet/impl5/bcmenet.c	2016-04-13 19:11:12.000000000 -0700
+++ bcmdrivers/opensource/net/enet/impl5/bcmsw.c	2016-04-13 19:11:13.000000000 -0700
+++ bcmdrivers/broadcom/char/pktflow/impl1/flwstats.c	2016-04-13 19:11:00.000000000 -0700
+++ bcmdrivers/broadcom/char/tms/impl1/Makefile	2016-04-13 19:11:01.000000000 -0700
```

# patch 2_1
```
+++ cfe/cfe/arch/arm/board/bcm63xx_rom/src/bcm63xx_impl1_rom_boot.S	2016-07-13 18:41:43.000000000 -0700
+++ cfe/cfe/arch/arm/board/bcm63xx_rom/src/bcm63xx_impl1_ddr_mcb.c	2016-07-13 18:41:43.000000000 -0700
+++ cfe/cfe/arch/arm/board/bcm63xx_rom/src/mcb/mcb_63138A_800MHz_16b_dev2Gx8_DDR3-1600K_ssc_p5per.h	2016-07-13 18:41:43.000000000 -0700
+++ cfe/cfe/arch/arm/board/bcm63xx_rom/src/mcb/mcb_63138A_800MHz_16b_dev4Gx16_DDR3-1600K_ssc_p5per.h	2016-07-13 18:41:43.000000000 -0700
+++ cfe/cfe/arch/arm/board/bcm63xx_rom/src/mcb/mcb_63138A_800MHz_16b_dev4Gx8_DDR3-1600K_ssc_p5per.h	2016-07-13 18:41:43.000000000 -0700
+++ cfe/cfe/arch/arm/board/bcm63xx_rom/src/mcb/mcb_63138A_800MHz_16b_dev2Gx16_DDR3-1600K_ssc_p5per.h	2016-07-13 18:41:43.000000000 -0700
+++ cfe/cfe/arch/arm/common/src/init_arm.S	2016-07-13 18:41:43.000000000 -0700
+++ cfe/cfe/arch/arm/common/src/pmc.S	2016-07-13 18:41:43.000000000 -0700
+++ cfe/build/broadcom/bcm63xx_rom/Makefile	2016-07-13 18:41:43.000000000 -0700
+++ hostTools/scripts/defconfig-bcm.template	2016-07-13 18:42:15.000000000 -0700
+++ hostTools/scripts/gendefconfig.d/15general.conf	2016-07-13 18:42:15.000000000 -0700
+++ userspace/private/apps/ethswctl/ethswctl.c	2016-07-13 18:43:13.000000000 -0700
+++ userspace/public/libs/bcm_flashutil/bcm_flashutil.c	2016-07-13 18:43:23.000000000 -0700
+++ bcmdrivers/opensource/include/bcm963xx/bcmxtmrt.h	2016-07-13 18:41:42.000000000 -0700
+++ bcmdrivers/opensource/char/rdpa_gpl/impl1/include/rdpa_l2_ucast.h	2016-07-13 18:43:56.000000000 -0700
+++ bcmdrivers/opensource/net/wfd/impl1/wfd_dev.c	2016-07-13 18:41:43.000000000 -0700
+++ bcmdrivers/opensource/net/enet/impl5/bcmmii.h	2016-07-13 18:41:42.000000000 -0700
+++ bcmdrivers/opensource/net/enet/impl5/bcmsw_runner.h	2016-07-13 18:41:43.000000000 -0700
+++ bcmdrivers/opensource/net/enet/impl5/bcmsw_dma.c	2016-07-13 18:41:42.000000000 -0700
+++ bcmdrivers/opensource/net/enet/impl5/bcmswdefs.h	2016-07-13 18:41:43.000000000 -0700
+++ bcmdrivers/opensource/net/enet/impl5/ethsw.c	2016-07-13 18:41:43.000000000 -0700
+++ bcmdrivers/opensource/net/enet/impl5/bcmsw_dma.h	2016-07-13 18:41:43.000000000 -0700
+++ bcmdrivers/opensource/net/enet/impl5/bcmsw.c	2016-07-13 18:41:42.000000000 -0700
+++ bcmdrivers/opensource/net/enet/impl5/bcmenet.c	2016-07-13 18:41:42.000000000 -0700
+++ bcmdrivers/opensource/net/enet/impl5/bcmsw_runner.c	2016-07-13 18:41:43.000000000 -0700
+++ bcmdrivers/opensource/net/enet/impl5/bcmsw.h	2016-07-13 18:41:42.000000000 -0700
+++ bcmdrivers/opensource/net/enet/impl5/ethsw_phy.c	2016-07-13 18:41:43.000000000 -0700
+++ bcmdrivers/opensource/net/xtmrt/impl5/xtmrt_runner.c	2016-07-13 18:41:43.000000000 -0700
+++ bcmdrivers/opensource/net/xtmrt/impl5/bcmxtmrt.c	2016-07-13 18:41:43.000000000 -0700
+++ bcmdrivers/opensource/net/xtmrt/impl5/xtmrt_dma.h	2016-07-13 18:41:43.000000000 -0700
+++ bcmdrivers/opensource/net/xtmrt/impl5/xtmrt_cfg.c	2016-07-13 18:41:43.000000000 -0700
+++ bcmdrivers/opensource/net/xtmrt/impl5/xtmrt_runner.h	2016-07-13 18:41:43.000000000 -0700
+++ bcmdrivers/opensource/net/xtmrt/impl5/xtmrt_dma.c	2016-07-13 18:41:43.000000000 -0700
+++ bcmdrivers/broadcom/include/bcm963xx/fcache.h	2016-07-13 18:41:37.000000000 -0700
+++ bcmdrivers/broadcom/char/pktrunner/impl2/pktrunner_proto.c	2016-07-13 18:41:37.000000000 -0700
+++ bcmdrivers/broadcom/char/fap/impl1/fap_wfd_inline.h	2016-07-13 18:41:37.000000000 -0700
+++ bcmdrivers/broadcom/char/fap/impl1/fap_packet.c	2016-07-13 18:41:37.000000000 -0700
+++ bcmdrivers/broadcom/char/fap/impl1/fap_mcast.c	2016-07-13 18:41:37.000000000 -0700
+++ bcmdrivers/broadcom/char/fap/impl1/4ke/fap4ke_packet.h	2016-07-13 18:41:37.000000000 -0700
+++ bcmdrivers/broadcom/char/vlan/impl1/bcm_vlan_dev.c	2016-07-13 18:41:37.000000000 -0700
+++ bcmdrivers/broadcom/char/rdpa/impl1/rdpa_mcast.c	2016-07-13 18:43:56.000000000 -0700
+++ bcmdrivers/broadcom/char/rdpa/impl1/rdpa_ucast.c	2016-07-13 18:43:56.000000000 -0700
+++ bcmdrivers/broadcom/char/rdpa/impl1/rdpa_l2_ucast.c	2016-07-13 18:43:56.000000000 -0700
+++ bcmdrivers/broadcom/char/xtmcfg/impl2/xtmconnection.cpp	2016-07-13 18:41:37.000000000 -0700
+++ bcmdrivers/broadcom/char/xtmcfg/impl2/xtmcfgimpl.h	2016-07-13 18:41:37.000000000 -0700
+++ bcmdrivers/broadcom/char/xtmcfg/impl2/xtmoslinux.c	2016-07-13 18:41:37.000000000 -0700
+++ bcmdrivers/broadcom/char/xtmcfg/impl2/xtmprocessor.cpp	2016-07-13 18:41:37.000000000 -0700
+++ bcmdrivers/broadcom/char/xtmcfg/impl2/xtmcfgdrv.c	2016-07-13 18:41:37.000000000 -0700
+++ bcmdrivers/broadcom/char/pktflow/impl1/fcachehw.c	2016-07-13 18:41:37.000000000 -0700
+++ bcmdrivers/broadcom/char/pktflow/impl1/flwstats.c	2016-07-13 18:41:37.000000000 -0700
+++ shared/opensource/include/bcm963xx/63148_map_part.h	2016-07-13 18:41:48.000000000 -0700
+++ shared/opensource/include/bcm963xx/63138_map_part.h	2016-07-13 18:41:48.000000000 -0700
+++ shared/opensource/include/bcm963xx/63381_map_part.h	2016-07-13 18:41:48.000000000 -0700
+++ shared/opensource/flash/nandflash.c	2016-07-13 18:41:48.000000000 -0700
+++ shared/broadcom/rdp/impl2/rdd/rdd_router.h	2016-07-13 18:43:57.000000000 -0700
+++ shared/broadcom/rdp/impl2/rdd/rdd_router.c	2016-07-13 18:43:57.000000000 -0700
+++ shared/broadcom/rdp/impl2/rdd/dhd_defs.h	2016-07-13 18:43:56.000000000 -0700
+++ shared/broadcom/rdp/impl2/rdd/rdd_runner_defs.h	2016-07-13 18:43:57.000000000 -0700
+++ shared/broadcom/rdp/impl2/rdd/rdd_data_structures_auto.h	2016-07-13 18:43:57.000000000 -0700
+++ shared/broadcom/rdp/impl2/rdd/rdd_tm.c	2016-07-13 18:43:57.000000000 -0700
+++ shared/broadcom/rdp/impl2/rdd/rdd_l2_ucast.c	2016-07-13 18:43:57.000000000 -0700
+++ shared/broadcom/rdp/impl2/rdd/generated/dsl_63148/rdd_runner_reg_dump.c	2016-07-13 18:43:57.000000000 -0700
+++ shared/broadcom/rdp/impl2/rdd/generated/dsl_63148/rdd_runner_d_labels.h	2016-07-13 18:43:57.000000000 -0700
+++ shared/broadcom/rdp/impl2/rdd/generated/dsl_63148/rdd_runner_a_labels.h	2016-07-13 18:43:57.000000000 -0700
+++ shared/broadcom/rdp/impl2/rdd/generated/dsl_63138/rdd_runner_reg_dump.c	2016-07-13 18:43:57.000000000 -0700
+++ shared/broadcom/rdp/impl2/rdd/generated/dsl_63138/rdd_runner_d_labels.h	2016-07-13 18:43:57.000000000 -0700
+++ shared/broadcom/rdp/impl2/rdd/generated/dsl_63138/rdd_runner_a_labels.h	2016-07-13 18:43:57.000000000 -0700
+++ shared/broadcom/rdp/impl1/rdd/dhd_defs.h	2016-07-13 18:43:56.000000000 -0700
+++ kernel/linux-3.4rt/Kconfig.bcm	2016-07-13 18:42:15.000000000 -0700
+++ kernel/linux-3.4rt/drivers/mtd/brcmnand/brcmnand_base.c	2016-07-13 18:41:45.000000000 -0700
+++ kernel/linux-3.4rt/include/linux/blog.h	2016-07-13 18:41:45.000000000 -0700
+++ kernel/linux-3.4rt/include/linux/crypto.h	2016-07-13 18:41:45.000000000 -0700
+++ kernel/linux-3.4rt/include/linux/flwstif.h	2016-07-13 18:41:45.000000000 -0700
+++ kernel/linux-3.4rt/include/linux/mtd/bchp_nand_7x.h	2016-07-13 18:41:45.000000000 -0700
+++ kernel/linux-3.4rt/net/ipv4/esp4.c	2016-07-13 18:41:45.000000000 -0700
+++ kernel/linux-3.4rt/net/core/flwstif.c	2016-07-13 18:41:45.000000000 -0700
+++ kernel/linux-3.4rt/net/core/blog.c	2016-07-13 18:41:45.000000000 -0700
+++ kernel/linux-3.4rt/net/core/iqos.c	2016-07-13 18:41:45.000000000 -0700
+++ kernel/linux-3.4rt/net/ipv6/ip6_tunnel.c	2016-07-13 18:41:45.000000000 -0700
+++ kernel/linux-3.4rt/net/ipv6/sit.c	2016-07-13 18:41:45.000000000 -0700
+++ kernel/linux-3.4rt/net/netfilter/nf_conntrack_proto_tcp.c	2016-07-13 18:41:45.000000000 -0700
+++ kernel/linux-3.4rt/net/netfilter/nf_conntrack_core.c	2016-07-13 18:42:06.000000000 -0700
+++ kernel/linux-3.4rt/net/netfilter/nf_conntrack_acct.c	2016-07-13 18:41:45.000000000 -0700
+++ kernel/linux-3.4rt/net/bridge/br_mcast.c	2016-07-13 18:41:45.000000000 -0700
+++ kernel/linux-3.4rt/net/bridge/br_input.c	2016-07-13 18:41:45.000000000 -0700
+++ targets/config.in	2016-07-13 18:42:15.000000000 -0700
```

# patch 2_2
```
+++ bcmdrivers/broadcom/char/xtmcfg/impl2/xtmoamhandler.cpp	2016-07-15 13:15:49.000000000 -0700
+++ bcmdrivers/broadcom/char/xtmcfg/impl2/xtmprocessor.cpp	2016-07-15 15:09:39.000000000 -0700
```
