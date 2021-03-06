# HTML5+CSS3 Notes

## HTML



###### 实体

语法：

​	&实体的名字;

​	&nbst;

​	\&gt;

​	\&lt;

###### \<a>超链接

- target属性：用来指定超链接打开的位置

 可选值：

​	 _self 默认值 在当前页面中打开超链接

​	 _blank 在一个新的页面中打开超链

- 回到顶部：

  可以将超链接的href属性设置为**#**,这样点击超链接以后页面不会发生跳转，而是转到当前页面的顶部的位置

- 回到底部：

  跳转到页面的指定位置，只需将href属性设置 #目标元素的id属性值

```html
<a href="#bottom">去底部</a>
<a id="bottom" href="#">回到顶部</a>
```

- 在开发中#可以作为超链接的路径的占位符使用
- 可以使用 javascript:; 来作为href的属性，此时点击这个超链接什么也不会发生。

###### id属性

- 每个标签都可以添加一个id属性

  id属性就说元素的唯一标识，同一个页面中不可以出现重复的id属性，并且区分大小写

###### img

- 图片标签用来引入外部图片，img标签是一个自结束标签

  img这种元素属于替换元素（块和行内元素之间，具有两种元素的特点）

  属性：

  - src 属性指定的是外部图片的路径（路径规则和超链接是一样的）

  - alt 图片的描述，这个描述默认情况下不会显示，有些浏览器会在图片无法加载时显示，搜索引擎会根据alt中的内容来识别图片，如果不写alt属性则图片不会被搜索引擎所收录
  - width图片的宽度（像素）
  - height 高度
    - 宽度和高度中如果只修改了一个，则另一个会等比例缩放
  - 注意：
    - 一般情况在pc端，不建议修改图片的大小，需要多大的图片久裁多大，但是在移动端经常需要对图片进行缩放。

- 图片的格式
  - jpej(jpg)
    - 支持的颜色笔记丰富，不支持透明效果和动图
    - 一般用来显示照片
  - gif
    - 支持颜色较少，支持简单透明，支持动图
    - 颜色单一的图片，动图
  - png
    - 支持的颜色丰富，支持复杂透明，不支持动图
    - 颜色丰富，复杂透明图片（专为网页而生）
  - webp
    - 是谷歌新推出的专门用来表示网页中的图片的一种格式
    - 它具备其它图片格式的所有优点，而且文件还特别小
    - 缺点：兼容性不好
  - base64
    - 将图片使用base64进行编码，这样可以直接将图片转换为字符，通过字符的形式来引入图片
    - 一般都是一些需要和网页一起加载的图片才会使用base64
- 效果一样，用小的，效果不一，用效果好的

###### audio video

- audio标签用来向页面中引入一个外部的音频文件

  音视频文件引用时，默认情况下不允许用户自己控制播放停止

- 属性

  - controls 是否允许用户控制播放
  - autoplay 音频文件是否自动播放
    - 如果设置了autoplay 则引用在打开页面时会自动播放，但目前来说大部分浏览器都不会自动对音乐进行播放
  - loop 音乐是否循环播放

- 使用video标签来向网页中引入一个视频 使用方法和audio基本相同

```html
<audio src="./source/audio.mp3" controls></audio><!-- 方法一 -->
<audio controls>
    对不起，您的浏览器不支持播放音频！请升级浏览器<!-- 当浏览器不兼容时 source标签引入音频视频无法播放 这段文字就会显示在浏览器中 -->
	<source src="./source/audio.mp3"><!--默认先使用第一个source-->
	<source src="./source/audio.ogg"><!-- 苹果浏览器可能无法使用mp3格式 就会使用这个source下的引用 -->
</audio>


<video controls>
	<source src="./source/flower.webm"> <!--谷歌提供的视频文件 -->
    <embed src="./source/flower.mp4" type="video/mp4"><!-- 考虑兼容IE -->
</video>

<!-- 当想要引入网上的视频但是没有云服务器 可以去各大视频网站上传再复制视频地址 -->
<ifame framborder="0" src="https://....."............
```

## CSS 层叠样式表

CSS用来设置网页中元素的样式

#### CSS编写方式

##### 内联式

##### 内部样式表

##### 外部样式表

- 将样式编写到外部的CSS文件中，可以使用到浏览器的缓存机制，从而加快网页的加载速度，提高用户体验

