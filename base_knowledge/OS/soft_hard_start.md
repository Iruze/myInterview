# 软启动 vs 硬启动
- 区别：硬启动包括各种**设备的自检**和**系统/内核引导**，软启动不需要重新自检这些设备

1). linux启动的过程:

**BIOS加电自检** 
<details>
<summary>展开</summary>
  
包括检测CPU、内存、风扇、显示设备等是否存在与能否工作；

</details>

**Bootloader引导系统**
<details>
<summary>展开</summary>

根据BIOS设置的启动顺序寻找第一个可引导设备的boot loader(位于MBR中)。Bootloader允许用户选择要启动的系统或不同的内核版本，然后把用户选定的内核装载到特定的内存空间，解压、展开内核，并把控制权移交给内核；

 MBR：主引导记录
                446：boot loader
                64：磁盘分区表

</details>

**kernel自身初始化**
<details>
<summary>展开</summary>
  
kernel自身初始化，探测可识别到的硬件设备；
                加载硬件驱动程序；(有可能会借助于ramdisk加载驱动程序)
                以只读方式挂载根文件系统(initrd阶段)；(之后会重新以读写方式挂载根文件系统)
                运行用户空间的第一个应用程序：/sbin/init(centos 5)

</details>

**rootfs用户空间程序**
<details>
  <summary>展开</summary>
  
  系统运行起来之后，在某一时刻要么是运行内核代码，要么是执行rootfs上某个路径上的某个程序的用户代码；
        kernel：进程管理、内存管理、网络管理、驱动程序、文件系统等、安全功能；
        rootfs：用户空间
        
</details>
