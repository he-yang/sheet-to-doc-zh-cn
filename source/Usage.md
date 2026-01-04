# 使用说明

[English](https://sheet-to-doc.wtsolutions.cn/en/latest/Usage.html)

Sheet to Doc 是一个功能强大的工具，可以自动将 Excel 表格转换为专业文档。在邮件合并的基础上，本工具具备更多功能。

## 使用步骤

### 准备您的数据和图片

首先，您需要准备包含要转换为文档的数据的 
   - Excel 表格。表格应具有清晰的结构：
      - 第一行为标题行，
      - 后续行为数据行。
   - CSV数据
   - JSON数据
   - JSONL数据

如果您需要上传图片，则需要提前准备好图片文件。

关于数据的准备，请参见[数据和图片准备](ExcelData.md)

### 准备您的 Word (.docx) 模板

接下来，您需要准备一个 Word 文档模板，用于生成最终文档。模板应包含来自 Excel 表格数据的占位符。

关于 Word 模板的准备，请参见[Word 模板](WordTemplate.md)

### 访问工具

您可以使用以下方式访问 Sheet to Doc：

- 使用现代浏览器（如 Chrome、Firefox、Edge、Safari）访问 [https://s.wtsolutions.cn/sheet-to-doc.html](https://s.wtsolutions.cn/sheet-to-doc.html)。
- 您可以在右上角点击语言切换器来切换到英文。
- 下载工具作为桌面应用程序进行离线使用（可断网使用）。 [下载](Download.md)

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

### 填写数据

- 直接从您的 Excel 表格中复制数据, 或者从CSV, JSON, JSONL文件中复制数据，
- 将其粘贴到 Sheet to Doc 应用的 "数据" 字段中，
- 您可以在应用中查看数据预览。

### 上传图片（如有）

如果您希望把图片写入Word模版，那么您还需要上传图片，您可以一次性上传多张图片，也可以逐个上传。上传区域下方会出现您已经上传的文件列表。如果您没有图片上传，则可以跳过图片上传这一步。

### 上传模板

- 上传您在步骤 2 中准备的 Word 模板文件。

### 数据比对

对步骤1输入的数据和步骤2上传的Word模版的内容进行比对，帮助用户发现模版中存在的错误，并提出修改建议。

关于具体比对过程，请参见[数据比对](Comparison.md)

### 生成文档      

在选择生成模式的之前，选择生成模式并定义文件名名称。

关于具体设置，请参见[设置](Settings.md)

点击 "生成" 按钮。该工具将使用数据填充模板，并根据您选择的模板生成专业文档。

## 例子

我们提供了若干的示例文档，您可以在[示例文档](Examples.md)中查看。通过查看这些例子，您可以了解到工具的使用方法和功能。


## 视频演示 

1. 使用Excel数据演示

<iframe src="//player.bilibili.com/player.html?isOutside=true&aid=115733463831611&bvid=BV1bgqVBCEDK&cid=34791951913&p=1" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true"></iframe>

2. 使用JSON数据演示

<iframe src="//player.bilibili.com/player.html?isOutside=true&aid=115762824026686&bvid=BV1gzBsB7ETa&cid=34907095682&p=1" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true"></iframe>

3. 更多视频

[bilibili视频](https://space.bilibili.com/1534949351/lists/7066080?type=season)
[其他视频平台](https://s.wtsolutions.cn/images/videoqrcodes.png)