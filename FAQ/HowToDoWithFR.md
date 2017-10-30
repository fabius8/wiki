## FR处理流程
new->accept->deliver->build->resolve->verify

## 提交错误汇总
```
   Error: ALU02375809 status N is not in  X

   Abort !!!
```
切换到accept状态，assigne engineer 检查下

## sdk 提交代码
```
注意以上提交代码都是在FDT库里提交的过程，比如HD_R56_FDT1256库
如果提交的代码是SDK的库（如BCMSDKv502L02）或者opensource库里面的内容：
1.	http://135.251.228.99/ext_repo/ext_repo.php
在该网址（用火狐或者IE打开）填写信息，把patch上传，由管理员提交
这个里面有一项是reviewID号，同上一封邮件，也是需要在相应库里先ci和post-review之后，生成一个reviewID号填写。
2.	SDK库的管理员是shen Peihua, opensource的库管理员是zhang Jianliang 
3.	网页上生成项之后，要发邮件给相应的管理员，由管理员代为提交代码。
4.	管理员提交之后会发邮件通知我们，此时在相应的库里，用hg incom命令可以看到，自己的代码已经进到SDK 或者OPENSOURCE，并且有一个changeset号
5.	在对应文件里修改changeset号把文件修改进到FDT库里。（SDK：XS_BCMSDKv502L02.mk        OPENSOURCE：XS_OPENSOURCE.mk）

注意：SDK和opensource的改动会影响其他板子，要做好注释和隔离，进代码要谨慎，一定要经过review
```

## pullme

http://172.24.213.179:8888/aont_pullme.html

`export PATH=/ap/local/cpe_ci/aont_pullme/pullme:$PATH`  
`pullme --fr=ALU02384597.rev="all()"`