#### 常用选择器

##### 元素选择器

- 根据标签名来选中指定的元素

  语法：

  - 标签名 { }
  - eg: p {} h1{}  div{}

##### id选择器

- 根据元素的id属性值选中一个元素

  语法：

  - \#id属性值{}
  - eg: \#box{} #red{}

##### 类选择器

- 根据元素的class属性值选中一组元素

  语法：

  - .class属性值{}   （可以重复使用）

- class是一个标签的属性，它和id类似，不同的是class可以重复使用，可以通过class属性为元素分组，可以同时为一个元素指定多个class属性

##### 通配选择器

- 可以选中页面中的所有元素

  语法: 

  - \* {}

#### 复合选择器

##### 交集选择器

- 选中同时符合多个条件的元素

  语法：

  - 选择器1选择器2选择器n{}

  注意点：

  - 交集选择器中如果有元素选择器，必须使用元素选择器开头

##### 选择器分组（并集选择器）

- 同时选择多个选择器对应的元素

  语法：

  - 选择器1,选择器2,选择器n{}

#### 关系选择器

###### 父元素

- 直接包含子元素的元素叫做父元素

###### 子元素

- 直接被父元素包含的元素是子元素

###### 祖先元素

- 直接或间接包含后代元素的元素叫做祖先元素
- 一个元素的父元素 也是它的祖先元素

###### 后代元素

- 直接或间接被祖先元素包含的元素叫做祖先元素
- 子元素也是后代元素

###### 兄弟元素

- 拥有相同父元素的元素是兄弟元素

##### 子元素选择器

- 选中指定父元素的指定子元素

  语法：

  - 父元素 > 子元素

##### 后代元素选择器

- 选中指定元素内的指定后代元素

  语法：

  - 祖先 后代

##### 选择下一个兄弟

- 语法：
  - 前一个 + 下一个

 （一定要紧接着的元素，假如中间隔了一个其它元素，则不起作用）

##### 选择下边所有的兄弟

- 语法：
  - 兄 ~ 弟

#### 属性选择器

```html
<p title="number">12345678</p> 
<!-- 在页面中当鼠标移动到这段文字 就会显示出number这个提示文字 -->

<style>
    p[title]{
        color:orange;
    }
    /*只要是包含title的p元素都会选中设置颜色为orange*/
    p[title=number]{
        color:blue;
    }
    /*只选中包含title且值为number的p元素*/
</style>

```

- 语法:

  [属性名] 选择含有指定属性的元素

  [属性名=属性值] 选择含有指定属性和属性值的元素

  [属性名^=属性值] 选择属性值以指定值开头的元素

  [属性名$=属性值] 选择属性值以指定值结尾的元素

  [属性名*=属性值] 选择属性值中含有某值的元素

#### 伪类选择器

##### 伪类

- 伪类（不存在的类，特殊的类)

  - 伪类用来描述第一个元素的特殊状态

    比如:第一个子元素，被点击的元素，鼠标移入的元素....

- 特点:一般情况下都是使用 : 开头

  ​	:first-child 第一个子元素

  ​	:last-child 最后一个子元素

  ​	:nth-child() 选中第n个子元素

  ​			特殊值：

  ​					n 第n个 n的范围是0-正无穷

  ​					2n 或者 even 表示选中偶数位的元素

  ​					2n+1 或者 odd 表示选中奇数位的元素

  - 注意：以上这些伪类都是根据所有的子元素进行排序
  - :first-of-type
  - :last-of-type
  - :nth-of-type
  
- 这几个伪类的功能和上述的类似，不同点是他们是在同类型元素中进行排序
  
- :not() 否定伪类
  
  - 将符合条件的元素从选择器中去
  
    ```css
    ul > li:not(:nth-of-type(3)){
        color:yellowgreen;
    }
    /*将ul无序列表下除了第三个li以外的其它li设置为黄绿色*/
    ```
  ```
  
    
  ```

##### 超链接的伪类

- :link 用来表示没访问过的链接（正常的链接)

- :visited 用来表示访问过的链接
  - 由于隐私的原因，所以visited这个伪类只能修改链接的颜色
- :hover 用来表示鼠标移入的状态
- :active 表示鼠标点击

#### 伪元素选择器

