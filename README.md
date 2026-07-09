# 硬件产品经理知识库

## 项目用途

本项目用于沉淀硬件产品经理常用的技术概念、产品定义方法、PRD模板、异常设计、测试关注点和典型项目案例。

## 使用方式

1. 在 `docs` 目录下按主题维护知识条目。
2. 每个知识条目使用统一 Markdown 模板。
3. 通过 `mkdocs.yml` 维护站点导航。

## MkDocs生成HTML方法

安装依赖：

```bash
pip install mkdocs mkdocs-material
```

本地预览：

```bash
mkdocs serve
```

生成静态HTML：

```bash
mkdocs build
```

生成结果默认输出到 `site` 目录。

