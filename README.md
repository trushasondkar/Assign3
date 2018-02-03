# Assign3
## Spring 2018

The purpose of this exercise is to get comfortable creating scripts using vim on a server, while teaching you the remainder of bash scripting you'll need as a foundation for this course. The scripts themselves are not particularly exciting but they are the building blocks you'll need.  You will be asked to create 11 scripts, which all come from http://dtg.usc.edu/tgrn510/index.php/bash-scripting/.  These are to all be placed in your "bin" directory. The results of running these should be put into a forked version of this github. 

The final question is considerably more difficult and requires you to put concepts together you have learned at this point.

 Completion means the scripts work in your home directory and you have put the results in your github where you will replace the placeholder text with the results from running the script. For exampler, you should replace

*REPLACE WITH RESULTS*

with codeblock text using backticks, which show both the program being called in trgn510.pmed.io and the result.  After, it should be:

`
davidcraig@trgn510:~/bin ls | test.sh
TEST.SH
`

### 1
Please create pointless.sh, changing from printing your hostname with $HOSTNAME, to your $USER

`
[sondkar@trgn510 ~]$ sh pointless.sh
trgn510.pmed.io
`

### 2
Please create quotequotes.sh, please add 1 additional lines that prints the process id of the current script using a special variable in a sentence: "The process id for this script is **235**'

`
[sondkar@trgn510 ~]$ sh quotequotes.sh
The process id for this script is 14513
`

### 3
Please create processes.sh.  Modify it such that it prints the top 5 CPU consuming processes

`
[sondkar@trgn510 ~]$ top -bn 1 | grep "^ " | awk '{ printf("%-8s  %-8s \n", $12, $9); }' | head -6
COMMAND   %CPU
systemd   0.0
kthreadd  0.0
ksoftirqd/0  0.0
kworker/0:0H  0.0
migration/0  0.0
`

