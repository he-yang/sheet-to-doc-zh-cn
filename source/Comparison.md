# 数据和占位符比对

[English](https://sheet-to-doc.wtsolutions.cn/en/latest/Comparison.html)

```{include} _snippet/intro.md
```



:::{hint}
步骤2.1数据比对，该步骤不是必须的，也就是可以跳过的。
:::

> （自2.1.0.0版本开始）

步骤2.1对步骤1输入的数据、图片（如有），和步骤2上传的Word模版的内容进行比对，帮助用户发现模版中存在的错误，并提出修改建议。

比对完成后的结果，对后续步骤给出建议，但不管比对结果如何，你都可以跳过步骤2.1，前往步骤3生成文档。

## 比对过程

- 数据占位符和数据比对
   - 找到步骤2中上传的Word模版中的出现数据占位符，例如`{姓名}`、`{出生日期}`等
   - 对比步骤1中提供的数据项和步骤2中模版中的数据占位符
   - 如果步骤2中模版中的有数据占位符`{姓名}`，但是在步骤1提供的数据没有提供`姓名`，只有`年龄`，那么认为不匹配
   - 以对号和叉叉表示匹配和不匹配
   - 同时，根据模版的情况，给出采用生成模式1，还是生成模式2的建议。

- 过滤器filters对比
   - 识别步骤2中上传的Word模版中出现的过滤器filters
   - 如果这些filters可以被Sheet-to-Doc处理，那么显示对号
   - 如果这些filters不能被Sheet-to-Doc处理，那么显示叉叉
   - 具体有哪些filters能被处理，可以参考[Word模版](WordTemplate.md)
   - 如果模版中没有使用filters，那么可以忽略这一步

- 图片占位符和图片比对
   - 首先识别步骤2中上传的Word模版有没有使用图片占位符
   - 如果有，则检查步骤1中提供的图片数据列名称是否与模版中的图片占位符匹配
      - 如果匹配，则显示对号
      - 如果不匹配，则显示叉叉
   - 识别图片类型是否可以被接受（jpg,png,jpeg,gif,bmp）
      - 如果可以，则显示对号
      - 如果不可以，则显示叉叉
   - 识别图片是否在步骤1中上传
      - 如果已经上传，则显示对号
      - 如果不在，则显示叉叉
   - 如果模版中没有使用图片占位符，那么可以忽略这一步


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

## 修改方式

- 根据比对结果，用户可以手动修改模版。
- 也可以根据建议，手动修改数据。
- 直到两者匹配，之后进行后续步骤。


:::{hint}
- 本步骤不是必须的，也就是可以跳过的。
- 如果用户跳过本步骤，那么在后续步骤中，用户需要手动确认数据和模版是否匹配。
- 本步骤的比对完全通过，并不意味着数据和模版完全匹配，后续的生成文档过程不一定会成功。
- 最终的生成结果一定要再进行人工检查。
:::