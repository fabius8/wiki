– Create the patch first. Being on your current repository do:

`hg diff > mychanges.diff`

BTW, you can achieve this though hg export also.

– Clone a new repository or move to the repo you want to apply the patch.

– move to your repository and apply the patch

`hg import mychanges.diff`

# revert
* `hg strip -r xxxx  --keep`    
backupfile saved  
* `hg unbundle xxxx`  
backupfile load     
