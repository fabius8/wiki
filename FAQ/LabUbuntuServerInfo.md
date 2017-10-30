# IP
192.168.122.120
# 外部管理
ssh admin@135.252.227.21 -p 6020

# apt
```
sudo apt -o Acquire::AllowInsecureRepositories=true \
-o Acquire::AllowDowngradeToInsecureRepositories=true \
update
```