# Getting Started

## 知识库结构说明

本知识库使用 MkDocs 管理，所有正文内容放在 `docs` 目录下。

目录按主题拆分：

- `00_Index`：首页、入门说明和维护规范
- `01_Hardware`：硬件平台、芯片和电源相关知识
- `02_Storage`：存储器件和存储介质相关知识
- `03_Communication`：通信接口和总线相关知识
- `04_Sensor`：传感器和定位相关知识
- `05_OS`：操作系统和运行环境相关知识
- `06_Function`：产品功能设计相关知识
- `07_PRD`：PRD、状态机、异常设计和测试模板
- `08_Project_Case`：项目案例和方案复盘

## 文件命名规则

- 使用英文文件名，避免空格。
- 多个单词使用下划线连接，例如 `Network_State.md`。
- 文件扩展名统一使用 `.md`。
- 新增页面后，需要在根目录 `mkdocs.yml` 的 `nav` 中加入页面路径。
- 页面路径从 `docs` 目录内部开始写，例如 `06_Function/OTA.md`。

## Markdown 编写规范

- 每个页面使用一个一级标题 `#`，标题应说明页面主题。
- 正文结构使用二级标题 `##` 和三级标题 `###`。
- 命令、文件名、字段名使用反引号标记，例如 `mkdocs.yml`。
- 代码块使用围栏语法，并标注语言类型。
- 图片和附件优先放在同主题目录下，使用相对路径引用。
- 内部链接优先链接到具体 Markdown 文件，例如 `[OTA](../06_Function/OTA.md)`。

## Git 同步流程

```bash
git status
git add .
git commit -m "docs: update knowledge base"
git pull --rebase
git push
```

推荐流程：

1. 修改前执行 `git status` 确认工作区状态。
2. 在 `docs` 中新增或修改 Markdown 文件。
3. 同步更新 `mkdocs.yml` 导航。
4. 本地执行 `mkdocs serve` 预览。
5. 预览无误后提交并推送。
