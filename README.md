# miniVue
简单300行代码实现vue一些核心功能

vue采取数据劫持，配合观察者者模式，通过Object.defineProperty() 来劫持各个属性的setter和getter，在数据变动时，发布消息给依赖收集器dep，去通知观察者，做出对应的回调函数，去更新视图。（也就是在getter中收集依赖，在setter中通知依赖更新。）

其实vue主要就是整合Observer，compile和watcher三者，通过Observer来监听 model数据变化表，通过compile来解析编译模板指令，最终利用Watcher搭起observer 和compile的通信桥梁，达到数据变化=>视图变化，视图变化=>数据变化的双向绑定效果。

## 该代码只简单实现了vue里的
1.v-model（数据的双向绑定）
2.v-bind/v-on
3.v-text/v-html
4.没有实现虚拟dom，采用文档碎片（createDocumentFragment）代替
5.数据只劫持了Object，数组Array没有做处理
