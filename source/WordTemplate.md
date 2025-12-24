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

占位符是指在 Word 模板中用于插入数据的特殊标记。每个占位符都以 `{` 和 `}` 括起来，例如 `{姓名}`、`{出生日期}` 等。

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

> 循环占位符的格式为 `{#data}...{/data}`。在 `{#data}...{/data}` 中，您可以使用数据占位符，如 `{姓名}` 来引用具体数据。

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

> 判断占位符的格式为 `{#a条件}...{/a条件}`。

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

### 过滤器（Filters）

您可以使用过滤器来转换模板中的数据。过滤器通过管道符（`|`）应用到占位符上，语法为：`{占位符 | 过滤器名称}` 或 `{占位符 | 过滤器名称:参数}`。

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

### 注意事项

- 占位符必须用大括号 `{}` 括起来。
- 占位符的名称必须与 Excel 表格中的列标题完全匹配，包括大小写。
- 占位符可以在模板中的任何位置使用，包括段落、表格、列表等。



## 视频演示 

1. 使用Excel数据演示

<iframe src="//player.bilibili.com/player.html?isOutside=true&aid=115733463831611&bvid=BV1bgqVBCEDK&cid=34791951913&p=1" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true"></iframe>

2. 使用JSON数据演示

<iframe src="//player.bilibili.com/player.html?isOutside=true&aid=115762824026686&bvid=BV1gzBsB7ETa&cid=34907095682&p=1" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true"></iframe>

3. 更多视频

[点击这里查看更多视频](https://s.wtsolutions.cn/images/videoqrcodes.png)