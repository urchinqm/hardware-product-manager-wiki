# eMMC

## 1. 基本概念

[COMMON] eMMC（embedded MultiMediaCard，嵌入式多媒体卡，把 NAND Flash 和控制器封装在一起的嵌入式存储器）常用于中低复杂度嵌入式系统的系统盘和数据盘。

[COMMON] Managed Flash（托管闪存，内部控制器负责坏块管理、纠错和磨损均衡的闪存方案）是 eMMC 的核心特征。

## 2. 工作原理

[COMMON] eMMC 通过标准 eMMC 接口连接主控，内部控制器管理 NAND Flash 的物理特性，对主机呈现块设备。

[COMMON] 主控通常在 eMMC 上划分 Boot Partition（启动分区）、User Data Area（用户数据区）和 RPMB（Replay Protected Memory Block，重放保护内存块，用于安全数据存储）。

## 3. 核心参数

[COMMON] 核心参数包括容量、eMMC 标准版本、顺序读写速度、随机读写性能、总线宽度、工作电压、寿命等级、温度等级、封装和供货周期。

[COMMON] 速度和寿命必须以具体颗粒型号、测试条件和主控配置为准，不能只按接口版本判断。

## 4. 参数影响

[COMMON] 容量影响系统分区、日志和用户数据空间；顺序写速度影响升级和大文件写入；随机性能影响系统启动和应用响应；寿命影响日志和频繁写入场景。

[COMMON] eMMC vs SD Card（Secure Digital Card，安全数字卡，可插拔存储卡）的差异是 eMMC 焊接在板上，连接可靠性和系统盘场景更稳定；SD Card 更适合可插拔扩展。

## 5. 优点

[COMMON] eMMC 集成控制器，降低主控侧 NAND 管理复杂度。

[COMMON] eMMC 成本、生态和软件支持成熟，适合大量嵌入式系统。

## 6. 局限性

[COMMON] eMMC 性能和并发能力通常低于 UFS。

[COMMON] eMMC 焊接在板上，现场更换不如 SD Card 方便。

## 7. 产品经理关注点

[COMMON] 产品经理需要确认系统镜像、OTA 双分区、日志、用户数据和预留空间是否满足生命周期需求。

[COMMON] 对长期运行设备，应定义写入量预算和寿命风险提示。

## 8. 常见应用场景

[COMMON] eMMC 常用于 Android 设备、Linux 网关、车载终端、摄像头、智能屏和工业控制主板。

## 9. 需求文档需要明确内容

[COMMON] PRD 需要明确总容量、系统占用、用户可用空间、分区方案、升级冗余、日志保留、恢复出厂和数据清除策略。

[COMMON] 文件系统可选 ext4（Fourth Extended Filesystem，Linux 常用日志文件系统）、FAT32（File Allocation Table 32，兼容性强但单文件大小受限的文件系统）或 exFAT（Extended File Allocation Table，适合大文件和可移动存储的文件系统），具体由操作系统和产品需求决定。

## 10. 异常状态设计

[COMMON] eMMC 异常状态包括空间不足、分区损坏、只读模式、写入失败、升级中断、寿命接近上限和安全分区访问失败。

[COMMON] 产品应定义系统盘保护、日志限额、恢复模式和售后数据导出方式。
