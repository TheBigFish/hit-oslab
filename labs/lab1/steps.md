# steps

## 配置环境

## 文件交换

```bash
$ cd ~/oslab/
$
# 启动挂载脚本
$ sudo ./mount-hdc
$
```

```bash
bigfish@bigfish:~/oslab$ cd hdc/
bigfish@bigfish:~/oslab/hdc$ ls
bin  dev  etc  image  Image  mnt  shoelace  tmp  usr  var
bigfish@bigfish:~/oslab/hdc$ ls -hal
total 186K
drwxr-xr-x 10 root    root     192 Apr 28  2005 .
drwxr-xr-x  5 bigfish bigfish 4.0K Oct 16 14:37 ..
drwxr-xrwx  2 root    root     880 Mar 22  2004 bin
drwxr-xrwx  2 root    root     336 Mar 22  2004 dev
drwxr-xrwx  2 root    root     256 Sep 24  2004 etc
drwxr-xrwx  8 root    root     128 Mar 22  2004 image
-rw----rw-  1 root    root    123K Apr 28  2005 Image
drwxr-xrwx  6 root    root     112 Sep 24  2004 mnt
-rwx--xrwx  1 root    root     48K Sep 22  2004 shoelace
drwxr-xrwx  2 root    root      80 Sep 24  2004 tmp
drwxr-xrwx 10 root    root     160 Mar 30  2004 usr
drwxr-xrwx  2 root    root      32 Mar 22  2004 var
```

```bash
$ cd ~/oslab/
$
# 卸载
$ sudo umount hdc
$
```
