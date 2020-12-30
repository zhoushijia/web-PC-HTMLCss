# vertical-align梳理

> 1 几个重要前置概念及规则
>
> 2 vertical-align解决什么问题?
>
> 3 vertical-align适用哪些元素?
>
> 4 vertical-align取值
>
> 5 vertical-align 到底通过什么实现 垂直对齐？
>
> 6 行盒子基线位置如何确定？

## 1 几个重要前置概念及规则

- inline元素 、inline-block元素 、文字 可在一行显示，它们 均由盒子包裹，此种盒子称为 行内盒子
- 一个或多个行内盒子 构成 一整行，这一整行也由盒子(看不见的)包裹，此种盒子称为 行盒子
- 行盒子的高度由其包含的最高的行内盒子决定
- 同一个行盒子中的各种内容会受该  行盒子 统一约束，默认遵循基线(baseline)对齐规则
- 基线对齐指所有行内元素的基线均与行盒子的基线对齐
- 行盒子的基线由其包含的最高的行内盒子的基线及其vertical-align值共同决定
- 行内盒子的基线位置又与font-size及line-height密切相关
- 英文字符的基线位置在字符x的下边缘，中文字符的基线略高于汉字底部，Inline-block元素若未包含文字则其基线在其margin-box底部，若包含文字，则其基线在其包含的最后一行文字的基线位置

## 2 vertical-align解决什么问题？

vertical-align解决同一行内各 行内元素以何种方式垂直对齐的问题

##  3 vertical-align适用于哪些元素

vertical-align适用于 inline  inline-block及table-cell元素

## 4 vertical-align的取值

可为 top middle bottom 等单词，也可为 百分比 ，还可为多少 像素，详见手册

## 5 vertical-align通过什么实现垂直对齐？

vertical-align通过改变各行内元素的对齐方式或行盒子基线位置实现垂直对齐

## 6 行盒子基线位置如何确定？

该基线位置由行盒子内最高的行内盒子及其vertical-align属性决定。在该行盒子内写入一个x,x底部会贴着该行盒子的基线。

## 参考资料

1 手册

2  https://www.codercto.com/a/74772.html 





