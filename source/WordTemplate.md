# Word 模板准备

[English](https://sheet-to-doc.wtsolutions.cn/en/latest/WordTemplate.html)


## 准备您的 Word 模板

> 我们推荐您使用微软的Word来准备您的模板文件，如果没有Word，您可以使用其他编辑器（如WPS）来准备模板文件。


- 创建一个新的 Word 文档，必须是.docx格式文件。
- 使用 `{占位符}` 语法插入占位符。关于占位符的详细用法，见下方“占位符”部分。
- 根据需要添加任何其他文本或格式。
- 将模板保存为 .docx 文件。

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

## 占位符

### 数据占位符

占位符是指在 Word 模板中用于插入数据的特殊标记。每个占位符都以**英文字符** `{` 和 `}` 括起来，例如 `{姓名}`、`{出生日期}` 等。

占位符的名称必须与 Excel 表格中的列标题完全匹配，否则数据将无法正确填充。

假设您的 Excel 表格包含以下列：姓名、年龄、性别。
```
    姓名    年龄    性别
    张三    25    男
```

在 Word 模板中，您可以插入以下占位符：

<div class="word-document">

{姓名},{年龄},{性别}。

</div>

当工具运行时，它将使用 Excel 表格中的数据填充这些占位符。
<div class="word-document">

张三,25,男。

</div>

### 循环占位符

> 循环占位符只能在生成模式2下（每个数据项生成一个Word文档）生效。

如果您的 Excel 表格中包含多行数据，您可以使用循环占位符来重复填充模板中的内容。

> 循环占位符的格式为 `{#data}...{/data}`。在 `{#data}...{/data}` 中，您可以使用数据占位符，如 `{姓名}` 来引用具体数据。注意`{}`需要使用**英文字符**。

假设您的 Excel 表格包含以下列：姓名、年龄、性别。
```
    姓名    年龄    性别
    张三    25    男
    李四    30    女
```

在 Word 模板中，您可以插入以下占位符：

<div class="word-document">

{#data}

{姓名},{年龄},{性别}。

{/data}
</div>

当工具运行时，它将循环阅读Excel 表格中的数据，然后逐行填充这些占位符。

<div class="word-document">

张三,25,男。

李四,30,女。

</div>


### 判断占位符

如果您的 Excel 表格中包含条件数据，您可以使用判断占位符来根据条件填充模板中的内容。

#### 判断占位符1 - true false

> 判断占位符1的格式为 `{#a条件}...{/a条件}`。注意`{}`需要使用**英文字符**。

假设您的 Excel 表格包含以下列：姓名、年龄、性别。
```
    姓名    年龄    性别    获奖
    张三    25    男    true
    李四    30    女    false
    王五    35    男    true
```

在 Word 模板中，您可以插入判断占位符`{#获奖}...{/获奖}`：

<div class="word-document">

本次比赛获奖名单：

{#data}

{#获奖}

{姓名},{年龄},{性别}。

{/获奖}

{/data}

</div>

当工具运行时，它将循环 Excel 表格中的数据，并完成判断是否是获奖人员，如果是，则填充占位符，如果不是，则不填充。

<div class="word-document">

本次比赛获奖名单：

张三,25,男。

王五,35,男。

</div>

#### 判断占位符2 - 等于指定值

> 判断占位符2的格式为 `{#a条件 == "指定值"}...{/}`。

举例：

假设您的 Excel 表格包含以下列：。
```
    姓名    奖品
    张三    手表
    李四    充电宝
    王五    手表
```

下载本模板文件：[Sample3-docx](_static/sample3-docx.docx)

<div class="word-document">

{#data}

{姓名}获得了{奖品}，展示如下：

{#奖品 == "手表"}

![手表](_static/watch.png)

{/}

{#奖品 == "充电宝"}

![充电宝](_static/batterybank.png)

{/}

{/data}

</div>

> 注意：例子中的"手表"和"充电宝"外面的双引号必须是英文双引号。
> 如果条件指定值是数字，则不用加双引号，直接写数字即可。

> 本例子应当在生成模式2所有数据在一个Word文档中重复生成下运行。

当工具运行时，它将循环 Excel 表格中的数据，并判断设置的条件，如果是，则填充占位符，如果不是，则不填充。

<div class="word-document">

张三获得了手表，展示如下：

![手表](_static/watch.png)

李四获得了充电宝，展示如下：

![充电宝](_static/batterybank.png)

王五获得了手表，展示如下：

![手表](_static/watch.png)

</div>


### 图片占位符
（自版本2.2.0开始支持）

Sheet to Doc提供两种插入图片的方法， 方法1见上述的判断占位符2中的方法，另外一种方法就是本章节的图片占位符方法。

图片占位符是指在 Word 模板中用于插入图片的特殊标记。每个图片占位符都以**英文字符** `{` 和 `}` 括起来，例如 `{@图片 | _inline_image:width:height}`、`{@图片 | _block_image:width:height}` 等。

- `_inline_image` 表示内联图片，会将图片插入到文本中，与文本紧密结合。
- `_block_image` 表示块级图片，会将图片插入到段落中，与段落独立。
- `width` 和 `height` 是可选参数，用于指定图片的宽度和高度。如果不指定，图片将按照5cm x 5cm的大小显示。如果需要指定，需要使用**厘米**作为单位。例如 `{@图片 | _inline_image:10:10}` 表示将图片插入到文本中，宽度为10cm，高度为10cm。

> 注意：
- 图片占位符必须以`@`开头，例如 `{@图片 | _inline_image}`
- 图片占位符必须包含图片类型（`| _inline_image` 或 `| _block_image`），否则工具无法识别, 其中`|`, `_`需要使用**英文字符**
- 图片占位符必须在Word模版中以单独一行的形式出现，不能与其他文本在同一行。否则无法正常显示。
- 图片占位符必须包含图片文件名变量，否则工具无法识别图片文件名，例如 `{@图片 | _inline_image}` 中的 `图片` 就是图片文件名变量
- 图片文件名与上传的图片文件名一致（区分大小写，需要有后缀名），否则工具无法找到对应的图片文件（例如 `watch.png`）。图片名称可以包含中文，但如果包含特殊字符，有可能会出现错误。
- 如果上传的图片多余Excel数据中列出的图片，工具会忽略多余的图片，只使用Excel数据中列出的图片。如果Excel数据中列出了数据，但是没有上传对应的图片，工具会在生成的文档中显示“没有上传图片，请上传图片”。

例子：

假如Excel数据列出了 图片名称、图片中文名。

例如：
```
    图片中文名  图片名称
    手表    watch.png
    充电宝    batterybank.png
```

同时需要上传 watch.png 和 batterybank.png 这两张图片。


Word模版采用以下格式：

<div class="word-document">

{#data}

{@图片名称 | _inline_image}

{/data}

</div>

会生成如下文档：

<div class="word-document">

![手表](_static/watch.png)

![充电宝](_static/batterybank.png)


</div>



### 过滤器（Filters）

您可以使用过滤器来转换模板中的数据。过滤器通过管道符（`|`）应用到占位符上，语法为：`{占位符 | 过滤器名称}` 或 `{占位符 | 过滤器名称:参数}`。注意`{}`和`|`需要使用**英文字符**。

#### 字符串过滤器

| 过滤器名称 | 描述 | 示例 | 输出 |
|-------------|-------------|---------|--------|
| `toUpperCase` | 将英文字符串转换为大写 | `{姓名 \| toUpperCase}` | `Zhang San` → `ZHANG SAN` |
| `toLowerCase` | 将英文字符串转换为小写 | `{姓名 \| toLowerCase}` | `Zhang San` → `zhang san` |
| `capitalize` | 将英文字符串的第一个字符大写 | `{姓名 \| capitalize}` | `Zhang San` → `Zhang san` |

#### 数字过滤器

##### 基本数字格式化

| 过滤器名称 | 描述 | 示例 | 输出 |
|-------------|-------------|---------|--------|
| `fixed` | 将数字格式化为固定小数位数 | `{价格 \| fixed:2}` 当价格为 123.456 | `123.46` |
| `round` | 将数字四舍五入到最接近的整数 | `{价格 \| round}` 当价格为 123.6 | `124` |
| `ceil` | 将数字向上取整到最接近的整数 | `{价格 \| ceil}` 当价格为 123.1 | `124` |
| `floor` | 将数字向下取整到最接近的整数 | `{价格 \| floor}` 当价格为 123.9 | `123` |

##### 货币和财务格式化

| 过滤器名称 | 描述 | 示例 | 输出 |
|-------------|-------------|---------|--------|
| `currency` | 将数字格式化为货币格式 | `{价格 \| currency:¥:2}` 当价格为 1234.56 | `¥1,234.56` |
| `accounting` | 将数字格式化为会计格式（负数使用括号） | `{价格 \| accounting:¥:2}` 当价格为 -1234.56 | `¥(1,234.56)` |
| `thousandSeparator` | 将数字格式化为带千位分隔符 | `{价格 \| thousandSeparator:2}` 当价格为 1234567.89 | `1,234,567.89` |

##### 百分比和科学计数法

| 过滤器名称 | 描述 | 示例 | 输出 |
|-------------|-------------|---------|--------|
| `percentage` | 将数字格式化为百分比 | `{利率 \| percentage:2}` 当利率为 0.1234 | `12.34%` |
| `scientific` | 将数字格式化为科学计数法 | `{数值 \| scientific:2}` 当数值为 123456 | `1.23e+05` |

##### 数字缩写

| 过滤器名称 | 描述 | 示例 | 输出 |
|-------------|-------------|---------|--------|
| `shortNumber` | 将数字格式化为简短形式（K, M, B） | `{金额 \| shortNumber}` 当金额为 1234567 | `1.23M` |



### 占位符出现位置

占位符可以出现在Word模版的任何位置，包括但不限于：
- 段落
- 表格
- 列表
- 标题
- 页眉
- 页脚
- 文本框
等等


## 注意事项

- 占位符必须用大括号 `{}` 括起来，例如 `{姓名}`、`{出生日期}` 等。注意`{}`需要使用**英文字符**。
- 占位符的名称必须与 Excel 表格中的列标题完全匹配，包括大小写。
- 占位符可以在模板中的任何位置使用，包括段落、表格、列表等。


## 视频演示 

1. 使用Excel数据演示

<iframe src="//player.bilibili.com/player.html?isOutside=true&aid=115733463831611&bvid=BV1bgqVBCEDK&cid=34791951913&p=1" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true"></iframe>

2. 使用JSON数据演示

<iframe src="//player.bilibili.com/player.html?isOutside=true&aid=115762824026686&bvid=BV1gzBsB7ETa&cid=34907095682&p=1" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true"></iframe>

3. 更多视频

[点击这里查看更多视频](https://s.wtsolutions.cn/images/videoqrcodes.png)