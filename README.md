# study-web
## DAY01 表单标签的value、name
### 2023/8/14
 这个地方是我记录前端学习的地方，今天是第一天。



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
 

## DAY46 算法
### 2023/9/28

**<1>两数之和1**

1. 第一遍做的思路：最朴实的办法，用了两次遍历，时间复杂度为O(n^2)，空间复杂度是O(1)

2. 查看题解：
   
   (1)哈希表：创建哈希表，牺牲空间换时间。时间复杂度为O(n)，空间复杂度是O(n)。

   (2)双指针法：先把 nums 排序，再用左右指针来求出和为 target 的两个数。由于排序会破坏元素的原始索引，所以要记录值和原始索引的映射。

**<2>数组、链表、跳表**

![Alt text](image.png)


## DAY47 算法
### 2023/9/29
**<1>移动零283**
1. 第一遍：要用到双指针，但是怎么用忘记了，就去看了题解。
2. 查看题解：定义两个函数。第一个函数得出移除掉0之后的数组长度。第二个函数利用前面得出的长度，将移除掉0后的数组后面的数值全都变成0

**<2>盛最多水的容器11**
1. 第一遍：只能想到先把全部面积都求出来，然后选面积最大的。但是当时不知道用什么办法来存储已经得到的面积，以及不知道指针该用什么方式来移动。没做出来。
2. 查看题解：
   - 用左右指针；
   - 用max数学方法通过比较两个数来存储已知面积；
   - 左右指针移动条件：移动较低的一边。

**<3>三数之和15**
1. 第一遍：
2. 查看题解：可以用哈希的办法，但是考虑到要去重，所以用双指针法合适。

**<4>常见的时间复杂度**

![Alt text](cbfe0c6c29aec68338d9cff95cbfc38.png)

排序的时间复杂度是O(NlogN)


## DAY48 算法
### 2023/9/30
**<1>有效的括号20**
1. 第一遍：没有思路。
2. 查看题解：用栈的方法。先创建一个栈数组，把左括号都放入栈里，如果遇到右括号就先把右括号转换成左括号，然后再判断这个右括号是否跟栈最后一个元素相等，如果相等，则pop掉。最后判断栈的长度是否为零。

**<2>有效的字母异位词242**
1. 第一遍：算出每个字母出现的次数，比较两个字符串字母出现次数是否相等。但是不知道用什么数据结构来进行。
2. 查看题解：创建一个长度为 26 的频次数组，通过索引来定位每个字母，数组的值就是字符串中的字母出现次数。（要用到字符编码知识）

**<3>字母异位词分组49**
1. 第一遍：对哈希表的用法还是不了解，直接看答案了。
2. 查看题解：用到哈希表。会用到【242.有效的字母异位词】里面的判断是否为字母异位词的函数。

**<4>反转字符串344**
1. 第一遍：用左右指针做。修正：左右指针的值不能直接交换，要定义一个临时变量来换。


## DAY50 算法
### 2023/10/2
**<1>二叉树的最大深度104**
1. 查看题解：两种思路：
   - 回溯算法：采用深度优先搜索的前序遍历方式，通过维护一个深度变量来记录深度。
   - 动态规划：通过递归函数分别计算左子树和右子树的最大深度，然后合并得到整棵树的最大深度。

**<2>二叉树的前序遍历144**

**<2>二叉树的中序遍历94**

**<2>二叉树的后序遍历145**


## DAY51 算法
### 2023/10/3
**<1>验证二叉搜索树98**
1. 查看题解：
   注意点：二叉搜索树(BST)里的root.val 要比左子树的所有节点都更大，要比右子树的所有节点都小，只检查左右两个子节点是不够的。
   - 关于BST：是一种具有特定性质的二叉树，其中每个节点的左子树都小于该节点，右子树都大于该节点，这是BST的一个重要性质，这个性质使得**中序遍历**BST会按照**升序**的顺序访问节点。

**<2>二叉树的层序遍历104**
1. 查看题解：使用了广度优先搜索（BFS）的思想来遍历二叉树的每一层节点，从上到下、从左到右。
   - 层序遍历通常与队列结构密切相关。

     在层序遍历中，将根节点放入队列，然后循环执行以下步骤：

     **出队列（取出队列中的第一个节点）--> 处理当前节点 --> 将当前节点的子节点（如果存在）入队列**

     这个过程不断重复，直到队列为空，所有节点都被处理完毕。

