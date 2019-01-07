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