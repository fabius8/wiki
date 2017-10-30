## Sharing the method to reduce compile time of compile kernel module like enet:

* First need the entire compilation

* Modify makeRule/target.brcm

 `sed -i 's/kernel_mod: kernel/kernel_mod:/' makeRule/targets.brcm`

* Modify xs/BCMSDKv502L02/GNUmakefile

 `sed -i 's/kernelmod: kernel/kernelmod:/' xs/BCMSDKv502L02/GNUmakefile`

* compile

 `cd build/brcm/xg250wxa`
 
 `make kernel_mod ASB_PLATFORM=brcm voip=no AONT_VOIP=n ONT_TYPE=xg250wxa`