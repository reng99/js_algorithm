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

**5. pop()**

`pop()`方法用于删除并返回数组的最后一个元素。

**6. reverse()**

`reverse()`方法用于数组的反转。

**7. sort(sortFn)**

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