- 伪元素，表示页面中一些特殊的并不存在的元素（特殊的位置)

- 伪元素使用  ::  开头

  - ::first-letter 表示第一个字母

  - ::first-line 表示第一行

  - ::selection 表示选中的内容

  - ::before 元素的开始

  - ::after 元素的最后

    - before和after 必须结合content属性来使用

    ```css
    div::before{
        content:'abc';
        color:blue;
    }
    /*用css设置的content内容会在div内容的最前面添加一个abc，这个abc是无法用鼠标选中的，因为是由css设置的*/
    ```

### 选择器的权重

- 样式的冲突：
  - 当我们通过不同的选择器，选中相同的元素，并且位相同的样式设置不同的值时，此时发生了样式的冲突
  - 当样式发生冲突时，选择器的权重（优先级）决定了应用哪个样式
- 选择器的权重
  - 内联样式  			  1,0,0,0
  - id选择器                 0,1,0,0
  - 类和伪类选择器     0,0,1,0
  - 元素选择器             0,0,0,1
  - 通配选择器              0
  - 继承的样式              没有优先级

- 比较优先级时，需要将所有的选择器的优先级进行相加计算，最后优先级越高，则越优先显示（分组选择器是单独计算）
  - 选择器的累加不会超过其最大的数量级，类选择器再高也不会超过id选择器
  - 如果优先级计算后相同，则优先使用靠下的样式

### 布局

#### 元素的水平方向布局：

- 元素在其父元素中水平方向的位置由以下几个属性共同决定：

  margin-left

  border-left

  padding-left

  width

  padding-right

  border-right

  margin-right

- 一个元素在其父元素中，水平布局必须要满足以下等式：

  margin-left+border-left+padding-left+width+padding-right+border-right+margin-right = 其父元素内容区的宽度（必须满足）

- 以上等式必须满足，如果相加结果使等式不成立，则称为过渡约束，则等式会进行调整

  调整的情况：

  - 如果7个值中没有auto的情况，则浏览器会自动调整margin-right的值使等式满足

  - 这7个值中有三个值和设置为auto

    width 

    margin-left

    margin-right

    - 如果某个值为auto，则会自动调整为auto的那个值使等式成立

      0 + 0 + 0 + auto + 0 + 0 + 0 =800   auto = 800

      0 + 0 + 0 + auto + 0 + 0 + 200 =800   auto = 600

      200 + 0 + 0 + auto + 0 + 0 + 200 =800   auto = 400

      auto + 0 + 0 + 200 +0 +0 +auto = 800 auto=300

    - 如果将一个宽度和一个外边距设置为auto，则宽度会调整到最大，设置为auto的外边距会自动为0

    - 如果三个值都设置为auto，则外边距都是0，宽度最大

    - 如果将两个外边距设置为auto，宽度值固定，则会将外边距设置为相同的

      - 所以常利用这一个特点来使一个元素在其父元素中水平居中

      - eg:

        width:xxxpx;

        margin:0 auto;

#### 垂直方向布局

- 子元素是在父元素的内容区中排列的，如果子元素的大小超过了父元素，则子元素会从父元素中溢出

  使用overflow属性来设置父元素如何处理溢出的子元素

  可选值:

  - visible 默认值 子元素会从父元素中溢出，在父元素外部的位置显示
  - hidden 溢出内容将会被裁剪不会显示
  - scroll 生成两个滚动条，通过滚动条来查看完整的内容
  - auto 根据需要生成滚动条 

  overflow-x

  overflow-y 

  单独处理水平方向或者垂直方向的溢出

#### 外边距的折叠

- 相邻的垂直方向外边距会发生重叠现象
- 兄弟元素：
  - 兄弟元素间的相邻垂直外边距会取两者之间的较大值（两者都是正值）
  - 特殊情况：
    - 如果相邻的外边距一正一负，则取两者的和
    - 如果相邻的外边距都是负值，则取两者中绝对值较大的
- 父子元素
  - 父子元素间的相邻外边距，子元素的会传递给父元素（上外边距）
  - 父子外边距的折叠会影响到页面布局，必须进行处理;

#### 行内元素的盒模型

- 行内元素不支持设置宽度和高度
- 行内元素可以设置padding，但是垂直方向padding不会影响页面布局
- 行内元素可以设置border，垂直方向的border不会影响页面的布局
- 行内元素可以设置margin，垂直方向的margin不会影响页面的布局

