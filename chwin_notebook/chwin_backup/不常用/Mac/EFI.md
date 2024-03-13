EFI

# 必装
## Lilu.kext

## VirtualSMC.kext
   内核驱动，替代Fakesmc，将更好的兼容未来macOS版本。要把 VirtualSMC.efi 放到 Drivers 目录一起使用。
   https://github.com/acidanthera/VirtualSMC/releases
## WhateverGreen.kext
   已经更新，合并了`igfx`、`ngfx`，以及`Shiki`，启动参数和以前一样，不论`A`卡、`N`卡还是`Intel`核心显卡，都建议使用
## USBInjectAll.kext

# 主板
- `XHCI`开头的三个`kext`对应适用于`x99`、`200`和`300`系主板，非此类主板删除

# 显卡
## AzulPatcher4600.kext
   只适用于核心显卡`HD4600`，其他型号删除


# 声卡
  - `AppleALC.kext`和`VoodooHDA-2.9.1.kext`任选其一
## AppleALC.kext
   开源的黑苹果声卡驱动补丁，需要配合lilu.kext来驱动你的声卡。
   https://github.com/acidanthera/AppleALC/releases # 下载址址
   https://github.com/acidanthera/AppleALC/wiki/Supported-codecs #驱动支持的硬件型号列表
   https://github.com/acidanthera/AppleALC # 项目地址
## VoodooHDA
   黑苹果万能声卡驱动


# 网卡
## 无线网卡
### Wireless.USB.Adapter.Clover-V7.zip
    REALTEK无线网卡驱动，包括安装程序及通过`CLOVER`加载的驱动
### ATH9KFixup.kext
    用于驱动`AR946x`、`AR956X`、`AR9485`高通无线网卡，合理选用

## 有线网卡
   - RTL8100.kext
     RTL8107E、RTL810X、RTL8139
   - RTL8111.kext 
     Realtek RTL8111/8168 B/C/D/E/F/G/H
   - IntelMausiEthernet.kext
     82578LM、82578LC、82578DM、82578DC、82579LM、82579V、I217LM、I217V、I218LM、I218V、I218LM2、I218V2、I218LM3、I219V、I219LM、I219V2、I219LM2、I219LM2
   - AtherosE2200Ethernet.kext
     AR816x、AR817x、Killer E220x、Killer E2400、Killer E2500
   - SmallTree-Intel-211-AT-PCIe-GBE.kext
     Intel I211
   - AppleIntelE1000.kext
     Intel系列 82540, 82541, 82542, 82543, 82544, 82545, 82546, 82547, 82578 (P55/H55)  82579 (P67/H67) 82574L 82571 82572 82573 82574 82583 I217V
   - AppleIGB.kext
     Intel 82575, 82576, 82580, dh89xxcc, i350, i210 and i211 |
   - ALXEthernet.kext
     Atheros alx Ethernet
   - FakePCIID_BCM57XX_as_BCM57765.kext
     BCM57XX
   - FakePCIID_Intel_GbX.kext
     Small Tree drivers for Intel chipset
    
- `FakePCIID_BCM57XX_as_BCM57765.kext`详细支持列表
  - Broadcom NetXtreme BCM5700 Gigabit Ethernet [14e4:1644]
  - Broadcom NetXtreme BCM5701 Gigabit Ethernet PCIe [14e4:1645]
  - Broadcom NetXtreme BCM5702 Gigabit Ethernet PCIe [14e4:1646]
  - Broadcom NetXtreme BCM5703 Gigabit Ethernet PCIe [14e4:1647]
  - Broadcom NetXtreme BCM5717 Gigabit Ethernet PCIe [14e4:1655]
  - Broadcom NetXtreme BCM5717 Gigabit Ethernet PCIe [14e4:1665]
  - Broadcom NetXtreme BCM5718 Gigabit Ethernet PCIe [14e4:1656]
  - Broadcom NetXtreme BCM5719 Gigabit Ethernet PCIe [14e4:1657]
  - Broadcom NetXtreme BCM5725 Gigabit Ethernet PCIe [14e4:1643]
  - Broadcom NetXtreme BCM5727 Gigabit Ethernet PCIe [14e4:16f3]
  - Broadcom NetXtreme BCM5761 10/100/1000BASE-T Ethernet [14e4:1688]
  - Broadcom NetXtreme BCM5762 Gigabit Ethernet PCIe [14e4:1687]
  - Broadcom NetXtreme BCM57760 Gigabit Ethernet PCIe [14e4:1690]
  - Broadcom NetXtreme BCM57764 Gigabit Ethernet PCIe [14e4:1642]
  - Broadcom NetXtreme BCM57767 Gigabit Ethernet PCIe [14e4:1683]
  - Broadcom NetLink BCM57781 Gigabit Ethernet PCIe [14e4:16b1]
  - Broadcom NetXtreme BCM57782 Gigabit Ethernet PCIe [14e4:16b7]
  - Broadcom NetLink BCM57785 Gigabit Ethernet PCIe [14e4:16b5] -- Confirmed
  - Broadcom NetXtreme BCM57786 Gigabit Ethernet PCIe [14e4:16b3] -- Confirmed
  - Broadcom NetXtreme BCM57787 Gigabit Ethernet PCIe [14e4:1641]
  - Broadcom NetLink BCM57788 Gigabit Ethernet PCIe [14e4:1691]
  - Broadcom NetLink BCM57790 Gigabit Ethernet PCIe [14e4:1694]
  - Broadcom NetLink BCM57791 Gigabit Ethernet PCIe [14e4:16b2]
  - Broadcom NetLink BCM57795 Gigabit Ethernet PCIe [14e4:16b6]
  - Broadcom NetLink BCM5785 Gigabit Ethernet [14e4:1699]
  - Broadcom NetLink BCM5785 Fast Ethernet [14e4:16a0]
  - Broadcom NetLink BCM5787M Gigabit Ethernet PCI Express [14e4:1693]
  - Broadcom Network Adapter [14e4:1689]

