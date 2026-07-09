# 硬件产品经理知识库

## 项目用途

本项目用于沉淀硬件产品经理常用的技术概念、产品定义方法、PRD模板、异常设计、测试关注点和典型项目案例。

## 使用方式

1. 在 `docs` 目录下按主题维护知识条目。
2. 每个知识条目使用统一 Markdown 模板。
3. 通过 `mkdocs.yml` 维护站点导航。

## 如何新增知识

1. 在 `docs` 目录中选择对应分类目录。
2. 新建 `.md` 文件，文件名使用英文和下划线，例如 `Power_Sequence.md`。
3. 在文件顶部写入一级标题，例如 `# Power Sequence`。
4. 按概念、应用场景、产品设计关注点、测试关注点组织正文。
5. 在 `mkdocs.yml` 的 `nav` 中加入新页面路径。

示例：

```yaml
nav:
  - 01_Hardware:
      - Power Sequence: 01_Hardware/Power_Sequence.md
```

## 如何修改 Markdown

Markdown 文件位于 `docs` 目录。

常用写法：

````markdown
# 页面标题

## 二级标题

- 列表项
- 列表项

```text
代码或配置示例
```
````

内部链接示例：

```markdown
[OTA](docs/06_Function/OTA.md)
```

## MkDocs生成HTML方法

安装依赖：

```bash
pip install -r requirements.txt
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

## 如何发布网站

生成静态 HTML 后，可以将 `site` 目录发布到任意静态网站托管服务。

常见方式：

1. GitHub Pages：将构建产物发布到 Pages 分支或使用 CI 自动构建。
2. 内部服务器：将 `site` 目录上传到 Nginx、Apache 或对象存储静态站点。
3. 文档平台：把 `site` 目录作为静态资源目录部署。

## GitHub Pages 自动发布

本项目已配置 GitHub Actions 工作流：

```text
.github/workflows/deploy-pages.yml
```

每次推送到 `main` 分支后，GitHub 会自动安装依赖、执行 `mkdocs build --strict`，并将生成的 `site` 目录发布到 GitHub Pages。

仓库需要在 GitHub 网页中设置一次：

1. 进入仓库 `Settings`。
2. 打开 `Pages`。
3. 将 `Build and deployment` 的 `Source` 设置为 `GitHub Actions`。

发布后网站地址：

```text
https://urchinqm.github.io/hardware-product-manager-wiki/
```

如果使用 GitHub Pages，可以在本地执行：

```bash
mkdocs gh-deploy
```

## 项目维护建议

- 每次新增页面后，同步更新 `mkdocs.yml`。
- 每次发布前执行 `mkdocs build` 检查配置和链接。
- 分类目录保持稳定，避免随意移动已发布页面。
- 大段配置和命令使用代码块，便于复制和搜索。