##### display

- 用来设置元素显示的类型

  可选值：

  ​	inline 将元素设置为行内元素

  ​	block 将元素设置为块元素

  ​	inline-block 将元素设置为行内块元素

  ​		行内块，既可以设置宽度和高度，又不会独占一行

  ​	table 将元素设置为一个表格

  ​	none 元素不在页面中显示

##### visibility

- 用来设置元素的显示状态

  可选值：

  ​	visible 默认值，元素在页面中正常显示

  ​	hidden 元素在页面中隐藏 不显示，但是依然占据页面中的位置

### 浮动float

- 通过浮动可以使一个元素向其父元素的左侧或右侧移动，使用 float 属性来设置于元素的浮动

  可选值：

  ​	none 默认值，元素不浮动

   	left 元素向左浮动

  ​	right 元素向右浮动

  注意：元素设置浮动以后，水平布局的等式便不需要强制成立，元素设置浮动以后，会完全从文档流中脱离，不再占用文档流的位置，所以元素下边的还在文档流中的元素会自动向上移动

- 浮动的特点：

  1. 浮动元素会完全脱离文档流，不再占据文档流中的位置
  2. 设置浮动以后元素会向父元素的左侧或右侧移动
  3. 浮动元素默认不会从父元素中移出
  4. 浮动元素向左或向右移动时，不会超过它前边的其它浮动元素。
  5. 如果浮动元素的上边是一个没有浮动的块元素，则浮动元素无法上移
  6. 浮动元素不会超过它上边的浮动的兄弟元素，最多和它一样高

- 总结:浮动可以让页面中的元素水平排列，通过浮动可以制作一些水平方向的布局

#### 脱离文档流的特点

- 元素设置浮动以后，会从文档流中脱离，从文档流中脱离后，元素的一些特点也会发生改变

- 特点：

  - 块元素：

    1. 块元素不再独占页面的一行
    2. 脱离文档流以后，块元素的宽度和高度默认都被内容撑开

  - 行内元素：

    ​	行内元素脱离文档流以后会变成块元素，特点和块元素一样

  - 脱离文档流以后，不需要再区分块和行内了

#### 高度塌陷问题

- 在浮动布局中，父元素的高度默认是被子元素撑开的，当子元素浮动后，其会完全脱离文档流，子元素会从文档流中脱离将会无法撑起父元素的高度，导致父元素的高度丢失

  父元素高度丢失后，其下的元素会自动上移，导致页面布局混乱

  

#### BFC（Block Formatting Context)块级格式化环境

- BFC是CSS中的一个隐含的属性，可以为一个元素开启BFC，该元素会变成一个独立的布局区域
- 元素开启BFC后的特点：
  1. 开启BFC的元素不会被浮动元素所覆盖
  2. 开启BFC的元素子元素和父元素外边距不会重叠
  3. 开启BFC的元素可以包含浮动的子元素
- 可以通过一些特殊的方式来开启元素的BFC：
  1. 设置元素的浮动（宽度会丢失）--不推荐
  2. 讲元素设置为行内块（宽度也会丢失）--不推荐
  3. 将元素的overflow设置为非visible的值
     - 常用的方式，为元素设置overflow:hidden 开启其BFC 以使其可以包含浮动元素

##### clear

- 如果不希望某个元素因为其它元素浮动的影响而改变位置，看可以使用clear属性来清除浮动元素对当前元素所产生的影响。

- 作用：清除浮动元素对当前元素所产生的影响
- 可选值：
  - left 清除左侧浮动元素对当前元素的影响
  - right 清除右侧浮动元素对当前元素的影响
  - both 清除两侧中最大影响的那侧
- 原理：
  - 设置清除浮动以后，浏览器会自动为元素添加一个上外边距，使其位置不受其它元素影响

#### 高度塌陷最终解决方案

- 使用after伪元素来解决高度塌陷

```html
<div class="box1">
	<div class="box2">
        <!-- <div class="box3"></div> --> 
    </div>
</div>
```

