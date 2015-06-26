# review
questions from https://github.com/chassing/linux-sysadmin-interview-questions
Linux System Administrator/DevOps Interview Questions
====================================================

A collection of linux sysadmin/devops interview questions. Feel free to contribute via pull requests, issues or email messages.


## <a name='toc'>Table of Contents</a>

  1. [Contributors](#contributors)
  1. [General Questions](#general)
  1. [Simple Linux Questions](#simple)
  1. [Medium Linux Questions](#medium)
  1. [Hard Linux Questions](#hard)
  1. [Expert Linux Questions](#expert)
  1. [Networking Questions](#network)
  1. [MySQL Questions](#mysql)
  1. [DevOps Questions](#devop)
  1. [Fun Questions](#fun)
  1. [Demo Time](#demo)
  1. [Other Great References](#references)


####[[⬆]](#toc) <a name='contributors'>Contributors:</a>

* [moregeek](https://github.com/moregeek)
* [typhonius](https://github.com/typhonius)
* martin
* [negesti](https://github.com/negesti)
* peter
* [andreashappe](https://github.com/andreashappe)
* [quatrix](https://github.com/quatrix)
* [biyanisuraj](https://github.com/biyanisuraj)
* [pedroguima](https://github.com/pedroguima)
* Ben


####[[⬆]](#toc) <a name='general'>General Questions:</a>

* What did you learn yesterday/this week?
* Talk about your preferred development/administration environment. (OS, Editor, Browsers, Tools etc.)
* Tell me about the last major Linux project you finished.
* Tell me about the biggest mistake you've made in [some recent time period] and how you would do it differently today. What did you learn from this experience?
* Why we must choose you?
* What function does DNS play on a network?
DNS是域名系统，对域名和IP地址进行相互映射
* What is HTTP?
HTTP是超文本传输协议，用于从WWW服务器传输超文本到本地浏览器。
* What is an HTTP proxy and how does it work?
* Describe briefly how HTTPS works.
* What is SMTP? Give the basic scenario of how a mail message is delivered via SMTP.
* What is RAID? What is RAID0, RAID1, RAID5, RAID10?
磁盘阵列
RAID0：数据分条技术
RAID1：磁盘镜像
RAID5：分布式奇偶校验的独立磁盘结构
RAID10：高可靠性与高效磁盘结构
* What is a level 0 backup? What is an incremental backup?
* Describe the general file system hierarchy of a Linux system.


####[[⬆]](#toc) <a name='simple'>Simple Linux Questions:</a>

* What is the name and the UID of the administrator user?  
	id -n  
	id -u  
	sudo cat /etc/passwd | grep sakurasou  
* How to list all files, including hidden one, in a directory?  
	ls -a  
* What is the Unix/Linux command to remove a directory and its contents?  
	rm -rf <name>
* Which command will show you free/used memory? Does free memory exist on Linux?  
	free
	存在，但通常都很小，很多都被buffer和cache
* How to search for the string "my konfi is the best" in files of a directory recursively?  
	find <dir> | xargs grep -r "my konfi is the best" 
* How to connect to a remote server or what is SSH?
	ssh <address>
* How to get all environment variables and how can you use them?  
	env
	使用export设置一个新的环境变量
	使用unset清除一个环境变量
* I get "command not found" when I run ```ifconfig -a```. What can be wrong?
	没装网卡驱动？
* What happens if I type TAB-TAB?
	如果输入m，再连续按两次TAB键，将列出所有以m开头的命令
* What command will show the available disk space on the Unix/Linux system?
	df -h
* What commands do you know that can be used to check DNS records?
	cat /etc/resolv.conf
* What Unix/Linux commands will alter a files ownership, files permissions?
	chown chmod
* What does ```chmod +x FILENAME```do?
	更改文件权限
* What does the permission 0750 on a file mean?
	rwxr-x---
* What does the permission 0750 on a directory mean?
	要注意目录的x权限指的是能否进入这个目录
* How to add a new system user without login permissions?
	adduser <username>
* How to add/remove a group from a user?
	groupadd <groupname>
* What is a bash alias?
	命令的别名，如 alias ll="ls -l",则敲ll即能执行ls -l的功能
* How do you set the mail address of the root/a user?
* What does CTRL-c do?
	传递SIGINT信号
* What is in /etc/services?
	记录网络服务名以及对应的端口号信息
* How to redirect STDOUT and STDERR in bash? (> /dev/null 2>&1)
	注意2>&1与2>1的区别，前者将STDERR重定向到STDOUT，后者却重定向到1文件
* What is the difference between UNIX and Linux.
* What is the difference between Telnet and SSH?
	安全性的区别，SSH把传输的数据进行加密，更安全。
* Explain the three load averages and what do they indicate.



####[[⬆]](#toc) <a name='medium'>Medium Linux Questions:</a>

* What do the following commands do?
 * ```tee```从标准输入读入信息到文件和标准输出
 * ```awk```嘛，一言难尽
 * ```tr```更改字符
 * ```cut```从每行中删除（抽取）文本区域
 * ```tac```与cat相反，按行倒序输出文件到标准输出
 * ```curl```也是网络下载
 * ```wget```网络下载器	与curl区别：支持递归下载，不能指定URL序列，curl支持更多的协议，支持HTTP/1.1
 * ```watch```周期性执行一个程序，并全屏显示
 * ```tail```输出文件的最后的部分
* What does a ```&``` after a command do?
	后台执行进程
* What does ```& disown``` after a command do?
	将正在运行的前台进程放到后台运行
* What is a packet filter and how does it work?
	包过滤防火墙。。。
* What is Virtual Memory?
	虚拟内存是一种由操作系统接管的按需动态内存分配的方法，它允许程序不知不觉中使用大于实际物理空间大小的存储空间(其实是将程序需要的存储空间以页的形式分散存储在物理内存和磁盘上)。
* What is swap and what is it used for?
	在linux 系统中当物理内存不足的时候，系统会将那些内存中不活跃的分页置换到swap 空间。
* What is an A record, an NS record, a PTR record, a CNAME record, an MX record?
* Are there any other RRs and what are they used for?
* What is a Split-Horizon DNS?
* What is the sticky bit?
	防删除位
* What does the immutable bit to a file?
* What is the difference between hardlinks and symlinks? What happens when you remove the source to a symlink/hardlink?
	硬链接：共享inode号，不能跨文件系统建立
	符号链接：不同的inode号，可以跨文件系统建立
	删除源文件后，硬链接仍有效，而符号链接失效
* What is an inode and what fields are stored in an inode?
	inode包含文件的元信息，具体来说有以下内容：
　　    * 文件的字节数
　　    * 文件拥有者的User ID
　　    * 文件的Group ID
　　    * 文件的读、写、执行权限
　　    * 文件的时间戳，共有三个：ctime指inode创建时间，mtime指文件内容上一次修改的时间，atime指文件最后一次访问的时间。
　　    * 链接数，即有多少文件名指向这个inode
　　    * 文件数据block的位置
* Howto force/trigger a file system check on next reboot?
* What is SNMP and what is it used for?
* What is a runlevel and how to get the current runlevel?
* What is SSH port forwarding?
	端口转发。可以建立一条安全的SSH通道,并把任意的TCP连接放到这条通道中。
* What is the difference between local and remote port forwarding?
* What are the steps to add a user to a system without using useradd/adduser?
	vim /etc/passwd
* What is MAJOR and MINOR numbers of special files?
* Describe a scenario when you get a "filesystem is full" error, but 'df' shows there is free space.
	因为linux会给user预留分区大小为5%左右的空间，超出这一范围会提示已满，然而df仍然会显示有空闲
* Describe a scenario when deleting a file, but 'df' not showing the space being freed.
	如果一个进程在打开一个大文件时，这个文件被删除，则df不会显示空间被释放
* Describe how 'ps' works.
* What happens to a child process that dies and has no parent process to wait for it and what’s bad about this?
	僵尸进程。造成内存空间浪费。
* Explain briefly each one of the process states.
	阻塞，就绪，执行
* How to know which process listens on a specific port?
* You run a bash script and you want to see its output on your terminal and save it to a file at the same time. How could you do it?
* Explain what echo "1" > /proc/sys/net/ipv4/ip_forward does.
* Describe briefly the steps you need to take in order to create and install a valid certificate for the site https://foo.example.com.
* Can you have several HTTPS virtual hosts sharing the same IP?
* What is a wildcard certificate?
* Which Linux file types to you know?
* What is the difference between a process and a thread? And parent and child processes after a fork system call?
* What is the difference between exec and fork?
* What is "nohup" used for?
* What is the difference between these two commands?
 * ```myvar=hello```定义一个shell变量
 * ```export myvar=hello```添加一个新的环境变量
* How many NTP servers would you configure in your local ntp.conf?
* What does the column 'reach' mean in ```ntpq -p``` output?


####[[⬆]](#toc) <a name='hard'>Hard Linux Questions:</a>

* What is the difference between processes and threads?
* What is a tunnel and how you can bypass a http proxy?
* What is the difference between IDS and IPS?
* What shortcuts do you use on a regular basis?
* What is the Linux Standard Base?
* What is an atomic operation?
* Your freshly configured http server is not running after a restart, what can you do?
* What kind of keys are in ~/.ssh/authorized_keys and what it is this file used for?
* I've added my public ssh key into authorized_keys but I'm still getting a password prompt, what can be wrong?
* Did you ever create RPM's, DEB's or solaris pkg's?
* What does ```:(){ :|:& };:``` do on your system?
* How do you catch a Linux signal on a script?
	signal(sig,handler) or sigaction
* Can you catch a SIGKILL?
	NO
* What's happening when the Linux kernel is starting the OOM killer and how does it choose which process to kill first?
* Describe the linux boot process with as much detail as possible, starting from when the system is powered on and ending when you get a prompt.
* What's a chroot jail?
* When trying to umount a directory it says it's busy, how to find out which PID holds the directory?
* What's LD_PRELOAD and when it's used?
* You ran a binary and nothing happened. How would you debug this?
* What are cgroups? Can you specify a scenario where you could use them?


####[[⬆]](#toc) <a name='expert'>Expert Linux Questions:</a>

* A running process gets ```EAGAIN: Resource temporarily unavailable``` on reading a socket. How can you close this bad socket/file descriptor without killing the process?


####[[⬆]](#toc) <a name='network'>Networking Questions:</a>

* What is localhost and why would ```ping localhost``` fail?
* What is the similarity between "ping" & "traceroute" ? How is traceroute able to find the hops.
* What is the command used to show all open ports and/or socket connections on a machine?
* Is 300.168.0.123 a valid IPv4 address?
* Which IP ranges/subnets are "private" or "non-routable" (RFC 1918)?
* What is a VLAN?
* What is ARP and what is it used for?
* What is the difference between TCP and UDP?
* What is the purpose of a default gateway?
* What is command used to show the routing table on a Linux box?
* A TCP connection on a network can be uniquely defined by 4 things. What are those things?
* When a client running a web browser connects to a web server, what is the source port and what is the destination port of the connection?
* How do you add an IPv6 address to a specific interface?
* You have added an IPv4 and IPv6 address to interface eth0. A ping to the v4 address is working but a ping to the v6 address gives yout the response ```sendmsg: operation not permitted```. What could be wrong?
* What is SNAT and when should be used?
* Explain how could you ssh login into a Linux system that DROPs all new incomming packets using a SSH tunnel.
* How do you stop a DDoS?


####[[⬆]](#toc) <a name='mysql'>MySQL questions:</a>

* How do you create a user?
* How do you provide privileges to a user?
* What is the difference between a "left" and a "right" join?
* Explain briefly the differences between InnoDB and MyISAM.
* Describe briefly the steps you need to follow in order to create a simple master/slave cluster.
* Why should you run "mysql_secure_installation" after installing MySQL?
* How do you check which jobs are running?


####[[⬆]](#toc) <a name='devop'>DevOps Questions:</a>

* Can you describe your workflow when you create a script?
* What is GIT?
* What is a dynamically/statically linked file?
* What does "configure && make && make install"?
* What is puppet/chef/ansible used for?
* How do you create a new mysql user?
* How do you create a new postgres user?
* What is a virtual IP address? What is a cluster?
* How print the strings of printable characters in files?
* How look shared library dependencies?
* What is Automake and Autoconf?
* ./configure shows an error that libfoobar is missing on your system, how could you fix this, what could be wrong?
* Advantages/disadvantages of script vs compiled program.
* What's the relationship between continuous delivery and DevOps?
* What are the important aspects of a system of continous integration and deployment?


####[[⬆]](#toc) <a name='fun'>Fun Questions:</a>

* A careless sysadmin executes the following command: ```chmod 444 /bin/chmod ``` - what do you do to fix this?
* I've lost my root password, what can I do?
* I've rebooted a remote server but after 10 minutes I'm still not able to ssh into it, what can be wrong?
* If you were stuck on a desert island with only 5 command-line utilities, which would you choose?
* You come across a random computer and it appears to be a command console for the universe. What is the first thing you type?
* Tell me about a creative way that you've used SSH?
* You have deleted by error a running script, what could you do to restore it?


####[[⬆]](#toc) <a name='demo'>Demo Time:</a>

* Unpack test.tar.gz without man pages or google.
* Remove all "*.pyc" files from testdir recursively?
* Search for "my konfu is the best" in all *.py files.
* Replace the occurrence of "my konfu is the best" with "I'm a linux jedi master" in all *.txt files.
* Test if port 443 on a machine with IP address X.X.X.X is reachable.
* Get http://myinternal.webserver.local/test.html via telnet.
* How to send an email without a mail client, just on the command line?
* Write a ```get_prim``` method in python/perl/bash/pseudo.
* Find all files which have been accessed within the last 30 days.
* Explain the following command ```(date ; ps -ef | awk ‘{print $1}’ | sort | uniq | wc -l ) >> Activity.log```
* Write a script to list all the differences between two directories.
* In a log file with contents as ```<TIME> : [MESSAGE] : [ERROR_NO] - Human readable text``` display summary/count of specific error numbers that occured every hour or a specific hour.


####[[⬆]](#toc) <a name='references'>Other Great References:</a>

Some questions are 'borrowed' from other great references like:

* https://github.com/darcyclarke/Front-end-Developer-Interview-Questions
* https://github.com/kylejohnson/linux-sysadmin-interview-questions/blob/master/test.md
* https://github.com/gurmeet1109/docgurmeet/tree/master/InterviewQuestionsSamples
* http://slideshare.net/kavyasri790693/linux-admin-interview-questions
* https://github.com/gurmeet1109/docgurmeet/tree/master/InterviewQuestionsSamples
* https://github.com/kylejohnson/linux-sysadmin-interview-questions/blob/master/test.md
