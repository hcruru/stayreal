# CSSfloat浮动

## float的特性

- 最初float是用于给文字添加环绕效果，即为图片设置float属性 class="float-left"就能够实现文字环绕图片显示。

### 包裹与破坏

- 包裹的三种行为：收缩、坚挺、隔绝

  即：BFC块级格式化上下文

#### 浮动的破坏性

- 浮动具有破坏性:使得父元素塌陷

  - 搞笑的例子:动画视频中那个可爱的小男孩，被父元素限制，以至于不能和美女接触，当添加了float:left;浮动后，使得父元素塌陷，他就可以和美女接触了！！！

    （也正是如此，float最初是用于实现文字环绕效果的）

- 浮动的破坏性只是单纯为了实现文字环绕效果——因此，父容器高度塌陷是一个标准特性，不是bug。

#### 清除浮动

- 清除浮动带来的影响：

  - 方法一：插入clear:both;

  - 方法二：父元素BFC或haslayout (BFC是高级浏览器特有的概念)

    - 方法差异：

      1.clear只是添加了一个"索道"，可以照样与外部连接

      2.haslayout则是封闭了一个空间

- clear通常应用形式：

  1.HTML block水平元素底部走起 

  2.CSS after伪元素底部生成

  - 但12其实都有不足之处，所以现在有权衡后的策略

  - IE8以上浏览器：

    .clearfix:after{ content:"; display: block; height: 0; overflow: hidden; clear:both;}

  - IE6\7:

    .clearfix{ *zoom:1;}

    - 可以简写为 .fix:after{} 和 .fix{}

  - 更好的方法：.clearfix:after{conten:"; **display:table**; clear:both;}

- 注意: .clearfix应用在包含浮动子元素的**父级元素**上。

#### 浮动的滥用

- 浮动可以使元素block块状化（砖头化）；
- 破坏性造成的紧密排列特性（去空格化）；
  - 容易出现问题：
    - 容错性差
    - 需要元素固定，重用性低
    - 兼容性差，低版本浏览器不适应

## float流体布局

## float兼容性