```css
.box1{
    border:10px red solid;/* 为父元素设置一个红色边框 */
}
.box2{
    width:100px;
    height:100px;
    background-color:#bfa;
    float:left;
    /*让子元素box2浮动*/
}
/* 这种为box3设置清除浮动的方式，是在使用html来改变结构，但是目的是为了修改样式，所以应该使用css来操作而不是采用html*/
/*设置box3清除浮动后，box3就会跟着box2，即使box2浮动，box3依然可以撑开父元素，达到父元素根据子元素的内容而改变大小*/
/*
.box3{
    clear:both;
}*/

/*在box1后添加一个伪元素，通过css的方式来达到效果而不是html改变结构的方式*/
.box1::after{ 
    content:'';/*将伪元素内容设置为空*/
    display:block;/*将伪元素改为块级元素*/
    clear:both;/*清除浮动*/
}
```

###### clearfix

- clearfix 这个样式可以同时解决高度塌陷和外边距重叠的问题，当遇到这些问题，直接使用clearfix即可。

  ```html
  <div class="box1">
  	<div class="box2"></div>
  </div>
  ```

  ```css
  .box1{
      width:200px;
      height:200px;
      background-color:#bfa;
  }
  .box2{
      width:100px;
      height:100px;
      background-color:orange;
      margin-top:100px;
  }
  .clearfix::before,
  .clearfix::after{
      content:'';
      display:table;
      clear:both;
  }
  
  ```

  

### 定位

- 定位（position）是一种更高级的布局手段

- 通过定位可以将元素摆放到页面的任意位置

- 使用position属性来设置定位

  可选值：

  ​	static 默认值，元素是静止的没有开启定位

  ​	relative 开启元素的相对定位

  ​	absolute 开启元素的固定定位

  ​	fixed 开启元素的固定定位

  ​	sticky 开启元素的沾滞定位

#### 相对定位

- 当元素的position属性值设置为relative时则开启了元素的相对定位

- 相对定位的特点：

  1. 元素开启相对定位以后，如果不设置偏移量元素不会发生任何变化
  2. 相对定位是参照于元素在文档流中的位置进行定位的
  3. 相对定位会提升元素的层级
  4. 相对定位不会使元素脱离文档流
  5. 相对定位不会改变元素的性质，块还是块，行内还是行内

- 偏移量（offset）

  - 当元素开启了定位以后，可以通过偏移量来设置元素的位置

    top

    - 定位元素和定位位置上边的距离

    bottom

    - 定位元素和定位位置下边的距离

    - 定位元素垂直方向的位置由top和bottom两个属性来控制，通常只会使用其中一个
      - top 值越大，定位元素越向下移动
      - bottom值越大，定位元素越向上移动

    left

    - 定位元素和定位位置左侧的距离

    right

    - 定位元素和定位位置右侧的距离
    - 定位元素水平方向的位置由left和right两个属性来控制，通常只会使用其中一个
      - left越大元素越靠右
      - right越大元素越靠左

#### 绝对定位

- 当元素的position属性值设置为absolute时，则开启了元素的绝对定位

- 绝对定位的特点：

  1. 开启绝对定位后，如果不设置偏移量元素的位置不会发生变化
  2. 开启绝对定位后，元素会从文档流中脱离
  3. 绝对定位会改变元素的性质，行内变成块，块的高度被内容撑开
  4. 绝对定位会使元素提升一个层级
  5. 绝对定位元素是相对于其包含块进行定位的

  包含块（ containing block）

  - 正常情况下：

    包含块就是离当前元素最近的祖先块元素

  - 绝对定位的包含块：

    - 包含块就是离它最近的的祖先元素，如果所有的祖先元素都没有开启定位，则根元素就是它的包含块

  - html(根元素、初始包含块)

- 只要position的值不是static就是开启了定位

#### 固定定位

- 将元素的position属性值设置为fixed则开启了元素的固定定位
- 固定的定位也是一种绝对定位，所以固定定位的大部分特点都和绝对定位一样
  - 唯一不同的是固定定位永远参照于浏览器的视口进行定位
  - 固定定位的元素不会随网页的滚动条滚动

#### 粘滞定位

- 当元素的position属性设置为sticky时则开启了元素的沾滞定位
- 沾滞定位和相对定位的特点基本一致，不同的是沾滞定位可以在元素到达某个位置时将其固定

#### 绝对定位元素的布局

水平布局

