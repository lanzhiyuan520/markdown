#### 								css3常用属性

#### box-shadow

```css
box-shadow : h-shadow v-shadow blur spread color inset
box-shadow : 10px 10px 15px #000 10px inset(outset)
```

参数：

| 参数     | 描述                                     |
| -------- | ---------------------------------------- |
| h-shadow | 水平偏移量                               |
| v-shadow | 垂直偏移量                               |
| blur     | 模糊距离（可选）                         |
| spread   | 阴影尺寸（可选）                         |
| color    | 阴影颜色                                 |
| inset    | 将外部阴影 (outset) 改为内部阴影（可选） |

#### translate()

通过 translate() 方法，元素从其当前位置移动，根据给定的 left（x 坐标） 和 top（y 坐标） 位置参数：

```css
transform : translate(x坐标,y坐标)
transform : translate(100px,200px)
```

#### rotate()

通过 rotate() 方法，元素顺时针旋转给定的角度。允许负值，元素将逆时针旋转。

```css
transform : rotate(旋转的角度)
transform : rotate(30deg)
```

#### scale()

通过 scale() 方法，元素的尺寸会增加或减少，根据给定的宽度（X 轴）和高度（Y 轴）参数：

```css
transform : scale(x轴，y轴)
transform : scale(2,4)  /*scale(2,4) 把宽度转换为原始尺寸的2倍，把高度转换为原始高度的4倍。*/
```

#### skew()

通过 skew() 方法，元素翻转给定的角度，根据给定的水平线（X 轴）和垂直线（Y 轴）参数:

```css
transform : skew(x轴,y轴)
transform : skew(30deg,20deg)   /*skew(30deg,20deg) 围绕 X 轴把元素翻转30度，围绕Y轴翻转20度*/
```