**<3>在每个数行中找最大值515**
1. 查看题解：两种思路：
   - BFS(广度优先搜索)：从上到下 ---> 从左到右
   - DFS(深度优先搜索)
  
  >笔记：Number.MIN_SAFE_INTEGER 是 JavaScript 的内置常量，它表示的是在 JavaScript 中能够安全表示的最小整数值。这种技巧常用于需要比较和记录一系列值中的最大值或最小值时，通过初始化为一个极端值，可以确保第一个值一定会被记录下来，而后续的值可以比较得出更大的或更小的值。


## DAY52 算法
### 2023/10/4
**<1>二分查找704**
1. 注意点：
   - right 赋值是 ``nums.length`` (相当于`[left,right)`) OR ``nums.length-1`` (相当于 `[left,right]`)
   - while循环条件中是 `<` 还是 `<=`
   - ``left = mid + 1``，``right = mid - 1`` 还是 ``right = mid``， ``left = mid``
  > 笔记：`left + (right - left) / 2` 这种写法能够有效防止 left 和 right 太大，直接相加导致溢出的情况。
    与`(left+right)/2` 结果一样。


## DAY60 asynchronous、服务端API客户端
### 2023/10/12
1. 使用异步处理（asynchronous）相当于你点了一个披萨，在后厨准备的这段时间里你可以做其他事（比如：打电话或者看报纸等等）。这使得你的时间更加充分利用，因为你不必一直等待披萨准备好，而可以同时进行其他活动。在编程中，异步操作允许程序执行一个任务的同时，可以在后台进行其他任务，而不必等待当前任务完成。
    - promises可以更好地帮助asynchronous运行。

2. 使用回调函数（callback）类似于将点餐和吃披萨的过程合二为一。当你点餐时，你也告诉服务员，当披萨准备好后，请通知你。这就是一个回调的过程。如果不使用回调函数，这两个过程将分开进行，你需要不断地检查披萨是否已经准备好了，这可能会浪费你的时间和精力。

3. addEventListener就是异步处理的过程。

## DAY67 实例 - 类
### 2023/10/19
1. “实例”是面向对象编程（OOP）中的一个核心概念。当我们有一个类（在许多编程语言中使用 class 关键字定义），我们可以创建其具体的对象，这个对象就被称为类的“实例”。实例化是从类创建对象的过程。这个对象继承了类中定义的所有属性和方法。


## DAY72 卡片轮播图
### 2023/10/24
1. 卡片轮播图

   如果要在页面显示的项目有4个，总共有5个项目
   
   思路：在前后各克隆2个项目（在开头克隆3、4；在结尾克隆1、2） ，即为 4 5 1 2 3 4 5 1 2 

    设置默认index为1  
    `PAGE.data.translateX = -(swiperItemWidth + swiperItemWidth * index);` 
   - 处理第一个项目的切换：若点击左边按钮（swiperPrev方法），当Index为-1（即克隆4）时，在动画完成后迅速切换到原始的项目4上，并取消动画效果，从而实现无缝的效果。（所以结尾克隆的个数等于页面显示的项目减2；而开头克隆的项目始终是2，即为总项目的最后两个）
  
   - 处理最后一个项目的切换：若点击右边按钮（在swpierNext方法），当Index等于swiperItem长度即5的时候，在动画完成后迅速切换到index为0（即开头的克隆5），并取消动画效果，从而实现无缝的效果。


## DAY73 事件监听器
### 2023/10/25

写法一：最基础
```js
onEventLister: function (parentNode, action, childClassName, callback) {
                parentNode.addEventListener(action, function (e) {
                    e.target.className.indexOf(childClassName) >= 0 && callback(e);
                })
            },

```

写法二：综合（用这个也可以解决方法三的问题），即如果点击到childClassName的子元素，也可以定位到childClassName
```javascript
 //展开关闭监听器：当点击的元素为childClassName的子元素
    onEventLister: function (parentNode, action, childClassName, callback) {
        parentNode.addEventListener(action, function (e) {
            let element = e.target.closest('.' + childClassName);  //把childClassName变为类选择器
            if (element) {
                callback(e);
            }
        })
    },

```

写法三：
```js
onEventLister: function (parentNode, action, childClassName, callback) {
        parentNode.addEventListener(action, function (e) {
            let elementCheck = e.target;

            // 如果触发事件的元素是一个图片，则考虑它的父元素
            if (elementCheck.tagName === 'IMG') {
                elementCheck = elementCheck.parentElement;
            }

            elementCheck.className.indexOf(childClassName) >= 0 && callback(e);

        })
    },

```