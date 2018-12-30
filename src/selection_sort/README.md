## 选择排序

> 选择排序是从数组的开头开始，将第一个元素和其他元素进行比较。检查完所有元素之后，最小的元素会被放到数组的第一个位置（这里设定的场景是数字数组的小到大排序）。然后算法会从第二个位置继续，以此类推...

```javascript
/**
* @method selectionSort
* @param { Array } 传入的数据数组
* @return { Array } 排序后的数据数组
*/
function selectionSort(arrNum){
    let min,
        dataStore = arrNum;

    for(let outer = 0; outer <= dataStore.length-2; outer++){
        min = outer;
        for(let inner = outer+1; inner <= dataStore.length-1; inner++){
            if(dataStore[inner] < dataStore[min]){
                min = inner;
            }
        }
        swap(dataStore, outer, min); // 交换两个数据
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