# study-web
## 2023/8/14 DAY01
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