### 4
Please create makeupper.sh.  Modify it to return lower case results, and change the name to makelower.sh
`
[sondkar@trgn510 ~]$ ps -ef | ./makelower.sh
uid        pid  ppid  c stime tty          time cmd
root         1     0  0 jan19 ?        00:03:02 /usr/lib/systemd/systemd --switched-root --system --deserialize 19
root         2     0  0 jan19 ?        00:00:00 [kthreadd]
root         3     2  0 jan19 ?        00:00:00 [ksoftirqd/0]
root         5     2  0 jan19 ?        00:00:00 [kworker/0:0h]
root         7     2  0 jan19 ?        00:00:01 [migration/0]
root         8     2  0 jan19 ?        00:00:00 [rcu_bh]
root         9     2  0 jan19 ?        00:00:57 [rcu_sched]
root        10     2  0 jan19 ?        00:00:05 [watchdog/0]
root        11     2  0 jan19 ?        00:00:04 [watchdog/1]
root        12     2  0 jan19 ?        00:00:02 [migration/1]
root        13     2  0 jan19 ?        00:00:02 [ksoftirqd/1]
root        15     2  0 jan19 ?        00:00:00 [kworker/1:0h]
root        17     2  0 jan19 ?        00:00:00 [kdevtmpfs]
root        18     2  0 jan19 ?        00:00:00 [netns]
root        19     2  0 jan19 ?        00:00:00 [xenwatch]
root        20     2  0 jan19 ?        00:00:00 [xenbus]
root        22     2  0 jan19 ?        00:00:00 [khungtaskd]
root        23     2  0 jan19 ?        00:00:00 [writeback]
root        24     2  0 jan19 ?        00:00:00 [kintegrityd]
root        25     2  0 jan19 ?        00:00:00 [bioset]
root        26     2  0 jan19 ?        00:00:00 [kblockd]
root        27     2  0 jan19 ?        00:00:00 [md]
root        33     2  0 jan19 ?        00:01:06 [kswapd0]
root        34     2  0 jan19 ?        00:00:00 [ksmd]
root        35     2  0 jan19 ?        00:00:03 [khugepaged]
root        36     2  0 jan19 ?        00:00:00 [crypto]
root        44     2  0 jan19 ?        00:00:00 [kthrotld]
root        46     2  0 jan19 ?        00:00:00 [kmpath_rdacd]
root        47     2  0 jan19 ?        00:00:00 [kpsmoused]
root        48     2  0 jan19 ?        00:00:00 [ipv6_addrconf]
root        67     2  0 jan19 ?        00:00:00 [deferwq]
root       160     2  0 jan19 ?        00:00:13 [kauditd]
root       223     2  0 jan19 ?        00:00:00 [ata_sff]
root       224     2  0 jan19 ?        00:00:00 [scsi_eh_0]
root       225     2  0 jan19 ?        00:00:00 [scsi_tmf_0]
root       226     2  0 jan19 ?        00:00:00 [scsi_eh_1]
root       227     2  0 jan19 ?        00:00:00 [scsi_tmf_1]
root       251     2  0 jan19 ?        00:00:00 [bioset]
root       252     2  0 jan19 ?        00:00:00 [xfsalloc]
root       253     2  0 jan19 ?        00:00:00 [xfs_mru_cache]
root       254     2  0 jan19 ?        00:00:00 [xfs-buf/xvda2]
root       255     2  0 jan19 ?        00:00:00 [xfs-data/xvda2]
root       256     2  0 jan19 ?        00:00:00 [xfs-conv/xvda2]
root       257     2  0 jan19 ?        00:00:00 [xfs-cil/xvda2]
root       258     2  0 jan19 ?        00:00:00 [xfs-reclaim/xvd]
root       259     2  0 jan19 ?        00:00:00 [xfs-log/xvda2]
root       260     2  0 jan19 ?        00:00:00 [xfs-eofblocks/x]
root       261     2  0 jan19 ?        00:04:06 [xfsaild/xvda2]
root       328     1  0 jan19 ?        00:03:50 /usr/lib/systemd/systemd-journald
root       369     1  0 jan19 ?        00:00:00 /usr/lib/systemd/systemd-udevd
root       399     1  0 jan19 ?        00:00:34 /sbin/auditd
root       400     2  0 jan19 ?        00:00:00 [ttm_swap]
root       459     2  0 jan19 ?        00:00:00 [edac-poller]
root       507     2  0 jan19 ?        00:00:00 [kworker/0:1h]
root       509     1  0 jan19 ?        00:00:14 /usr/lib/systemd/systemd-logind
root       510     1  0 jan19 ?        00:00:50 /usr/sbin/irqbalance --foreground
dbus       512     1  0 jan19 ?        00:00:29 /bin/dbus-daemon --system --address=systemd: --nofork --nopidfile --systemd-activation
chrony     514     1  0 jan19 ?        00:00:02 /usr/sbin/chronyd
polkitd    524     1  0 jan19 ?        00:00:01 /usr/lib/polkit-1/polkitd --no-debug
root       526     1  0 jan19 ?        00:02:27 /usr/sbin/rsyslogd -n
root       541     1  0 jan19 ?        00:00:01 /usr/bin/python -es /usr/sbin/firewalld --nofork --nopid
root       543     1  0 jan19 ?        00:00:19 /usr/sbin/networkmanager --no-daemon
root       666   543  0 jan19 ?        00:00:01 /sbin/dhclient -d -q -sf /usr/libexec/nm-dhcp-helper -pf /var/run/dhclient-eth0.pid -lf /var/lib/networkmanager/dhclient-5fb06bd0-0bb0-7ffb-45f1-d6edd65f3e03-eth0.lease -cf /var/lib/networkmanager/dhclient-eth0.conf eth0
root       863     1  0 jan19 ?        00:01:44 /usr/bin/python -es /usr/sbin/tuned -l -p
root       865     1  0 jan19 ?        00:00:52 /usr/sbin/httpd -dforeground
root       968     1  0 jan19 ?        00:00:38 /usr/sbin/sshd -d
root       969     1  0 jan19 ttys0    00:00:00 /sbin/agetty --keep-baud 115200 38400 9600 ttys0 vt220
root       974     1  0 jan19 ?        00:00:07 /usr/sbin/crond -n
root       977     1  0 jan19 tty1     00:00:00 /sbin/agetty --noclear tty1 linux
root       996     1  0 jan19 ?        00:00:00 /usr/sbin/dovecot -f
root      1024     1  0 jan19 ?        00:00:00 rhnsd
dovecot   1034   996  0 jan19 ?        00:00:00 dovecot/anvil
root      1035   996  0 jan19 ?        00:00:00 dovecot/log
mysql     1174     1  0 jan19 ?        00:00:00 /bin/sh /usr/bin/mysqld_safe --basedir=/usr
mysql     1344  1174  0 jan19 ?        00:07:00 /usr/sbin/mysqld --basedir=/usr --datadir=/var/lib/mysql --plugin-dir=/usr/lib64/mysql/plugin --log-error=/var/log/mysqld.log --pid-file=/var/run/mysqld/mysqld.pid --socket=/var/lib/mysql/mysql.sock
root      1414     2  0 jan19 ?        00:00:01 [kworker/1:1h]
root      1528     2  0 jan19 ?        00:00:20 [jbd2/xvdf-8]
root      1529     2  0 jan19 ?        00:00:00 [ext4-rsv-conver]
root      4194     2  0 04:31 ?        00:00:00 [kworker/0:0]
apache    5583   865  0 jan29 ?        00:00:00 /usr/sbin/httpd -dforeground
apache    5584   865  0 jan29 ?        00:00:00 /usr/sbin/httpd -dforeground
apache    5585   865  0 jan29 ?        00:00:00 /usr/sbin/httpd -dforeground
apache    5586   865  0 jan29 ?        00:00:00 /usr/sbin/httpd -dforeground
apache    5587   865  0 jan29 ?        00:00:00 /usr/sbin/httpd -dforeground
root      6421     2  0 feb02 ?        00:00:00 [kworker/u30:1]
apache   11051   865  0 feb02 ?        00:00:00 /usr/sbin/httpd -dforeground
apache   11052   865  0 feb02 ?        00:00:00 /usr/sbin/httpd -dforeground
root     19527   968  0 02:00 ?        00:00:00 sshd: yuxinjin [priv]
yuxinjin 19534 19527  0 02:00 ?        00:00:00 sshd: yuxinjin@pts/1
yuxinjin 19535 19534  0 02:00 pts/1    00:00:00 -bash
root     22731   968  0 03:00 ?        00:00:00 sshd: sunying [priv]
sunying  22740 22731  0 03:00 ?        00:00:00 sshd: sunying@pts/5
sunying  22741 22740  0 03:00 pts/5    00:00:00 -bash
root     24330   968  0 03:29 ?        00:00:00 sshd: sondkar [priv]
sondkar  24339 24330  0 03:29 ?        00:00:02 sshd: sondkar@pts/0
sondkar  24340 24339  0 03:29 pts/0    00:00:00 -bash
root     24812   968  0 03:37 ?        00:00:00 sshd: zhaniyaz [priv]
zhaniyaz 24823 24812  0 03:37 ?        00:00:00 sshd: zhaniyaz@pts/4
zhaniyaz 24824 24823  0 03:37 pts/4    00:00:00 -bash
root     25701     2  0 04:40 ?        00:00:00 [kworker/1:1]
apache   25847   865  0 jan29 ?        00:00:00 /usr/sbin/httpd -dforeground
root     26021   968  0 03:59 ?        00:00:00 sshd: zhaniyaz [priv]
zhaniyaz 26031 26021  0 03:59 ?        00:00:00 sshd: zhaniyaz@pts/6
zhaniyaz 26032 26031  0 03:59 pts/6    00:00:00 -bash
root     26069     2  0 04:45 ?        00:00:00 [kworker/1:2]
root     26135     2  0 04:01 ?        00:00:00 [kworker/0:1]
sunying  26774 22741  0 04:55 pts/5    00:00:00 vim count_by_to.sh
root     26796     2  0 04:56 ?        00:00:00 [kworker/1:0]
zhaniyaz 26858 26032  0 04:56 pts/6    00:00:00 vim count_by_to.sh
root     26882   968  0 04:57 ?        00:00:00 sshd: root [priv]
sshd     26883 26882  0 04:57 ?        00:00:00 sshd: root [net]
sondkar  26895 24340  0 04:57 pts/0    00:00:00 ps -ef
sondkar  26896 24340  0 04:57 pts/0    00:00:00 /bin/bash ./makelower.sh
sondkar  26897 26896  0 04:57 pts/0    00:00:00 cat /dev/stdin
sondkar  26898 26896  0 04:57 pts/0    00:00:00 tr a-z a-z
root     26976     2  0 04:14 ?        00:00:00 [kworker/u30:0]
root     32625   968  0 feb02 ?        00:00:00 sshd: davidcraig [priv]
davidcr+ 32634 32625  0 feb02 ?        00:00:00 sshd: davidcraig@pts/2
davidcr+ 32635 32634  0 feb02 pts/2    00:00:00 -bash
davidcr+ 32695 32635  0 feb02 pts/2    00:00:00 ssh varshagi@trgn510.pmed.io
[sondkar@trgn510 ~]$
`

