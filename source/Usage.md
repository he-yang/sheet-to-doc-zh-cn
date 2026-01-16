# 使用步骤

[English](https://sheet-to-doc.wtsolutions.cn/en/latest/Usage.html)

```{include} _snippet/intro.md
```



## 准备您的数据和图片

首先，您需要准备包含要转换为文档的数据的，可以是如下格式的数据
   - Excel 表格
   - CSV数据
   - JSON数据
   - JSONL数据

如果您需要上传图片，则需要提前准备好图片文件。
   - JPEG
   - PNG
   - GIF
   - BMP
   - JPG

:::{hint}
关于数据的准备的详细说明，请参见[数据和图片准备](ExcelData.md)
:::

## 准备您的 Word (.docx) 模板

接下来，您需要准备一个 Word 文档模板，用于生成最终文档。模板应包含来自 Excel 表格数据的占位符。

:::{hint}
关于 Word 模板的准备的详细说明，请参见[Word 模板](WordTemplate.md)
:::

## 打开Sheet-to-Doc

您可以使用以下方式访问 Sheet-to-Doc：

1. 使用现代浏览器（如 Chrome、Firefox、Edge、Safari）访问 [https://s.wtsolutions.cn/sheet-to-doc.html](https://s.wtsolutions.cn/sheet-to-doc.html)。
2. 下载工具作为桌面应用程序进行离线使用（可断网使用）。 [前往下载](Download.md)
3. 安装插件版Excel或WPS表格中的插件。 [前往下载](Download.md)

<script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js?client=ca-pub-8772217510669640"
     crossorigin="anonymous"></script>
   <ins class="adsbygoogle"
      style="display:block; text-align:center;"
      data-ad-layout="in-article"
      data-ad-format="fluid"
      data-ad-client="ca-pub-8772217510669640"
      data-ad-slot="2653271427"></ins>
   <script>
      (adsbygoogle = window.adsbygoogle || []).push({});
   </script>

## 填写数据

- 直接从您的 Excel 表格中复制数据, 或者从CSV, JSON, JSONL文件中复制数据，
- 将其粘贴到 Sheet-to-Doc 应用的 "数据" 区域中
- 您可以在应用中查看数据预览。

## 上传图片（如有）

如果您希望把图片写入Word模版，那么您还需要上传图片，您可以一次性上传多张图片，也可以逐个上传。上传区域下方会出现您已经上传的文件列表。如果您没有图片上传，则可以跳过图片上传这一步。

## 上传模板

上传您准备的 Word 模板文件。

## 数据和占位符比对

对步骤1输入的数据和步骤2上传的Word模版的内容进行比对，帮助用户发现模版中存在的错误，并提出修改建议。

:::{hint}
关于具体比对过程的详细说明，请参见[数据比对](Comparison.md)
:::

## 生成文档      

在选择生成模式的之前，选择生成模式并定义文件名名称。

:::{hint}
关于具体设置的详细说明，请参见[设置](Settings.md)
:::

点击 "生成" 按钮。该工具将使用数据填充模板，并根据您选择的模板生成专业文档。


