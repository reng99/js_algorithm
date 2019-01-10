## 散列

> 散列是一种常用的数据存储技术，散列后的数据可以快速地插入或取出。散列使用的数据结构叫做**散列表**

```javascript
/**
* @method HashTable 哈希表类
*/
function HashTable() {
    this.table = new Array(137);
    this.simpleHash = simpleHash;
    this.showDistro = showDistro;
    this.put = put;
    this.get = get;
}
```

简单选择一个散列函数：

```javascript
/**
* 使用的是字符串的ASSII码值相加对table长度取余
* @method simpleHash 哈希表类
* @param { String } data 传入的字符串
* @return { Number } 返回取余的数字
*/
function simpleHash(data) {
    let total = 0;
    for(let i = 0; i < data.length; i++){
        total += data.charCodeAt(i);
    }
    return total % this.table.length;
}
```

```javascript
/**
* @method put 添加元素
* @param { String } data 传入的字符串
*/
function put(data) {
    let pos = this.simpleHash(data);
    this.table[pos] = data;
}
```

```javascript
/**
* @method showDistro 展示散列表中的数据
*/
function showDistro() {
    let n = 0;
    for(let i = 0; i < this.table.length; i++){
        if(this.table[i] != undefined) {
            console.log(i + " : " + this.table[i]);
        }
    }
}
```

### 碰撞处理

当散列函数对于多个输入产生相同的输出时，就产生了碰撞。处理碰撞有但不止下面两种：

**开链法**

开链接的方法是集合了链表，在寻找的插入位置点上创建一个链表，如果有重复点的数据就放在链表的后面。

**线性探测法**

线性上的查找是如果插入点上是有点入位了，那就遍历下一个点，然后再入位。

> 详细的内容可以搜索下
