# 知识库索引

## 1. 知识库目标

本知识库用于沉淀硬件产品经理在技术评审、需求定义、方案选型、异常设计、测试验收和项目复盘中需要反复查阅的知识。

内容优先服务于产品决策，不替代芯片规格书、标准原文、认证报告或供应商设计指南。

## 2. 分类结构

- `01_Hardware`：MCU、MPU、SoC、PMIC 等硬件平台知识。
- `02_Storage`：Flash、NOR、NAND、eMMC、UFS、SD Card 等存储知识。
- `03_Communication`：蓝牙、WiFi、蜂窝网络、CAN、UART、SPI、I2C、USB 等通信知识。
- `04_Sensor`：GNSS、GPS、IMU、G-Sensor、Gyroscope、Compass、Barometer 等传感器知识。
- `05_OS`：Linux、Android、RTOS、QNX、Windows IoT 等系统知识。
- `06_Function`：OTA、绑定、登录、网络状态、恢复出厂、固件升级等功能设计。
- `07_PRD`：需求模板、状态机模板、异常处理模板和测试用例模板。
- `08_Project_Case`：车机、行车记录仪、摩托车设备等项目案例。

## 3. 使用方式

使用左侧导航按分类浏览，使用顶部搜索框检索专业名词、接口、异常状态或产品功能。

优先阅读同类对比内容，例如 MCU vs MPU、BLE vs Bluetooth Classic、FAT32 vs exFAT、Linux vs RTOS。

## 4. 维护原则

新增页面必须使用统一 Markdown 模板，并在 `mkdocs.yml` 中加入导航。

专业名词第一次出现时，应写出英文名称和中文解释。

涉及技术指标时，不猜测具体数值；具体数值应来自芯片规格书、标准文档、认证资料或测试报告。

## 5. 发布流程

内容更新后执行 `mkdocs build --strict` 检查构建、导航和链接。

提交到 `main` 分支后，GitHub Actions 会自动构建并发布到 GitHub Pages。

网站地址：

```text
https://urchinqm.github.io/hardware-product-manager-wiki/
```