​	left + margin-left + border-left + padding-left + width + padding-right + border-right + margin-right +right = 包含块内容区的宽度

- 当我们开启了绝对定位后:

  - 水平方向的布局等式就需要添加left 和 right 两个值

  - 此时规则和之前一样只是多添加了两个值：

    - 当发生过度约束：
      - 如果9个值中没有 auto 则自动调整right的值以使等式满足
      - 如果有auto 则自动调整auto的值使等式满足
    - 可设置auto的值
      - margin width left right
    - 因为left 和 right 的值默认是auto，所以如果不知道left 和 right 则等式不满足时，会自动调整这两个值

  - 垂直方向布局的等式也必须要满足

    top + margin-top/bottom + padding-top/bottom + boder-top/bottom + height = 包含块的高度

```html
<div class="box1">
    <div class="box2">
        
    </div>
</div>
```

```css
.box1{
    width:500px;
    heitht:200px;
    background-color:#bfa;
    position:relative;
}
.box2{
    width:100px;
    height:100px;
    background-color:orange;
    position:absolute;
    margin:auto; /*通过调整magin+left,right,top,bottom值设置为0达到居中效果*/
    left:0;
    right:0;
    top:0;
    bottom:0;
}
```

#### 元素的层级

- 对于开启了定位元素，可以通过z-index属性来指定元素的层级
- z-index需要一个整数作为参数，值越大元素的层级越高，元素的层级越高越优先显示
- 如果元素的层级一样，则优先显示靠下的元素
- 祖先的元素的层级再高也不会盖住后代元素

### 图标字体

图标字体（iconfont)

- 在网页中经常需要使用一些图标，可以通过图片来引入图标

  但是图片大小本身较大，且使用不灵活

- 可以在使用图标时，将图标设置为字体，通过font-face的形式来使用图标

fontawsome 使用步骤

 1. 下载 官方网站https://fontawesome.com/

 2. 解压

 3. 将css和webfonts移动到项目中

 4. 将all.css引入到网页中

 5. 使用图标字体

    - 直接通过类目来使用图标字体

      class="fas fa-bell"

      class="fab fa-accessible-icon"

##### 通过伪元素设置图标字体

1. 找到要设置图标的元素通过before或after选中

2. 在content中设置字体的编码

3. 设置字体的样式

   fab

   font-family : 'Font Awesome 5 Brands';

   fas

   font-family:'Font Awesome 5 Free';

   font-weight:900;

```css
li::before{
    content:'\f1b0';
    font-family:'Font Awesome 5 Free';
    font-weight:900;
    color:blue;
    margin-right:10px;
}
```



##### 通过实体来使用图标字体

&#x图标的编码；

```html
<span class="fas">&#xf0f3;</span>
```

#### 文本的样式

##### text-align 

- 文本的水平对齐
  - left 左侧对齐
  - right 右侧对齐
  - center居中对齐
  - justify 两端对齐

##### vertical-align 

- 设置元素垂直对齐的方式

  - baseline 默认值 基线对齐
  - top顶部对齐
  - bottom 底部对齐
  - middle 居中对齐

  当在p标签插入某张图片时，因为图片属于替换元素，特点和字相同，所以图片对齐也是默认基线对齐，只要设置图片的vertical-align属性不是默认值即可把图片的缝隙给清除掉

##### text-decoration

- 设置文本修饰
  - none 什么都没有
  - underline下划线
  - line-through 删除线
  - overline 上划线

##### white-space 

- 设置网页如何处理空白
  - normal 正常
  - nowrap 不换行
  - pre 保留空白

```css
.box2{
    width:200px;
    /*设置文本不换行*/
    white-space:nowrap;
    /*将溢出文本裁剪*/
    overflow:hidden;
    /*设置溢出样式为省略号 从而达到网站新闻简短接受带省略号的效果*/
    text-overflow:ellipsis;
        
}
```

### 图片

#### 雪碧图

- 将多个小图片统一保存到一个大图片中，然后通过调整background-position来显示相应的图片，这样图片就会同时加载到网页中，可以有效避免出现闪烁的问题

- 这个技术应用十分广泛，被称为CSS-Sprite，称为雪碧图

- 使用步骤：

  1. 确定要使用的图标
  2. 测量图标的大小
  3. 根据测量结果创建一个元素
  4. 将雪碧图设置为元素的背景图片
  5. 设置一个偏移量以显示正确的图片

