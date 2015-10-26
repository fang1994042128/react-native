<h1>reactive native 文档  </h1>


 **状态机制**

* 在React Native中，整个UI都是一个component树，React Native的UI更新逻辑也是依赖于这个树来实现的。每个component都有state这个属性，以及自己的生命周期。每一次componen的state改变的时候，React Native在后台会调用render：function（）这个方法去重新渲染视图，不会重新绘制UI。

   > <a herf=https://facebook.github.io/react/docs/thinking-in-react.html>
   		https://facebook.github.io/react/docs/thinking-in-react.html  </a>

**开放接口**

* 由于整个UI都是component树，有时候需要在外部使用用component的属性，React Native每个component都有property属性。this.props 对象的属性与组件的属性一一对应。
 
 >  <a herf=https://facebook.github.io/react/docs/transferring-props.html>
 		https://facebook.github.io/react/docs/transferring-props.html </a>

**手势应答系统**

* 用户用不同的方式触摸屏幕，从而给用户不同的体验就是依赖这个依赖的系统。

1. 反馈/高亮——显示给用户是什么正在处理他们的触摸，以及当他们释放手势时，会发生什么 

2. 撤销的能力——当做一个动作时，用户应该能够在触摸过程中通过移动手指中止该动作。

> <a herf=https://facebook.github.io/react-native/docs/gesture-responder-system.html#content>
	https://facebook.github.io/react-native/docs/gesture-responder-system.html#content  </a>


FB为什么推出React，它解决的问题
-------
1.  **要讲React的实质作用那一定不能脱离Flux模型**
    <ul>
                Flux是为了解决MVC模型中数据流向不一致的问题的
![在这里输入图片描述][1]
                Flux是来一次数据刷新一下界面.
                Flux的（大致）做法是：来新的数据了，好，我把它Merge到客户端的旧数据中，然后把客户                端存着的所有数据交给一个Render，然后把整个HTML从头到尾渲染一边，最后把新的HTML替换掉现    有的HTML就好啦！ 
                ![在这里输入图片描述][2]                                                          
                 **但是这样每次数据都更新一次界面，用户体验相当的差!!!!!!**      
    </ul>
2. **React 解决问题办法**
    <ul>其原理是写看起来像是DOM的JS代码，然后生成ReactDOMElement的对象，而不是真正的DOM，然后把新的Virtual DOM Tree跟用户正在看的DOM Tree做个Diff，然后用最小的改动量Update整个网页。
    </ul>



  [1]: https://pic4.zhimg.com/9256957d0674965401a1733a8b20c0a7_r.jpg
  [2]: https://pic4.zhimg.com/124ebc5f080b831c2501997a861c71d7_r.jpg