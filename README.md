# network-security-issues

## 移除可疑的 crontab 任务
### 编辑 crontab：
运行 crontab -e 命令以编辑当前用户（在这个案例中是 root 用户）的 crontab。  

### 注释或删除任务：
在编辑器中，你可以通过在每行任务前添加 # 来注释掉这些行。这将阻止它们被执行，但仍然保留记录以备后用。如果你确定这些任务是恶意的，可以直接删除这些行。  
```
# 5 6 * * 0 /root/.configrc5/a/upd>/dev/null 2>&1
# @reboot /root/.configrc5/a/upd>/dev/null 2>&1
# 5 8 * * 0 /root/.configrc5/b/sync>/dev/null 2>&1
# @reboot /root/.configrc5/b/sync>/dev/null 2>&1
# 0 0 */3 * * /tmp/.X291-unix/.rsync/c/aptitude>/dev/null 2>&1
```
### 保存并退出编辑器：
完成编辑后，根据你的编辑器指示保存更改并退出。这通常涉及按下 Ctrl + X，然后按 Y 以确认保存更改，最后按 Enter 键退出。  

### 确认更改：
使用 crontab -l 再次查看，确认可疑的任务已被注释掉或删除。  

