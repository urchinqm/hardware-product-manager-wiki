# MCU

## 1. 基本概念

[COMMON] MCU（Microcontroller Unit，微控制器单元，把 CPU、存储器、外设接口和基础控制电路集成在单芯片内的控制器）主要用于确定性控制、低功耗控制和外设管理。

[COMMON] CPU（Central Processing Unit，中央处理器，用于执行指令和控制运算流程）是 MCU 内部的核心计算单元，但 MCU 不等同于 CPU。

## 2. 工作原理

[COMMON] MCU 上电后从片上 Flash（Flash Memory，非易失性闪存，用于断电保存固件）或外部存储读取启动代码，初始化时钟、电源、GPIO（General Purpose Input/Output，通用输入输出接口）和外设，然后进入主循环或 RTOS（Real-Time Operating System，实时操作系统）任务调度。

[COMMON] MCU 通常通过 Interrupt（中断，硬件或软件事件触发 CPU 暂停当前流程并执行指定处理函数的机制）响应按键、通信、定时器和传感器事件。

## 3. 核心参数

[COMMON] 产品经理需要关注的 MCU 参数包括内核架构、主频、片上 Flash 容量、SRAM（Static Random Access Memory，静态随机存取存储器，用于运行时数据存放）容量、GPIO 数量、ADC（Analog-to-Digital Converter，模数转换器）通道、通信接口、工作电压、低功耗模式、封装、工作温度和供货周期。

[COMMON] 接口参数应按需求列清：UART（Universal Asynchronous Receiver/Transmitter，通用异步收发器）、SPI（Serial Peripheral Interface，串行外设接口）、I2C（Inter-Integrated Circuit，集成电路间总线）、CAN（Controller Area Network，控制器局域网）等。

## 4. 参数影响

[COMMON] 主频影响控制循环速度和功耗；存储容量影响固件规模、日志缓存和 OTA（Over-The-Air，空中升级）冗余空间；接口数量影响外设扩展；低功耗模式影响电池产品续航；封装影响 PCB 面积、焊接工艺和维修难度。

[COMMON] MCU vs MPU（Microprocessor Unit，微处理器单元，通常依赖外部内存和操作系统运行复杂应用）的核心差异是集成度、实时控制能力、系统复杂度和资源规模。

## 5. 优点

[COMMON] MCU 集成度高、启动快、功耗低、成本可控，适合确定性控制。

[COMMON] MCU 软件栈相对简单，适合按键、传感器、马达、电源管理和通信桥接等控制任务。

## 6. 局限性

[COMMON] MCU 计算资源、内存容量和图形能力有限，不适合复杂 UI、多媒体处理和大型应用运行。

[COMMON] MCU 固件升级、异常恢复和量产测试需要在资源受限条件下设计。

## 7. 产品经理关注点

[COMMON] 产品经理应明确 MCU 承担的是主控、协处理器、电源管理控制器还是外设桥接控制器。

[COMMON] 选型时必须同时评估功能接口、功耗、成本、供应链、开发工具、SDK（Software Development Kit，软件开发工具包）成熟度和认证风险。

## 8. 常见应用场景

[COMMON] MCU 常用于遥控器、传感器节点、电源控制板、车载控制模块、按键板、灯控、马达控制和低功耗 IoT（Internet of Things，物联网）设备。

## 9. 需求文档需要明确内容

[COMMON] PRD（Product Requirements Document，产品需求文档）需要明确控制对象、响应时间、接口清单、功耗目标、升级方式、异常恢复、产测接口、日志能力和量产烧录方式。

[COMMON] 如果 MCU 参与 OTA，需求必须定义升级包来源、校验、断电保护、回滚和失败提示。

## 10. 异常状态设计

[COMMON] MCU 异常状态包括上电失败、看门狗复位、外设初始化失败、通信超时、Flash 写入失败、低电压复位、固件校验失败和升级中断。

[COMMON] Watchdog（看门狗，用于检测软件卡死并触发复位的硬件或软件机制）策略必须区分正常复位、异常复位和升级过程中的受控复位。
