# Sheet to Doc - 中文文档

这是 Sheet to Doc 的中文文档，Sheet to Doc 是一个将 Excel 表格转换为专业文档的工具。

## 文档结构

文档使用 Sphinx 和 Read the Docs 构建。主要内容位于 `source` 目录中，包含 Markdown 文件，涵盖了使用 Sheet to Doc 的各个方面。

## 构建文档

要在本地构建文档，您需要安装 Python 和 Sphinx。然后运行：

```bash
pip install -r source/requirements.txt
sphinx-build -b html source build/html
```

构建后的文档将位于 `build/html` 目录中。

## 文档内容

- **getstarted.md**: 基本使用步骤、限制条件和示例
- **WebApp.md**: 关于 Web 应用的信息
- **ExcelAddIn.md**: 关于 Excel 插件的信息
- **WPSAddIn.md**: 关于 WPS 插件的信息
- **API.md**: API 文档
- **usage.md**: 详细使用说明
- **contact.md**: 联系信息
- **termsofuse.md**: 使用条款
- **privacy.md**: 隐私政策

## 贡献

如果您发现文档有任何问题或有改进建议，请联系我们。

## 许可证

文档采用 MIT 许可证。有关详细信息，请参阅 LICENSE 文件。