# study-web
## DAY01 表单标签的value、name
### 2023/8/14
 这个地方是我记录前端学习日记的地方，今天是第一天。



**笔记**

1. 两个选项的name要相同，否则单选作用失效。
```html
<form>
    <div >
        <span>性别</span>
        <input type="radio" name="sex" value="男">男
        <input type="radio" name="sex" value="女">女
    </div>
</form>
```
2. radio和checkbox里面的value值是做动态网页时把数据提交到后台用的。

3. reset和submit里面的value值是按钮的名称。
```html
<form>
    <div>
        <input type="reset" name="reset" value="重设">
        <input type="submit" name="submit" value="提交">
    </div>
</form>
```

## DAY02 text-align
### 2023/8/15 

**笔记**

1. text-align 会影响容器内部的行内元素，而不会影响块级元素。
   
   `text-align: center; `
   - 只适用于水平方向上的居中对齐，垂直方向上的居中对齐需要使用其他方法，如使用 Flexbox，或者设置容器的高度并使用 line-height 属性来实现。
   - 对于内联块级元素（包括图片）同样可以使它们在容器内水平居中对齐；对于纯粹的行内元素，如文本、链接等，也可以通过 text-align: center; 来实现水平居中对齐。

2. **图片**是内联块级元素（inline-block）。内联块级元素的特点是在水平方向上表现得像行内元素，但在垂直方向上会保留块级元素的特性，即可以设置宽度、高度、内外边距等。

## DAY03 img空白字符串
### 2023/8/17
**笔记**

把img放在一个div容器里，如果img后面有空白字符串，解决办法：
1. 调整img元素的display，改为block 块元素。
2. 给div容器设置一个高度（跟img的高度一样），img的高度设置为100%.
3. 给div容器设置font-size：0；消除空字符串的影响。

## DAY10 页面要求
### 2023/8/23
**笔记**

1. 写样式要灵活，尽量不要把宽度和高度写死。多用flex布局，减少手动增改。
2. margin和padding区别。
3. 高度出现问题：检查空白字符影响；line-height设置。
4. 标签、样式要精简，去掉没用的。

## DAY12 居中
### 2023/8/25
**笔记**

1. 导航栏居中


2. 使用flex布局给盒子a设置space-between（如何撑开？）：
   - 直接给盒子a设置一个宽度。
   - 给总的container设置宽度，再给盒子a加上`flex:1 1;`
  
3. 放置背景图：
```html
<div class="container">
    <div class="pic"> 
        <a>这里放图片</a>
    </div>    
</div>
```
```css
.container {
    position: relative;
    height: px;
    width:  px;
}

.pic {
    position: absolute;
    top: 0;
    left: 0;
    display: inline-block;
    width: 100%;
    height: 100%;
}

a {
    display: block;
    height: 100%;
    width: 100%;
    background-size: px px;
    background-repeat: no-repeat;
    background-position: 50%;
    background-image:url(图片链接);
}
```

4. position上下居中：
```html
<div class="outside">
    <div class="inside"></div>
</div>
```
```css
.outside {
    position:relative
}

.inside {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);  
}

```

5. 超出文本用省略号显示
```css
p{
    overflow: hidden;/*超出部分隐藏*/
    text-overflow:ellipsis;/* 超出部分显示省略号 */
    white-space: nowrap;/*规定段落中的文本不进行换行 */
    width: 250px;/*需要配合宽度来使用*/
}
```

6. 修改placeholder颜色
```css
input::placeholder {
        color: green;
    }
```

## DAY38 javascript学习开始
### 2023/9/20
今天开始学习js了，每天要多花时间才行啊。

**笔记**
1. js在页面中的位置（可放在head以及body内）
浏览器解释html时是按先后顺序的
进行页面显示初始化的js要放在head里面。而如果是通过事件调用执行的function那么对位置没什么要求的。

2. 注释方式
单行：Ctrl + /
多行：Ctrl + Shift + /

3. 变量命名规则
- 变量名区分大小写。
- 必须使用字母、下划线`_`   或者美元符 `$`  开始，但是不能用数字开头。
- 变量名内部可包括：任意多个英文字母、数字、下划线`_`或者美元符`$`，但是不能包括空格和其他标点符号。
- 不能使用JavaScript关键词与JavaScript保留字。

4. 互动方法：
document.write、alert、confirm、prompt、window.open、window.close

5. 不同声明 （var、let、const）
let和const的区别
常量用const，变量用let
尽量使用 let 和 const ，不使用 var 。
 
