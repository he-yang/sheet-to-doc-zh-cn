# 快速入门

[English](https://sheet-to-doc.wtsolutions.cn/en/latest/getstarted.html)

Sheet to Doc 是一个功能强大的工具，可以自动将 Excel, CSV, JSON, JSONL数据写入docx格式的Word模版，批量的转换为Word文档。

在邮件合并的基础上，本工具开发了更多功能，比如自定义文件名，自定义文件路径，嵌入图片等等等等。

:::{attention}
本快速入门指南（本页内容）将引导您快速了解使用步骤，帮助您快速上手使用 Sheet to Doc，当您熟悉了之后应该阅读具体的[使用说明](Usage.md)来了解更多的功能。
:::



## 使用场景

### 场景1：生成销售报告

1. **准备 Excel 表格**：创建包含以下列的表格：产品名称、数量、价格、总计。
2. **选择模板**：使用 "销售报告" 模板。
3. **生成**：点击 "生成" 按钮创建销售报告。
4. **结果**：一份专业的销售报告，包含产品、数量、价格和总计的表格。

### 场景2：生成发票

1. **准备 Excel 表格**：创建包含以下列的表格：发票编号、客户名称、日期、项目、数量、价格、总计。
2. **选择模板**：使用 "发票" 模板。
3. **生成**：点击 "生成" 按钮为每一行创建发票。
4. **结果**：多张发票，每张发票都有自己的发票编号、客户名称、日期和项目详情。

### 场景3：生成信件

1. **准备 Excel 表格**：创建包含以下列的表格：收件人姓名、地址、日期、主题、正文。
2. **选择模板**：使用 "商务信函" 模板。
3. **生成**：点击 "生成" 按钮创建个性化信函。
4. **结果**：带有收件人姓名、地址和自定义内容的个性化商务信函。

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

## 基本使用步骤

### 准备您的 Excel 数据

首先，您需要准备包含要转换为文档的数据的 Excel 表格。表格应具有清晰的结构：
- 第一行为标题行，
- 后续行为数据行。

示例：

下载示例 Excel 文件：[sample1-sheet.xlsx](_static/sample1-sheet.xlsx)

| 姓名   | 出生日期    | 性别 |
|--------|--------------|--------|
| 张三  | 1990-05-12   | M     |


### 准备您的 Word (.docx) 模板

接下来，您需要准备一个 Word 文档模板，用于生成最终文档。模板应包含来自 Excel 表格数据的占位符。

示例：

- 创建一个新的 Word 文档。
- 使用 `{占位符}` 语法插入占位符。例如，`{姓名}` 将被替换为 "姓名" 列的数据，`{出生日期}` 将被替换为 "出生日期" 列的数据。
- 根据需要添加任何其他文本或格式。
- 将模板保存为 DOCX 文件。

示例2：

下载示例 Word 模板文件：[sample1-doc.docx](_static/sample1-doc.docx)

---



<div class="word-document">

主题：访问通知：一位同事明天来访

尊敬的 Davidson：

我们特此通知您，我们的一位同事明天将访问您的办公室。其员工 ID 上显示的详细信息如下：

姓名：{姓名}

出生日期：{出生日期}

性别：{性别}

请在其抵达时协助办理入场和协调事宜。如有任何进一步的信息需求，请随时与我联系。

感谢您的支持。

此致

敬礼

WTSolutions

</div>

---



### 打开Sheet to Doc

您可以使用以下方式访问 Sheet to Doc：

1. 使用现代浏览器（如 Chrome、Firefox、Safari）访问 [https://s.wtsolutions.cn/sheet-to-doc.html](https://s.wtsolutions.cn/sheet-to-doc.html)。
2. 下载软件安装包作为桌面应用程序（可离线单机使用）。 [前往下载](Download.md)


### 填写数据

- 直接从您的 Excel 表格中复制数据。
- 将其粘贴到 Sheet to Doc Web 应用的 "数据" 区域中。
- 您可以在 Web 应用中查看数据预览。

### 上传模板

- 上传您准备的 Word 模板文件。

### 生成文档      

在选择生成模式的时候，选择模式1：每行数据生成单独Word文档

点击 "生成" 按钮。该工具将使用 Excel 表格中的数据填充模板，并根据您选择的模板生成专业文档。

示例：

下载示例生成的文档：[sample1-report.docx](_static/sample1-report.docx)

---



<div class="word-document">

主题：访问通知：一位同事明天来访

尊敬的 Davidson：

我们特此通知您，我们的一位同事明天将访问您的办公室。其员工 ID 上显示的详细信息如下：

姓名：张三

出生日期：1990/5/12

性别：M

请在其抵达时协助办理入场和协调事宜。如有任何进一步的信息需求，请随时与我联系。

感谢您的支持。

此致

敬礼

WTSolutions

</div>

---

:::{note}
以上为简单的快速入门教程，现在您可以开始使用 Sheet to Doc 来自动生成专业文档了。
如果您想要了解更多的使用技巧，请参考[使用教程](Usage.md)。
:::