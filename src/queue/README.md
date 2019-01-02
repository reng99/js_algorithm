## 队列

> 先进先出

### 相关方法

**1. shift()**

移除数组中的第一个元素

```javascript
let arr = ['hello', 'world'];

// print 'hello'
arr.shift();
```

**2. unshift()**

在数组的开始位置添加元素

```javascript
let arr = ['world'];

// print 'hello world'
arr.unshift('hello').join(' ');
```