- 雪碧图特点：

  一次性将多个图片加载进页面，降低请求的次数，加快访问速度，提升用户体验

#### 渐变

##### 线性渐变

- 颜色沿着一条直线发生变化

  linear-gradient()

  ```css
  background-image:linear-gradient(red,yellow);
  /*红色在开头，黄色在结尾，中间是过度区域*/
  ```

- 线性渐变的开头，可以指定一个渐变的方向

  to left

  to right

  to bottom

  to top

  deg deg表示度数

  turn表示圆

- 渐变可以同时指定多个颜色，多个颜色默认情况下平均分布，也可以手动指定渐变分布情况

  ```css
  background-image:linear-gradient(red 50px,yellow);/*从50px开始过渡，之前都是红色*/
  ```

- repeating-linear-gradient() 可以平铺的线性渐变

##### 径向渐变

- radial-gradient() 径向渐变（放射性的效果）

- 默认情况下径向渐变圆心的形状根据元素的形状来计算的

  - 正方形-->圆形

  - 长方形-->椭圆形

  - 也可以手动指定径向渐变的大小

    - circle
    - ellipse
    - 调整像素大小

  - 也可以指定渐变的位置

    - 语法：
          radial-gradient(大小 at 位置, 颜色 位置 ,颜色 位置 ,颜色 位置)
              大小：
                  circle 圆形
                  ellipse 椭圆
                  closest-side 近边	
                  closest-corner 近角
                  farthest-side 远边
                  farthest-corner 远角

      ​		位置：
      ​        	top right left center bottom




### animation

#### 过渡（transition）

- 通过过渡可以指定一个属性发生变化时的切换方式

- 通过过渡可以创建一些非常好的效果，提升用户的体验

- transition-property: 指定要执行过渡的属性 多个属性间使用,隔开 如果所有属性都需要过渡，则使用all关键字

  大部分属性都支持过渡效果，注意过渡时必须是从一个有效数值向另外一个有效数值进行过渡

- transition-duration: 指定过渡效果的持续时间

​        时间单位：s 和 ms 1s = 1000ms

​       /* transition-duration: 100ms, 2s; */

​       /* transition-duration: 2s; */

- transition-timing-function: 过渡的时序函数

​        指定过渡的执行的方式 

​        可选值：

​          ease 默认值，慢速开始，先加速，再减速

​          linear 匀速运动

​          ease-in 加速运动

​          ease-out 减速运动

​          ease-in-out 先加速 后减速

​          cubic-bezier() 来指定时序函数

​            https://cubic-bezier.com

​          steps() 分步执行过渡效果

​            可以设置一个第二个值：

​              end ， 在时间结束时执行过渡(默认值)

​              start ， 在时间开始时执行过渡

​       	/* transition-timing-function: cubic-bezier(.24,.95,.82,-0.88); */

​       	/* transition-timing-function: steps(2, start); */

- transition-delay: 过渡效果的延迟，等待一段时间后在执行过渡 
- transition 可以同时设置过渡相关的所有属性，只有一个要求，如果要写延迟，则两个时间中第一个是持续时间，第二个是延迟  
- transition:2s margin-left 1s cubic-bezier(.24,.95,.82,-0.88);



#### 动画

- 动画和过渡类似，都是可以实现一些动态的效果，不同的是过渡需要在某个属性发生变化时才会触发

  动画可以自动触发动态效果

- 设置动画效果，必须先要设置一个关键帧，关键帧设置了动画执行每一个步骤

```css
/* animation-name: 要对当前元素生效的关键帧的名字 */
/* animation-name: test; */

/* animation-duration: 动画的执行时间 */
/* animation-duration: 4s; */

            

/* 动画的延时 */
/* animation-delay: 2s; */

/* animation-timing-function: ease-in-out; */

/* 
animation-iteration-count 动画执行的次数 
可选值：
次数
infinite 无限执行
*/
/* animation-iteration-count: 1; */

/*
animation-direction
指定动画运行的方向
可选值：
normal 默认值  从 from 向 to运行 每次都是这样 
reverse 从 to 向 from 运行 每次都是这样 
alternate 从 from 向 to运行 重复执行动画时反向执行
alternate-reverse 从 to 向 from运行 重复执行动画时反向执行

*/
/* animation-direction: alternate-reverse; */

/* 
animation-play-state: 设置动画的执行状态 
                可选值：
                    running 默认值 动画执行
                    paused 动画暂停
            */
            /* animation-play-state: paused; */

            /* 
            animation-fill-mode: 动画的填充模式
                可选值：
                    none 默认值 动画执行完毕元素回到原来位置
                    forwards 动画执行完毕元素会停止在动画结束的位置
                    backwards 动画延时等待时，元素就会处于开始位置
                    both 结合了forwards 和 backwards
            */
            /* animation-fill-mode: both; */
            animation: test 2s 2 1s alternate;

            
```



