# Vue-learning

[Vue API documents](https://cn.vuejs.org/v2/api/#Vue-nextTick)

## 基础元素

* data

  类似于类的属性，传入响应式的数据
  
* prop

  用于接收父组件传递的数据。可以定义数据类型，或者设施默认值
  
* computed

  开关。根据响应式属性进行计算（data中的数据）
  可定义于组件和实例中，最终被混入到实例中
  
* methods

  可定义于组件和实例中，最终被混入到实例中
  可通过VM 实例访问这些方法

* watch
  
  类型 ` [key: string] : string | function | object `
  
  示例
  
  ```
  var vm = new Vue({
    data: {
      a: 1,
      b: 2,
      c: 3
    },
    watch: {
      a: function (val, oldVal) {
        console.log('new: %s, old: %s', val, oldVal)
      },
      // 方法名
      b: 'someMethod',
      // 深度 watcher
      c: {
        handler: function (val, oldVal) { /* ... */ },
        deep: true
      }
    }
  })
  vm.a = 2 // -> new: 2, old: 1
  ```
  
* template

  挂载元素的内容都将被忽略，除非模板的内容有分发 slot
  如果值以 # 开始，则它用作选项符，将使用匹配元素的 innerHTML 作为模板(不是JQuery ID 选择器 :) )  
  **如果 Vue 选项中包含 render 函数，template 选项将被忽略**

* v-if

  根据表达式的值的真假条件渲染元素。在切换时元素及它的数据绑定 / 组件被销毁并重建
  
* v-show

  根据表达式之真假值，切换元素的 display CSS 属性
  
* key

  使用key，它会基于key的变化重新排列元素顺序，并且会移除key不存在的元素
  不使用key，Vue会使用一种最大限度减少动态元素并且尽可能的尝试修复/再利用相同类型元素的算法
  
  ??
  1. 不使用key, DOM只能添加或者修改，不能删除
  2. 不使用key, 在面对大量数据时，DOM更新的效率和使用key对比，那个更快
  3. 是否存在key滥用


