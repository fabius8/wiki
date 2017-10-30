
## 单模块编译  
```
1. cd sysdrivers/bcmdrv/502L02/src/  
2. make ASB_PLATFORM=brcm voip=no AONT_VOIP=n ONT_TYPE=xg250wxa TOP_DIR=`hg root`  
 (这里会将ko直接安装到fs.install下)  
3. cd build/brcm/xg250wxa/  
4. make noRemake=1 ASB_PLATFORM=brcm voip=no AONT_VOIP=n ONT_TYPE=xg250wxa  
(生成版本)
```  