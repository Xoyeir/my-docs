# my-docs

使用 MkDocs Material 编写的个人技术文档，通过 GitHub Actions 自动构建并发布到 GitHub Pages。

- 网站地址：<https://Xoyeir.github.io/my-docs/>
- 文档源码：`docs/`
- 实践记录与报告：[个人实验报告](report/README.md)

## 目录结构

| 路径 | 说明 |
| --- | --- |
| `docs/` | 网站页面，MkDocs 的内容目录 |
| `report/` | 作业过程说明与截图 |
| `mkdocs.yml` | 站点名称、主题与导航配置 |
| `requirements.txt` | 构建依赖 |
| `.github/workflows/` | GitHub Actions 工作流 |
| `site/` | 构建产物，不提交（见 `.gitignore`） |

## 本地运行

```bash
python -m pip install -r requirements.txt
python -m mkdocs serve
```

浏览器访问 <http://127.0.0.1:8000/> 预览。

严格模式构建：

```bash
python -m mkdocs build --strict
```

## 文档约定

修改 `docs/` 中的 Markdown 后推送到 main 分支，GitHub Actions 会自动构建并部署。新增页面时需要在 `mkdocs.yml` 的 nav 中登记，路径相对 `docs/` 目录，不要写 `docs/` 前缀。
