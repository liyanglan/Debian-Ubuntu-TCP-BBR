# Debian-Ubuntu-TCP-BBR-
Debian/Ubuntu TCP BBR 改进版/增强版/魔改版
背景:

原版的BBR对于我们来说,速度不太稳定. 通过修改BBR源码,调整参数,使其更强劲.


更新: [2017.07.25] 修复一个由检测gcc版本引起的不可预料的错误. [2017.07.15] 

自动检测gcc版本,如果gcc版本大于4.9的将不会再安装gcc. [2017.07.12] 支持用户自行指定内核版本(需要与 -f 命令同时使用).


准备:

使用前,请确认能够开启BBR. 可参考: Debian/Ubuntu 开启 TCP BBR 拥塞算法 或者直接执行此命令进行开启.

wget --no-check-certificate -qO 'BBR.sh' 'https://moeclub.org/attachment/LinuxShell/BBR.sh' && chmod a+x BBR.sh && bash BBR.sh -f


注意:执行此命令会自动重启.

一键地址:

wget --no-check-certificate -qO 'BBR_POWERED.sh' 'https://moeclub.org/attachment/LinuxShell/BBR_POWERED.sh' && chmod a+x BBR_POWERED.sh && bash BBR_POWERED.sh


指定内核版本(以v4.11.9内核版本为例):

wget --no-check-certificate -qO 'BBR_POWERED.sh' 'https://moeclub.org/attachment/LinuxShell/BBR_POWERED.sh' && chmod a+x BBR_POWERED.sh && bash BBR_POWERED.sh -f v4.11.9



说明:

执行过程中会重新编译模块.

模块默认为开机自动加载.

模块名称:tcp_bbr_powered

可用 modprobe tcp_bbr_powered 命令进行加载模块.

可执行 lsmod |grep 'bbr_powered'

结果不为空,则加载模块成功

可执行 sysctl -w net.ipv4.tcp_congestion_control=bbr_powered 使用此模块.

以上只是说明,直接使用一键脚本即可.
