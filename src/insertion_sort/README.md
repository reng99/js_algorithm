## 插入排序

> 简单来说，插入排序就是**未排序的元素**对已经排序好的序列数据进行合适位置的插入。

```javascript
/**
* @method insertionSort
* @param { Array } arrNum 传入的数字数组
* @return { Array } 返回冒泡排序后的数组
*/
function insertionSort(arrNum){
    let temp,
        inner,
        dataStore = arrNum;

    for(let outer = 1; outer <= dataStore.length-1; outer++){
        temp = dataStore[outer];
        inner = outer;
        while(inner>0 && dataStore[inner-1]>=temp){
            dataStore[inner] = dataStore[inner-1];
            inner--;
        }
        dataStore[inner] = temp;
    }

    return dataStore;
}
```