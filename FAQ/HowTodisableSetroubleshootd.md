# info
https://security.stackexchange.com/questions/126612/how-to-know-if-setroubleshoot-is-running-in-centos-7-2

# link
https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/7/html/selinux_users_and_administrators_guide/sect-security-enhanced_linux-working_with_selinux-which_log_file_is_used

# 解决方法
setroubleshoot是排查应用会被selinux阻止启动的工具。  
由于setroubleshoot不再以service运行，简单的方式是直接卸载。  
`yum remove setroubleshoot-server`

