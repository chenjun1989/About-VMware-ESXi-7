How to add vib drivers to that ESXi7 series Images./怎么在ESXi7系列镜像里添加网卡vib驱动。

在此感谢 sh1njp  的文章，并借鉴了其很多URL，使我受益匪浅，https://github.com/sh1njp/esxi7_custom

概要：
本人是从VMware官网上面下载的最新版ESXi ISO镜像（2021.10.6）.


操作办法以及环境：
Windows 10/Server 2019 (补丁打至2021.10.6)  使用「ESXi-Customizer-PS」最新版脚本融合产生的新镜像。


VMWare PowerCLI的使用
通过使用管理员启动PowerShell后执行： 

Install-Module -Name VMware.PowerCLI -AllowClobber 回车

透过此URL 进行下载ESXI-Customizer-PS.ps1       https://raw.githubusercontent.com/VFrontDe/ESXi-Customizer-PS/master/ESXi-Customizer-PS.ps1


VIB驱动下载
https://flings.vmware.com/community-networking-driver-for-esxi#requirements
文件全名为：Net-Community-Driver_1.2.0.0-1vmw.700.1.0.15843807_18028830.zip
该驱动支持的网卡型号可以参考URL   https://flings.vmware.com/community-networking-driver-for-esxi#requirements


重中之重，如何归纳数据文件进此文件夹


位于桌面新建一个文件夹PKG,路径为C:\Users\Administrator\Desktop\PKG
拷贝文件进此文件夹：

第一个：Net-Community-Driver_1.2.0.0-1vmw.700.1.0.15843807_18028830.zip

第二个：ESXi-Customizer-PS.ps1

第三个：VMware-VMvisor-Installer-7.0U2a-17867351.x86_64.iso

然后执行此命令：.\ESXi-Customizer-PS.ps1 -v70 -pkgDir C:\Users\Administrator\Desktop\PKG -NSC


此期间需要耐心等待一段时间，生成好的文件名为：ESXi-7.0U3-18644231-standard-customized.iso


至此告一段落，再次感谢sh1njp 。


ありがとうございます！sh1njp

感谢！  sh1njp

Thanks a lot! sh1njp
