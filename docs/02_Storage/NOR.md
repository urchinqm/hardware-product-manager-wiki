# NOR Flash

## 1. 基本概念

[COMMON] NOR Flash（或非型闪存，一种支持高效随机读取并常用于启动代码和固件存储的非易失性存储器）适合保存 Bootloader、固件和少量关键配置。

[COMMON] XIP（Execute In Place，片上或外部存储中原地执行代码）是 NOR Flash 的典型能力之一。

## 2. 工作原理

[COMMON] NOR Flash 支持按地址随机读取，系统可以像访问存储映射空间一样读取代码或数据。

[COMMON] 写入前仍需要擦除，擦除通常按 Sector（扇区，擦除操作的基本区域）或 Block（块，较大的擦除区域）进行。

## 3. 核心参数

[COMMON] 核心参数包括容量、接口类型、读取速度、页编程时间、扇区擦除时间、擦写寿命、数据保持时间、工作电压、封装和温度等级。

[COMMON] 常见接口包括 SPI NOR（Serial Peripheral Interface NOR，通过 SPI 总线访问的 NOR Flash）和 Parallel NOR（并行 NOR，通过并行地址/数据总线访问的 NOR Flash）。

## 4. 参数影响

[COMMON] 读取速度影响启动时间和 XIP 运行效率；擦除时间影响升级和配置写入体验；容量影响双备份固件和回滚空间；擦写寿命影响频繁配置写入的可靠性。

[COMMON] NOR Flash vs NAND Flash 的核心差异是 NOR 随机读和启动友好，NAND 容量密度和单位容量成本更适合大容量数据。

## 5. 优点

[COMMON] NOR Flash 随机读取能力强，适合启动代码和固件执行。

[COMMON] NOR Flash 管理复杂度通常低于裸 NAND Flash。

## 6. 局限性

[COMMON] NOR Flash 单位容量成本通常高于 NAND Flash，容量扩展不适合大文件存储。

[COMMON] NOR Flash 写入和擦除速度不是其优势，不适合高频大量写入日志。

## 7. 产品经理关注点

[COMMON] 产品经理应明确 NOR Flash 是用于启动、固件、配置还是日志。

[COMMON] 如果用于 OTA，需要定义 A/B 分区、回滚、校验和升级失败恢复。

## 8. 常见应用场景

[COMMON] NOR Flash 常用于 MCU 固件、Bootloader、BIOS 类启动代码、设备配置、校准参数和小容量关键数据。

## 9. 需求文档需要明确内容

[COMMON] PRD 需要明确固件大小、备份分区、升级策略、配置写入频率、校准数据保护和异常恢复路径。

[COMMON] 需要写清楚掉电期间正在写入配置时的系统行为。

## 10. 异常状态设计

[COMMON] NOR Flash 异常状态包括扇区擦除失败、页编程失败、固件校验失败、配置损坏、升级中断和启动区损坏。

[COMMON] 关键启动数据应设计只读保护、备份区或恢复模式。
