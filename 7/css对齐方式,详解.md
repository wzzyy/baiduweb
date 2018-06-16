css对齐方式,详解

对齐方式分为水平和居中,对齐的元素又分为block,inline-block, inline, table-cell等多种情况.

一般块级元素的对齐方式:

| 元素         | 水平           |      |        |       | 垂直           |      |            |          |
| ------------ | -------------- | ---- | ------ | ----- | -------------- | ---- | ---------- | -------- |
|              | 方法           | 左   | 中     | 右    | 方法           | 上   | 中         | 下       |
| inline       | 容器text-align | left | center | right | line-height    | 默认 | 和行高一样 | 小于行高 |
| inline-block |                |      |        |       | vertical-align | top  | middle     | bottom   |
| block        | margin         | 默认 | 0 auto | 计算  | position       |      |            |          |
|              |                |      |        |       |                |      |            |          |
| table-cell   |                |      |        |       | vertical-align | top  | middle     | bottom   |



内联元素: margin-top  margin-bottom无效
