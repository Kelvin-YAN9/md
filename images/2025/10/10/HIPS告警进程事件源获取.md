# HIPS告警进程事件源获取

可疑命令插件名chaitin.skyeye.cmd_audit

1. 执行可疑命令

   ```shell
   root@24agent:~# python3 -c 'import pty;pty.spawn("/bin/sh")'
   # 
   ```

   通过`pty.spawn()`函数创建终端

2. 查看执行命令的进程信息

   ```shell
   root@24agent:~# pstree -p
   systemd(1)──sshd(916)──sshd(2800)───bash(2850)───python3(3190)───sh(3191)
   ```

   ![image-20250910160031461](/Users/ys/Documents/md/牧云/HIPS告警进程事件源获取.assets/image-20250910160031461.png)

3. 查看debug日志查查找对应事件源

