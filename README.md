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
