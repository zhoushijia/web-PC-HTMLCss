> 学习任务：
>
> 表格
>
> 列表
>
> 表单

## 表格

作用:展示数据（多年以前，也用于布局）

### 标签

- table  外面最大的
- tr 表格的一行
- td/th 一行中的一个单元格 ，th为表头单元格文字会加粗居中
- 辅助标签
  - thead  包在 表头tr的外面  表示 表格头部
  - tbody  包在 数据tr的外面 表示 表格主体
  - tfoot  表示表尾 ，了解即可 
  - caption 表格标题 直接写在table中 文字居中加粗

### 属性 （实际基本不用，主要为了记住单词）

- align  设置对齐  值可为 left  right  center
- border  设置边框  
- cellspacing  设置单元格之间的间距
- cellpadding 设置单元格边沿和内容之间的间距
- width 设置宽度
- height  高度

### 表格实例

```html
<!--以下表格 3行3列宽高均为300px,边框1px,水平居中，单元格间距及单元格与内容之间间距均为0-->
<table
      align="center"
      border="1"
      cellspacing="0"
      cellpadding="10"
      width="300"
      height="300"
    >
    <thead>
        <tr>
            <th>姓名</th>
            <th>年龄</th>
            <th>成绩</th>
        </tr>
    </thead>
    <tbody>
        <tr align="center">
            <td>张三</td>
            <td>20</td>
            <td>100</td>
        </tr>
        <tr>
            <td>李四</td>
            <td>30</td>
            <td>105</td>
        </tr>
    </tbody>
</table>
```

### 合并单元格

步骤:

1. 确定行合并还是列合并
2. 确定目标单元格 行合并时 最上面单元格  列合并时 最左边单元格，并在其中书写属性 colspan="xxx" rowspan="xxx"
3. 删除多余的单元格

```html
<table width="400" height="200" border="1" cellspacing="0" align="center">
      <caption>
        合并单元格
      </caption>
      <tr>
        <td colspan="4"></td>
        <!-- <td></td>
        <td></td>
        <td></td> -->
      </tr>
      <tr>
        <td colspan="2" rowspan="2"></td>
        <!-- <td></td> -->
        <td></td>
        <td rowspan="3"></td>
      </tr>
      <tr>
        <!-- <td></td>
        <td></td> -->
        <td></td>
      </tr>
      <tr>
        <td></td>
        <td></td>
        <td></td>
      </tr>
    </table>
```



## 列表

作用:显示数据 及 布局

### 无序列表(重点)

```html
<!-- unordered list ul 无序列表 只能直接放li-->
<ul>
    <!-- list item  li 列表项  独占一行 默认 左侧缩进 li中可放任意标签 外部必须被ul或ol包裹 -->
    <li>HTML</li>
    <li>CSS</li>
    <li>JS</li>
    <li>
        <ul>
            <li></li>
        </ul>
        <div></div>
        <a href=""></a>
    </li>
</ul>
```

### 有序列表（了解）

```html
<!-- ordered list ol 有序列表 只能直接放li -->
<ol>
    <li>40</li>
    <li>50</li>
    <li>30</li>
</ol>
```

### 定义列表

```html
<!-- dl definition list  定义列表  里面只能放dt dd -->
    <dl>
      <!-- dt及dd外面必须有dl dt和dd中可以放任意标签，dt dd独占一行 -->
      <!-- dt:definition title 定义标题  dd:definition description 定义描述  dt与dd为兄弟关系，一个dt通常对应多个dd -->
      <dt>家用电器</dt>
      <dd>冰箱</dd>
      <dd>空调</dd>
      <dd>洗衣机</dd>
      <dt>办公电器</dt>
      <dd>电脑</dd>
      <dd>打印机</dd>
      <dd>传真机</dd>
    </dl>
```



## 表单

作用:收集用户数据

由 表单域 及表单元素 表单提示信息 构成

### 表单域

```html
<form action="" method="post" name="myform">
</form>
```

### 表单元素

```html
<!-- 在form里面写表单元素,所有表单元素都不会独占一行 -->
      <!--input type="text" 普通文本框
          ="password" 密码框
          ="radio" 单选框
          ="checkbox" 复选框
          ="submit" 提交
          ="reset" 重置，会将表单元素恢复到默认状态
          ="button" 普通按钮
          ="image" 图片按钮
          ="file" 文件域
        -->
      <!-- 其他重要属性
        name:表示表单元素的名字，即提交信息的名字，由程序员设定
        value:表示表单元素的值，即提交信息的具体内容，通常由用户填写或程序员设定
        checked:表示被选中，对单选及复选框有效
        maxlength:定义最大输入字符数，对input框有效，了解即可
		selected: 表示被选中，对下拉列表有效
    -->

<form action="" method="post" name="myform">
     用户名: <input type="text" name="username" value="张三" /> <br />
      密码：<input type="password" /> <br />
      性别: <input type="radio" name="sex" value="1" id="man" />
      <label for="man">男</label>
    <!--label可以让提示文字关联表单元素，两种方法，1 通过for属性(推荐) 2 通过将表单元素包裹在label中-->
      <label><input type="radio" name="sex" value="2" checked /> 女</label>
      <br />
      爱好: <input type="checkbox" name="" id="" checked />篮球
      <input type="checkbox" name="" id="" />足球
      <input type="checkbox" name="" id="" />排球 <br />
      <br />
      国籍:
      <!-- 下拉列表，可在多个选项中选择 -->
      <!-- selected属性 设置选中项，未设置时第一个option被选中 -->
      <select name="" id="">
        <option value="">中国</option>
        <option value="" selected>德国</option>
        <option value="">法国</option>
      </select>
      <br />
      个人简介:
      <!-- 文本域，可输入多行文字 -->
      <textarea name="" id="" cols="30" rows="10">
介绍你自己

      </textarea>
      <!-- 提交按钮，可以提交数据 -->
      <input type="submit" />
      <!-- 重置按钮，恢复表单到初始状态 -->
      <input type="reset" />
      <!-- 普通按钮，需结合js使用 -->
      <input type="button" value="获取验证码" />
      <!-- 图片按钮，可以提交 -->
      <input type="image" src="../images/icon/man.jpg" alt="" />
      <!-- 另一种按钮，也可提交 -->
      <button>另一个按钮</button>
      <br />
      <!-- 文件域，用于上传文件 -->
      <input type="file" name="" id="" />
</form>
```

