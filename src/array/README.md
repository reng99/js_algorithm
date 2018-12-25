## 数组

> 一个存储元素的线性集合

### 创建数组的方式

**1. 通过[]操作符声明**

```javascript
let arr = [];
```

**2. 调用Array的构造函数创建**

```javascript
let arr = new Array();
```

### 数组的一些属性

**1. length**

`length`表示数组的长度。

### 数组的一些方法

**1. splice(index,howmany,item1,...itemx)**

`splice()`方法是数组中最强大的方法。可以实现对数组的删除，插入和删除。index参数为整数且必需，规定添加/删除项目的位置，使用负数可从数组结尾处规定位置；howmany参数为必需，要删除的项目数量，如果设置为 0，则不会删除项目；item1,...itemx为可选，向数组添加新的项目。

**2. indexOf(searchValue, fromIndex)**

`indexOf()`方法返回某个指定字符串值在数组中的位置。searchValue是查询的字符串；fromIndex是查询的开始位置，默认是0。如果查询不到，会返回-1。

**3. concat(array1,...arrayn)**

`concat()`方法用于链接两个或者多个数组。

**4. push(newElement1,..newElementN)**

`push()`方法可向数组的**末尾**添加一个或者多个元素。

**5. unshift(newElement1,...newElementN)**

`unshift()`方法可向数组的**开头**添加一个或者多个元素。

**6. pop()**

`pop()`方法用于删除并返回数组的**最后**一个元素。

**7. shift()**

`shift()`方法可以删除数组的**第一**个元素。

**8. reverse()**

`reverse()`方法用于数组的反转。

**9. sort(sortFn)**

`sort()`方法是对数组的元素进行排序。参数sortFn可选，规定排序顺序，必须是函数。

```javascript
let values = [0, 1, 5, 10, 15];
values.sort();
console.log(values); // 0, 1, 10, 15, 5

let arr = [0, 10, 5, 1, 15];
function compare(el1, el2){
    return el1 - el2;
}
arr.sort(compare);
console.log(arr); // 0, 1, 5, 10, 15

arr.sort((el1, el2) => {
    return el2 - el1;
}); 
console.log(arr); // 15, 10, 5, 1, 0
```

**10. forEach(function(currentValue, index, arr){}, thisValue)**

`forEach()`方法用于调用数组的每个元素，并将元素传递给回调函数。参数`function(currentValue, index, arr){}`是一个回调函数。thisValue可选，传递给函数的值一般用 "this" 值，如果这个参数为空， "undefined" 会传递给 "this" 值。

**11. every(function(currentValue, index, arr){}, thisValue)**

`every()`方法用于检测数组中所有元素是否符合指定条件，如果数组中检测到有一个元素不满足，则整个表达式返回`false`，且剩余的元素不再检查。如果所有的元素都满足条件，则返回`true`。

**11. some(function(currentValue,index,arr),thisValue)**

`some()`方法用于检测数组中元素是否满足指定条件。只有有一个符合就返回`true`，剩余的元素不再检查。如果所有元素都不符合条件，则返回`false`。

**12. reduce(function(total, currentValue, currentIndex, arr), initialValue)**

`reduce()`方法接收一个函数作为累加器，数组中的每个值（从左到右）开始缩减，最终为一个值。回调函数的四个参数的意义如下：total，必需，初始值, 或者计算结束后的返回值；currentValue，必需，当前元素；currentIndex,可选,当前元素的索引;arr,可选,当前元素所属的数组对象。`initialValue`，可选，传递给函数的初始值。

数组是比较重要的数据结构，在后期讲到的算法中多多少少使用到～