## 字典

> 字典是一种以**键-值对**形式储存数据的数据结构，就像电话号码薄里的名字和电话号码一样。

实现的DEMO：

```javascript
/**
* @method Dictionary 字典类
*/
function Dictionary(){
    // 添加元素
    this.add = add;
    this.datastore = new Array();
    // 查找元素
    this.find = find;
    // 移除元素
    this.remove = remove;
    // 展示全部元素
    this.showAll = showAll;
}
```

```javascript
/**
* @method add 添加元素
* @param { String } key 键
* @param { String } value 值
*/
function add(key, value){
    this.datastore[key] = value;
}
```

```javascript
/**
* @method find 查找元素
* @param { String } key 键
* @return { String } 返回查找到的值
*/
function find(key){
    return this.datastore[key];
}
```

```javascript
/**
* @method remove 移除元素
* @param { String } key 键
*/
function remove(key){
    delete this.datastore[key];
}
```

```javascript
/**
* @method showAll 展示所有元素
*/
function showAll(){
    let datakeys = Array.prototype.slice.call(Object.keys(this.datastore));
    for(let key in datakeys) {
        console.log(datakeys[key] + " -> " + this.datastore[datakeys[key]]);
    }
}
```