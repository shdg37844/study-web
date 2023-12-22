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

![Alt text](/images/image.png)


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

![Alt text](/images/cbfe0c6c29aec68338d9cff95cbfc38.png)

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

## DAY74 箭头函数、this、requestAnimationFrame
### 2023/10/26
1. 使用箭头函数使得this的上下文被正确地保留了，可以直接访问类或对象的其他方法和属性。

   箭头函数的主要特点是它不绑定自己的this。这意味着，在箭头函数内部，this的值与箭头函数定义时的外部作用域中的this值相同。

2. requestAnimationFrame 是一个浏览器提供的API，用于在下一次重绘之前执行一段代码。它主要用于动画和游戏的开发，因为它可以确保代码在屏幕刷新的最佳时机执行，从而提供流畅的动画效果。


## DAY75 classList
### 2023/10/27
classList 是一个DOM元素的属性，返回一个 DOMTokenList 对象。这个对象代表了元素的类名列表，并提供了一系列方法来操作这些类名。

classList的常用方法：
- add(类名1, 类名2, ...)
- remove(类名1, 类名2, ...)
- contains(类名)
- toggle(类名, [force])
- replace(旧类名, 新类名)


## DAY76 构造函数中的this与let/const/var
### 2023/10/28
用法：使用 this 来初始化新对象的属性和方法； let/const/var 用来创建在函数内部使用的局部变量。

**this**：
- 当在 JavaScript 中使用构造函数创建一个新的对象时，this 关键字引用的是正在被创建的那个对象。它在构造函数中用于引用并初始化新对象的属性和方法。
- 它将存活于新对象的整个生命周期。
- 通过 this 定义的属性和方法可以通过对象实例在外部访问，除非使用了其他封装机制。

**let/const/var**：
- 用于在函数内部或块作用域内声明局部变量（var: 函数作用域； let 和 const: 块作用域）
- 它们创建的是变量，不是对象的属性或方法。
- 变量存在于其作用域的生命周期中。这些变量只能在其定义的作用域内访问。

## DAY79 node.js
### 2023/10/31
1. path module：
   
   basename 和 dirname：可以直接获得，也可以通过path module获得

2. fs module：创建文件夹、创建文件、重命名文件、给文件添加内容、输出文件内容...
3. os module
4. url module

## DAY80 node.js gulp
### 2023/11/1
1. **gulp3**及之前的版本的任务是通过 gulp.task() 方法直接注册的，这意味着一旦在 gulpfile.js 中使用 gulp.task() 定义了任务，Gulp 就知道这些任务的存在，可以直接在命令行中调用它们（不用exports）。

    **gulp4** 是通过常规的 JavaScript 函数定义，并通过 exports 关键字导出（从而可以在命令行使用运行）。


## DAY82 node.js webpack
### 2023/11/3
在 webpack 5 中，对于资源文件（例如图片），不再需要 file-loader 和 url-loader 这样的 loader。因为 webpack 5 引入了一个内置的资源类型 asset，可以替代这些 loader。

asset 类型提供了两种模式：
- asset/resource（替代 file-loader）
- asset/inline（替代 url-loader）

在webpack.config.js中：
```js
{
  test: /\.(png|svg|jpg|gif)$/,
  type: 'asset/resource',  //替代 file-loader
  generator: {
    filename: 'assets/images/[name][hash][ext][query]' // 定义输出的文件名和路径
  }
},
```

## DAY83 数组方法
### 2023/11/4
有返回值：格式用return
1. **filter**  【筛选】不会改变原数组。返回一个新数组。

2. **map**  

3. **find**  返回第一个true值 

4. **some**  检查是否有值满足条件；返回true或者false

5. **every**  检查是否所有值都满足条件；返回true或者false

6. **reduce**   会改变原数组

7. **includes**  【特殊：没有function，用的是argument】用在一些简单的含有数字的数组里，检查某个数字是否在数组里，返回true或者false
>  parameter和argument的不同：
> - **Parameter** is the variable in the declaration of the function.
> - **Argument** is the actual value of this variable that gets passed to the function.


没有返回值：
1. **forEach**  


## DAY84 Node.js
### 2023/11/5
1. node.js与浏览器的命令有一些是不同的

2. 清除浏览器缓存或使用强制刷新（通常是 Ctrl+F5 或 Cmd+Shift+R）

3. **Express**框架和**Gulp**、**Webpack**这些工具服务于JavaScript应用开发中的不同目的和阶段，它们之间是互补关系。

4. **Axios** 是一个工具，用于前端与**API**之间的通信，通过发送HTTP请求来获取或发送数据。API 是后端服务，它定义了如何通过HTTP请求接收和发送数据。两者共同协作，使得前端和后端能够进行数据交换。
   - 例如，如果你正在构建一个需要从第三方服务获取天气信息的Web应用程序，你可以使用Axios 发送一个GET请求到该服务的API，API 处理你的请求并将天气数据以JSON格式返回给你的应用程序。

5. **dotenv** 是一个非常流行的Node.js模块，它允许你将环境变量从一个.env文件加载到process.env中。环境变量是在操作系统级别或者在执行环境级别设置的动态命名值，通常用于存储配置值，比如数据库连接信息或外部服务的API密钥。

6. **require** 和 **import**
    - require 是CommonJS模块规范的一部分，最初是为了Node.js被设计的。
    - import 是ES6（也称为ES2015）的模块规范的一部分，它是JavaScript的一个官方标准。可以被现代浏览器 以及 使用了特定转译步骤（如Babel）的Node.js环境支持。