### 5
Referring to math.sh, create a script called add.sh that takes two inputs and adds them, **add.sh 5 3** would print 8

`
[sondkar@trgn510 ~]$ ./add.sh 9 9
18
`

### 6
Create a program "mb_or_kb.sh", referring to bigornot.sh and useful.sh, create a script called big file that checks to see if the file exists provided as the first argument exists, and if it exists then gets the filesize, storing it as a variable. I have not provided you with a way to get filesize in exercise, and expect you to search web for a way.  The program then checks to see if the size is greater than 1,000,000.  If its less then 1,000,000, it prints the number of kilobytes (divide by 1000) followed by "kB".  If its greater than 1,000,000, then print the number of megabytes followed by "MB".

`
[sondkar@trgn510 ~]$ ./mb_or_kb.sh ~/.bashrc
0.231 KB
`

### 7
Create a program "count_by_to.sh", referring to count.sh.  The file should take two arguments, and should count jumping by the first argument until the second argument is reached, starting at 0.  For example, *count.sh 2 10* would print 0 2 4 6 8 10

`
[sondkar@trgn510 ~]$ ./count_by_to.sh 2 10
0
2
4
6
8
10
`

### 9
Please create whatgene.sh.  Please edit such that the function print_gene, prints upper case of the input.

`
[sondkar@trgn510 ~]$ sh whatgene.sh
mygene PTEN
mygene JUPITER
`

