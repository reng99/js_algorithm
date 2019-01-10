## 树

> 树由一组以边连接的节点组成。

### 二叉树

> 二叉树是一种特殊的树，它的子节点个数不超过两个。

### 二叉查找树【重点】

> 二叉查找树是一种特殊的二叉树，相对较小的值保存在左节点中，相对较大的值保存在右节点中。

```javascript
/**
* @method Node 节点类
* @param { String } data 元素数据
* @param { Object } left 二叉树左节点链接
* @param { Object } right 二叉树右节点链接
*/
function Node(data, left, right){
    this.data = data;
    this.left = left;
    this.right = right;
    this.show = show;
}

/**
* @method show 展示节点功能
*/
function show(){
    return this.data;
}
```