----

- `FakePCIID_Intel_GbX.kext`详细支持列表
  - Supported devices for SmallTreeIntel8254x.kext:
  - 8086:1010 82546EB Gigabit Ethernet Controller (Copper)
  - 8086:1011 82545EM Gigabit Ethernet Controller (Fiber)
  - 8086:1012 82546EB Gigabit Ethernet Controller (Fiber)
  - 8086:101d 82546EB Gigabit Ethernet Controller
  - 8086:1026 82545GM Gigabit Ethernet Controller
  - 8086:1027 82545GM Gigabit Ethernet Controller
  - 8086:1028 82545GM Gigabit Ethernet Controller
  - 8086:105e 82571EB Gigabit Ethernet Controller (Also covered by AppleIntel8254XEthernet.kext)
  - 8086:105f 82571EB Gigabit Ethernet Controller
  - 8086:1079 82546GB Gigabit Ethernet Controller
  - 8086:107a 82546GB Gigabit Ethernet Controller
  - 8086:107b 82546GB Gigabit Ethernet Controller
  - 8086:107c 82541PI Gigabit Ethernet Controller
  - 8086:107d 82572EI Gigabit Ethernet Controller (Copper)
  - 8086:107e 82572EI Gigabit Ethernet Controller (Fiber)
  - 8086:10a4 82571EB Gigabit Ethernet Controller
  - 8086:10b5 82546GB Gigabit Ethernet Controller (Copper)
  - 8086:10b9 82572EI Gigabit Ethernet Controller (Copper)
  - 8086:10bc 82571EB Gigabit Ethernet Controller (Copper)

  - SmallTreeIntel82576.kext:
  - 8086:1521 I350 Gigabit Network Connection
  - 8086:1522 I350 Gigabit Fiber Network Connection
  - 8086:1533 I210 Gigabit Network Connection (Also covered by AppleIntelI210Ethernet.kext)

- SmallTreeIntel8259x.kext
  - 8086:10c6 82598EB 10-Gigabit AF Dual Port Network Connection
  - 8086:10c7 82598EB 10-Gigabit AF Network Connection
  - 8086:10c8 82598EB 10-Gigabit AT Network Connection
  - 8086:10ec 82598EB 10-Gigabit AT CX4 Network Connection
  - 8086:10d8 82599EB 10 Gigabit Network Connection
  - 8086:10fb 82599ES 10-Gigabit SFI/SFP+ Network Connection
  - 8086:10f1 82598EB 10-Gigabit AF Dual Port Network Connection
  - 8086:151c 82599 10 Gigabit TN Network Connection
  - 8086:150b 82598EB 10-Gigabit AT2 Server Adapter
  - 8086:1528 Ethernet Controller 10-Gigabit X540-AT2
  - 8086:10fc 82599 10 Gigabit Dual Port Network Connection
  - 8086:1560 Ethernet Controller X540

# 存储
## NVMeFix.kext
   黑苹果NVMe提升兼容性驱动

# 外设
- `VoodooPS2Controller.kext`和`ApplePS2SmartTouchPad.kext`两者选其一，不可全用
- `NoTouchID`用于禁止`TouchID`的检测，合理选用



# 笔记本
## 电量显示
- `ACPIBatteryManager.kext`用于实现电量显示，如遇五国卡`BAT0`之类的请删除
