# lazyLoadImg
三种懒加载图片的方式

思路：图片初始化不设src属性，在data-src上写上正确地址，在适当时候将src加上并把data-src值赋给它

demo1
clientHeight-屏幕可视窗口高度
offsetTop    元素距离文档最顶部的距离
scrollTop    滚动条竖向距离
offsetTop<clientHeight+scrollTop=》此时图片src赋值为正确值

demo2
通过getBoundingClientRect()方法来获取元素的大小以及位置,top【元素的顶部相对文档顶部】
top<clientHeight 时-图片处于马上被看到的临界值-图片src赋值为正确值

demo3
IntersectionObserver可以自动观察元素是否在视口内（Chrome 51+ 已经支持，IE完全不支持）
