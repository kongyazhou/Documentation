# Vue实例

## 构造器

## 属性和方法

vm.data 属性

vm.$data === data // -> true
vm.$el === document.getElementById('example') // -> true

// $watch 是一个实例方法
vm.$watch('a', function (newVal, oldVal) {
  // 这个回调将在 `vm.a`  改变后调用
})


## 生命周期钩子

beforeCreate

created，这个钩子在实例被创建之后被调用

beforeMount

mounted

beforeUpdate

updated

beforeDestroy

destroyed

# 模板语法

## 指令

## 过滤器

## 缩写

# 计算属性

computed:
methods:
watch:

## 事件修饰符

通过由点(.)表示的指令后缀来调用修饰符。

只能对原生的 DOM 事件起作用。

.stop
.prevent
.capture
.self
.once
event.preventDefault() 或 event.stopPropagation()

## 按键修饰符

.enter
.tab
.delete (捕获 “删除” 和 “退格” 键)
.esc
.space
.up
.down
.left
.right
.ctrl
.alt
.shift
.meta

- [Vue官网](https://cn.vuejs.org/)
- [Vue教程](https://cn.vuejs.org/v2/guide/)
