## 冒泡排序

基础排序--冒泡排序是一种最容易的排序算法。

```javascript
/**
* @method bubbleSort
* @param { Array } arrNum 传入的数字数组
* @return { Array } 返回冒泡排序后的数组
*/
function bubbleSort(arrNum){
    let numElements = arrNum.length,
        temp,
        dataStore = arrNum;

    for(let outer = numElements-1; outer >= 2; --outer){
        for(let inner = 0; inner <= outer -1; ++inner){
            if(dataStore[inner] > dataStore[inner+1]){
                swap(dataStore, inner, inner+1); // 交换两个元素
            }
        }
    }

    return dataStore;
}

/**
* @method swap
* @param { Array } arr 进行交换的数组
* @param { Number } index1 数组的索引1
* @param { Number } index2 数组的索引2
*/
function swap(arr, index1, index2){
    let temp = arr[index1];
    arr[index1] = arr[index2];
    arr[index2] = temp;
}
```

