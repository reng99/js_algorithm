## 集合

> 集合是由一组无序但是彼此之间又有一定相关性的成员构成的，每个成员在集合中只能出现一次。

```javascript
/**
* @method Set 字典类
*/
function Set(){
    // 数组数据结构存储数据
    this.dataStore = [];
    // 添加元素的方法
    this.add = add;
    // 移除元素的方法
    this.remove = remove;
    // 字典的长度
    this.size = size;
}
```

```javascript
/**
* @method add 添加元素
* @param { String } data 传入的字符串
* @return { Boolean } 返回是否添加成功
*/
function add(data){
    if(this.dataStore.indexOf(data) < 0){
        this.dataStore.push(data);
        return true;
    }else{
        return false;
    }
}
```

```javascript
/**
* @method remove 移除元素
* @param { String } data 传入的字符串
* @return { Boolean } 返回是否添加成功
*/
function remove(data){
    let pos = this.dataStore.indexOf(data);
    if(pos > -1){
        this.dataStore.splice(pos, 1);
        return true;
    }else{
        return false;
    }
}
```

```javascript
/**
* @method show 显示元素
*/
function show(){
    return this.dataStore;
}
```

```javascript
/**
* @method contains 辅助函数，检查一个成员是否属于该集合
* @param { String } data 传入的字符串
* @return { Boolean } 返回是否添加成功
*/
function contains(data){
    if(this.dataStore.indexOf(data) > -1){
        return true;
    }else{
        return false;
    }
}

/**
* @method union 两集合的并集
* @param { Array } set 传入的数组
* @return { Array } 返回并集的数组
*/
function union(set){
    let tempSet = new Set();
    for(let i = 0; i < this.dataStore.length; ++i){
        tempSet.add(this.dataStore[i]);
    }
    for(let i = 0; i < set.dataStore.length; ++i){
        if(!tempSet.contains(set.dataStore[i])){
            tempSet.dataStore.push(set.dataStore[i]);
        }
    }
    return tempSet;
}

/**
* @method intersect 两集合的交集
* @param { Array } set 传入的数组
* @return { Array } 返回并集的数组
*/
function intersect(set){
    let tempSet = new Set();
    for(let i = 0; i < this.dataStore.length; ++i){
        if(set.contains(this.dataStore[i])){
            tempSet.add(this.dataStore[i]);
        }
    }
    return tempSet;
}

/**
* @method size 数组的长度
*/
function size(){
    return this.dataStore.length;
}

/**
* @method subset 集合的子集
* @param { Array } set 传入的数组
* @return { Boolean } 返回是否是子集
*/
function subset(set) {
    if(this.size() > set.size()){
        return false;
    }else{
        this.dataStore.forEach((item, index)=>{
            if(!set.contains(item)){
                return false;
            }
        })
    }
    return true;
}


```

