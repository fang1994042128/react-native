<h1>reactive native 文档  </h1>


 **状态机制**

* 在React Native中，整个UI都是一个component树，React Native的UI更新逻辑也是依赖于这个树来实现的。每个component都有state这个属性，以及自己的生命周期。每一次componen的state改变的时候，React Native在后台会调用render：function（）这个方法去重新渲染视图，不会重新绘制UI。

   > https://facebook.github.io/react/docs/thinking-in-react.html

**开放接口**

* 由于整个UI都是component树，有时候需要在外部使用用component的属性，React Native每个component都有property属性。this.props 对象的属性与组件的属性一一对应。
 
 >   https://facebook.github.io/react/docs/transferring-props.html

**手势应答系统**

* 用户用不同的方式触摸屏幕，从而给用户不同的体验就是依赖这个依赖的系统。

1. 反馈/高亮——显示给用户是什么正在处理他们的触摸，以及当他们释放手势时，会发生什么 

2. 撤销的能力——当做一个动作时，用户应该能够在触摸过程中通过移动手指中止该动作。

>https://facebook.github.io/react-native/docs/gesture-responder-system.html#content