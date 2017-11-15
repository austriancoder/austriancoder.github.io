---
layout: post
title: Change mac address under linux - the brutal way
date: '2012-10-13 11:42:24'
---


Last days I run into a problem that I needed to change the mac address of a network card directly under linux. In the last years VxWorks was used for this purpose – oh and yes I know that you should not change a mac address 🙂 But I am working in a company which produces devices with network ports and they need an initial mac address.

The first thing you would try is to use ifconfig to change the mac address.

ifconfig eth0 hw ether xx:xx:xx:xx:xx:xx

 root@OT:~# strace ifconfig eth0 hw ether 00:10:7e:02:52:b6 execve("/sbin/ifconfig", ["ifconfig", "eth0", "hw", "ether", "00:10:7e:02:52:b6"], [/* 11 vars */]) = 0 brk(0) = 0x943b000 access("/etc/ld.so.nohwcap", F_OK) = -1 ENOENT (No such file or directory) mmap2(NULL, 4096, PROT_READ|PROT_WRITE, MAP_PRIVATE|MAP_ANONYMOUS, -1, 0) = 0xb77d0000 access("/etc/ld.so.preload", R_OK) = -1 ENOENT (No such file or directory) open("/etc/ld.so.cache", O_RDONLY) = 3 fstat64(3, {st_mode=S_IFREG|0644, st_size=20075, ...}) = 0 mmap2(NULL, 20075, PROT_READ, MAP_PRIVATE, 3, 0) = 0xb77cb000 close(3) = 0 access("/etc/ld.so.nohwcap", F_OK) = -1 ENOENT (No such file or directory) open("/lib/libc.so.6", O_RDONLY) = 3 read(3, "177ELF111\0\0\0\0\0\0\0\0\03\03\01\0\0\0360m1\0004\0\0\0"..., 512) = 512 fstat64(3, {st_mode=S_IFREG|0755, st_size=1319176, ...}) = 0 mmap2(NULL, 4096, PROT_READ|PROT_WRITE, MAP_PRIVATE|MAP_ANONYMOUS, -1, 0) = 0xb77ca000 mmap2(NULL, 1329480, PROT_READ|PROT_EXEC, MAP_PRIVATE|MAP_DENYWRITE, 3, 0) = 0xb7685000 mprotect(0xb77c3000, 4096, PROT_NONE) = 0 mmap2(0xb77c4000, 12288, PROT_READ|PROT_WRITE, MAP_PRIVATE|MAP_FIXED|MAP_DENYWRITE, 3, 0x13e) = 0xb77c4000 mmap2(0xb77c7000, 10568, PROT_READ|PROT_WRITE, MAP_PRIVATE|MAP_FIXED|MAP_ANONYMOUS, -1, 0) = 0xb77c7000 close(3) = 0 mmap2(NULL, 4096, PROT_READ|PROT_WRITE, MAP_PRIVATE|MAP_ANONYMOUS, -1, 0) = 0xb7684000 set_thread_area({entry_number:-1 -> 6, base_addr:0xb76846c0, limit:1048575, seg_32bit:1, contents:0, read_exec_only:0, limit_in_pages:1, seg_not_present:0, useable:1}) = 0 mprotect(0xb77c4000, 8192, PROT_READ) = 0 mprotect(0xb77ed000, 4096, PROT_READ) = 0 munmap(0xb77cb000, 20075) = 0 brk(0) = 0x943b000 brk(0x945c000) = 0x945c000 uname({sys="Linux", node="OT", ...}) = 0 access("/proc/net", R_OK) = 0 access("/proc/net/unix", R_OK) = 0 socket(PF_FILE, SOCK_DGRAM, 0) = 3 socket(PF_INET, SOCK_DGRAM, IPPROTO_IP) = 4 access("/proc/net/if_inet6", R_OK) = -1 ENOENT (No such file or directory) access("/proc/net/ax25", R_OK) = -1 ENOENT (No such file or directory) access("/proc/net/nr", R_OK) = -1 ENOENT (No such file or directory) access("/proc/net/rose", R_OK) = -1 ENOENT (No such file or directory) access("/proc/net/ipx", R_OK) = -1 ENOENT (No such file or directory) access("/proc/net/appletalk", R_OK) = -1 ENOENT (No such file or directory) access("/proc/sys/net/econet", R_OK) = -1 ENOENT (No such file or directory) access("/proc/sys/net/ash", R_OK) = -1 ENOENT (No such file or directory) access("/proc/net/x25", R_OK) = -1 ENOENT (No such file or directory) ioctl(4, SIOCSIFHWADDR, {ifr_name="eth0", ifr_hwaddr=00:10:7e:02:52:b6}) = 0 exit_group(0) = ?

What this does is to change the mac address, but after a reboot this change is gone. So where is the mac address stored, you my ask. Normaly each NIC has an eeprom where some specific informations are stored like the mac address. And for linux there exists a nice tool to dump and change the contents of this eeproms – ethtool.

 root@OT:~# ethtool -e eth0 Offset Values ------ ------ 0x0000 00 10 7e 01 fc 5b 00 00 00 00 01 03 01 47 00 00 0x0010 00 00 00 00 c0 49 01 00 00 00 70 00 00 00 00 00 0x0020 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 0x0030 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 0x0040 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 0x0050 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 0x0060 20 00 01 40 0a 41 00 00 00 00 00 00 00 00 00 00 0x0070 00 00 00 00 00 00 00 00 00 00 00 00 00 00 e2 37

 root@OT:~# ifconfig eth0 eth0 Link encap:Ethernet HWaddr 00:10:7e:01:fc:5b inet addr:10.204.120.12 Bcast:10.204.127.255 Mask:255.255.192.0 UP BROADCAST RUNNING MULTICAST MTU:1500 Metric:1 RX packets:812 errors:0 dropped:0 overruns:0 frame:0 TX packets:37 errors:0 dropped:0 overruns:0 carrier:0 collisions:0 txqueuelen:1000 RX bytes:125002 (122.0 KiB) TX bytes:3195 (3.1 KiB)

Did you see it? We found the place where our mac address is stored 🙂
 Lets try to change the mac address directly in the eeprom.

 root@OT:~# ethtool -E eth0 magic 0x1234 offset 0x5 value 0x5c root@OT:~# ethtool -e eth0 Offset Values ------ ------ 0x0000 00 10 7e 01 fc 5c 00 00 00 00 01 03 01 47 00 00 0x0010 00 00 00 00 c0 49 01 00 00 00 70 00 00 00 00 00 0x0020 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 0x0030 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 0x0040 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 0x0050 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 0x0060 20 00 01 40 0a 41 00 00 00 00 00 00 00 00 00 00 0x0070 00 00 00 00 00 00 00 00 00 00 00 00 00 00 e2 36

In theory our new mac address should be available after an reboot.

 root@OT:~# reboot root@OT:~# ifconfig eth0 eth0 Link encap:Ethernet HWaddr 00:10:7e:01:fc:5c inet addr:10.204.120.12 Bcast:10.204.127.255 Mask:255.255.192.0 UP BROADCAST RUNNING MULTICAST MTU:1500 Metric:1 RX packets:482 errors:0 dropped:0 overruns:0 frame:0 TX packets:7 errors:0 dropped:0 overruns:0 carrier:0 collisions:0 txqueuelen:1000 RX bytes:32327 (31.5 KiB) TX bytes:986 (986.0 B)

Success – now its time for the big **fat warning:**

Every NIC stores the mac address at different offsets etc. so its a good idea
 to first look at the datasheet and then make experiments. Also the magic value
 needed for ethtool needs to be kown – look at the corresponding linux driver.