### 10
Please create a bash shell called "genotype.sh" that takes a VCF as argument 1, and prints space delimited chromosome, position, reference, alternative, and genotype for all genotypes in VCF.

`
[sondkar@trgn510 ~]$ sh genotype.sh HG001_GRCh37_GIAB_highconf_CG-IllFB-IllGATKHC-Ion-10X-SOLID_CHROM1-X_v.3.3.2_highconf_PGandRTGphasetransfer.vcf | head -n 10
#CHROM POS REF ALT FORMAT
1 239339 A G GT:DP:ADALL:AD:GQ:IGT:IPS:PS
1 239482 G T GT:DP:ADALL:AD:GQ:IGT:IPS:PS
1 240147 C T GT:DP:ADALL:AD:GQ:IGT:IPS:PS
1 240898 T G GT:DP:ADALL:AD:GQ:IGT:IPS:PS
1 567239 CG C GT:DP:ADALL:AD:GQ:IGT:IPS:PS
1 568745 C CCA GT:DP:ADALL:AD:GQ:IGT:IPS:PS
1 837214 G C GT:DP:ADALL:AD:GQ:IGT:IPS:PS
1 838153 CA C GT:DP:ADALL:AD:GQ:IGT:IPS:PS
1 842825 A G GT:DP:ADALL:AD:GQ:IGT:IPS:PS
`

