# 关于本项目

## 项目目标

实现从 Markdown 文档到公开网站的自动化发布。

具体来说，希望达到三个效果：

1. 只维护一份 Markdown 源文件，不在网页排版上重复劳动。
2. 每次推送到 main 分支，网站自动更新，不需要手工上传文件。
3. 网站拥有固定的公开地址，方便同学和老师直接访问。

## 技术组成

| 工具 | 作用 |
| --- | --- |
| Markdown | 编写文档内容 |
| MkDocs Material | 将文档构建成静态网站 |
| GitHub Actions | 自动执行安装、构建和部署 |
| GitHub Pages | 托管并提供网站访问地址 |

## 发布流程

整个流程可以概括为一条流水线：

```text
编写 Markdown  →  git push  →  GitHub Actions  →  生成 site/  →  发布到 Pages
```

其中 MkDocs 负责把 `docs/` 中的 Markdown 和 `mkdocs.yml` 中的配置转换成 HTML；GitHub Actions 负责在云端重复执行“安装依赖、构建、上传”这几步；GitHub Pages 则把这些 HTML 对外提供访问。

## 我的理解

在动手之前，我以为“自动部署”需要自己写服务器脚本。实际做下来发现，GitHub Actions 提供的是一台临时的云端机器：每次触发时拉取仓库代码、安装 `requirements.txt` 中的依赖、执行构建命令，再把产物交给 Pages。理解了这一点之后，配置文件里的每一步就不再是“照抄的咒语”，而是可以逐行解释的操作。

## 相关页面

- 返回[首页](index.md)
- 查看[使用指南](guide.md)
- 查看[API 参考](api.md)