## DAY86 端口监听 / 实例 vs 包含配置的对象
### 2023/11/7
在 Node.js 中，模块系统遵循 CommonJS 规范，允许你通过 module.exports 导出模块，并通过 require 函数导入模块。

注意在导出的时候（以knex为例）：
- **一个只包含配置的对象**：仅仅包含了连接数据库所需的参数，而不包括用于创建连接、执行查询和处理数据库交互的逻辑。
- **实例化一个对象**：这个实例拥有类中定义的属性和方法。比如：如何构建和执行 SQL 查询，它封装了数据库连接和操作的逻辑，而不仅仅是数据库连接的参数。

## DAY88 自定义启动端口
### 2023/11/9
通过环境变量，自定义启动端口（比如自定义7070为端口）

命令行：
- cmd / (git cmd)
`set PORT=7070`

- powershell
`$env:PORT=7070`

## DAY93 http的请求方法
### 2023/11/14
1. 什么是API？

2. http的请求方法：CRUD
    - create：post()
    - read：get()
    - update：put()、patch()
    - delete：delete()

    等等

3. 什么是**中间件**？ 中间件是介于req(请求)和res(响应)之间的功能模块，用于在服务器接收到请求和发送响应之间，对传入的请求数据进行操作，或者在发送出响应之前对数据进行加工。

4. 具体应用：

    （1）get( )方法：
       
        - 基于json文件，获取数据展示到客户端
    
    （2）use( )方法：中间件。路由也是中间件，所以也用use()方法来建立。


## DAY94 图片等比例缩放
### 2023/11/15
1. 实现图片等比例缩放的方法：
```css
/* 给img外面的容器设置宽高数据 */
width: xx px;
height: xx px;

/* 设置img本身 */
width: 100%;
height: auto;
```

## DAY101 调试排查错误
### 2023/11/22
1. 后端逻辑检查
    - 检查**函数**是否调用？
    - 检查**路由**是否正确：运用日志console.log打印查询结果；注意：如果在函数中使用了 res.render 或 res.json 来发送响应，那么之后的中间件将不会被执行。

2. 数据库查询
    - MySQL等数据库查询语句

3. 前端检查
    - 模板检查
    - AJAX请求触发是否与路由匹配？


## DAY102 require导入、遍历DOM的方法
### 2023/11/23
1. 当使用 require() 函数来导入一个模块时，提供的路径会决定导入的是一个**本地模块**还是一个**npm包**。

    - 本地文件：如果路径以 ./ 或 ../ 开头，Node.js 会将其视为一个文件路径，并在本地文件系统中查找该模块。

    - npm包：如果路径不以 ./ 或 ../ 开头，Node.js 会认为它是一个npm包，并会在 node_modules 目录中查找该模块。

2. 两个遍历DOM方法：
    - **closest**：这个方法从当前元素开始，**向上**遍历 DOM 树，直到找到匹配给定选择器的第一个元素。如果当前元素本身匹配选择器，那么 closest 方法就会返回当前元素。这个方法常用于查找元素的祖先元素。

    - **find**：这个方法从当前元素开始，**向下**遍历 DOM 树，查找所有匹配给定选择器的后代元素，不包括当前元素本身。这个方法用于寻找一个元素内部的子元素。


## DAY103 结合两个数据库表
### 2023/11/24
如何联合两个表？
1. 数据库设计：确保两个表之间包含了关联，有外键字段

2. 查询数据库

3. 传递数据到模板

## DAY104 jQuery用法
### 2023/11/25
1. `toggleClass()`：在元素上添加或删除一个或多个类名。如果指定的类名存在，则删除它；如果不存在，则添加它。

```javascript
$(selector).toggleClass(className, state);   //state 是一个布尔值，用于决定是否添加或移除类名。
```

2. `toArray()`：将 jQuery 对象转换成一个原生的 JavaScript 数组。这允许你使用 JavaScript 的数组方法，比如 .map()、.filter() 和 .every() 等，这些方法是 jQuery 对象本身不提供的。

## DAY106 nestjs
### 2023/11/27
1. `nest new project-name` 创建新文件

2. 在开发环境安装nodemon： `npm i --save-dev nodemon`。然后修改package.json文件里
```json
"scripts": {
  "start:dev": "nodemon --watch src --ext ts --exec ts-node src/main.ts"
}
```
接着 `npm run start:dev` 即可启动nestjs程序

## DAY118 Vue Router
### 2023/12/9
1. 路由模式
    - HTML5 历史模式：使用 createWebHistory 创建基于 HTML5 History API 的路由。这种模式提供干净的 URL，无需 #。但需要适当的服务器配置，以便所有路径请求都返回入口 HTML 文件。
    - 哈希模式：使用 createWebHashHistory 创建基于 URL 哈希的路由。这种模式的 URL 包含 #，适用于所有浏览器，无需特殊服务器配置。

2. 路由导航
    - `<router-link>`：用于在 Vue 应用内部创建导航链接，点击时**不会重新加载**页面，而是动态更新视图。
    - `<a>` 标签：传统的 HTML 链接，**会导致页面重新加载**。用于单页应用时，需要服务器配置支持。

## DAY122
### 2023/12/13 computed使用
在 JavaScript 的箭头函数中，如果使用花括号，这意味着定义一个函数体，需要显式地返回一个值。如果没有 return 语句，函数会默认返回 undefined。
```js
const x = computed(() => {
  return ... ;
});
```

省略花括号的写法：
```js
const x = computed(() =>  ... );
```