#### 变形平移

-  变形就是指通过CSS来改变元素的形状或位置
  - 变形不会影响到页面的布局
    - transform 用来设置元素的变形效果
      - 平移：
        translateX() 沿着x轴方向平移
        translateY() 沿着y轴方向平移
        translateZ() 沿着z轴方向平移
        - 平移元素，百分比是相对于自身计算的   

- 可以完成移入某个元素达到移动有点飘起来的效果

  ```css
  /*为box4设置一个移入效果*/
  .box4{
              width: 220px;
              height: 300px;
              background-color: #fff;
              float: left;
              margin: 0 10px;
              transition:all .3s;
          }
  
  .box4:hover{
  transform: translateY(-4px);
  box-shadow: 0 0 10px rgba(0, 0, 0, .3)
          }
  ```



#### Z轴平移

- z轴平移，调整元素在z轴的位置，正常情况就是调整元素和人眼之间的距离，
  - 距离越大，元素离人越近
  - z轴平移属于立体效果（近大远小），默认情况下网页是不支持透视，如果需要看见效果，必须要设置网页的视距

#### 缩放

```css
/* 变形的原点 默认值 center*/
/* transform-origin:20px 20px;  */

.box1:hover{
        /* 
            对元素进行缩放的函数：
                scaleX() 水平方向缩放
                scaleY() 垂直方向缩放
                scale() 双方向的缩放
        */
        transform:scale(2)
    }
```
### less

- less是一门css的预处理语言
  - less是一个css增强版，通过less可以编写更少的代码实现更强大的样式
  - 在less中添加了许多的新特性：像对变量的支持、对mixin的支持……
  - less语法大体上和css语法一直，但是less中

```less

//变量，在变量中可以存储一个任意的值
// 并且我们可以在需要时，任意的修改变量中的值
// 变量的语法： @变量名
@a:200px;
@b:#bfa;
@c:box6;

.box5{
    //使用变量是，如果是直接使用则以 @变量名 的形式使用即可
    width: @a;
    color:@b;
}

//作为类名，或者一部分值使用时必须以 @{变量名} 的形式使用
.@{c}{
    width: @a;
    background-image: url("@{c}/1.png");
}

@d:200px;
@d:300px;

div{
    // 变量发生重名时，会优先使用比较近的变量
    @d:115px;
    width: @d;
    height: @e;
}

//可以在变量声明前就使用变量
@e:335px;
```



// 并且我们可以在需要时，任意的修改变量中的值

// 变量的语法： @变量名



## 练习

```css
/*小米logo+切换效果*/

/* 设置logo的h1 */
.header .logo{
    float: left;
    margin-top: 22px;
    width: 55px;
    height: 55px;
    position: relative;
    overflow: hidden;
    /* 隐藏logo中的文字 */
    text-indent: -9999px
}

/* 统一设置logo的超链接 */
.header .logo a{
    position: absolute;
    width: 55px;
    height: 55px;
    left: 0;
    background-color: #FF6700;
    background-image: url(../img/mi-logo.png);
    background-position: center;
    transition: left 0.3s;
}

/* 设置home图片 */
.header .logo .home{
    background-image: url(../img/mi-home.png);
    left: -55px;
}

/* 设置鼠标移入以后两个图标的位置 */
.header .logo:hover .mi{
    left: 55px;
}

.header .logo:hover .home{
    left: 0;
}
```

```html
<!-- 设置网站图标 -->
在标题栏和收藏栏的网站图标
网站图片一般都存储在网站的根目录下，名字一般都叫做favicon.ico
<link rel="icon" href="./favicon.ico">
```

