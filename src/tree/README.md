## 树

> 树由一组以边连接的节点组成。

### 二叉树

> 二叉树是一种特殊的树，它的子节点个数不超过两个。

### 二叉查找树【重点】

> 二叉查找树是一种特殊的二叉树，相对较小的值保存在左节点中，相对较大的值保存在右节点中。

```javascript
/**
* @method Node 节点类
* @param { Num } data 元素数据
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

```javascript
/**
* @method BST 二叉查找树类
*/
function BST(){
    this.root = null;
    this.insert = insert;
}

/**
* @methods insert 插入数据
* @param { Num } data 元素数据
*/
function insert(data) {
    let n = new Node(data, null, null);
    if(this.root == null){
        this.root = n;
    }else{
        let current = this.root;
        let parent;
        while(true){
            parent = current;
            if(data < current.data){
                current = current.left;
                if(current == null){
                    parent.left = n;
                    break;
                }
            }else{
                current = current.right;
                if(current == null){
                    parent.right = n;
                    break;
                }
            }
        }
    }
}
```

二叉查找树的遍历，分为下面的三种遍历：中序、先序和后序遍历。

```javascript
/**
* @methods inOrder 中序遍历
* @param { Object } node 节点数据
*/
function inOrder(node){
    if(!(node ==  null)){
        inOrder(node.left);
        console.log(node.show()+' ');
        inOrder(node.right);
    }
}
```

```javascript
/**
* @methods preOrder 先序遍历
* @param { Object } node 节点数据
*/
function preOrder(node){
    if(!(node ==  null)){
        console.log(node.show()+' ');
        inOrder(node.left);
        inOrder(node.right);
    }
}
```

```javascript
/**
* @methods postOrder 后序遍历
* @param { Object } node 节点数据
*/
function postOrder(node){
    if(!(node ==  null)){
        inOrder(node.left);
        inOrder(node.right);
        console.log(node.show()+' ');
    }
}
```

查找最小值和最大值

```javascript
/**
* @methods getMin 获取最小
* @return { Num } 返回最小的数值
*/
function getMin(){
    let current = this.root;
    while(!(current.left == null)){
        current = current.left;
    }
    return current.data;
}

/**
* @methods getMax 获取最大
* @return { Num } 返回最大的数值
*/
function getMax(){
    let current = this.root;
    while(!(current.right == null)){
        current = current.right;
    }
    return current.data;
}
```

查找指定的节点

```javascript
/**
* @methods find 查找
* @param { Num } data 指定查找的数字
* @return { Object } 返回最大的对象
*/
function find(data){
    let current = this.root;
    while(current != null){
        if(current.data == data){
            return current;
        }else if(data < current.data){
            current = current.left;
        }else{
            current = current.right;
        }
    }
    return null;
}
```

删除节点【重点难点】⚠️

```javascript
/**
* @methods remove 删除函数
* @param { Num } data 指定查找的数字
*/
function remove(data){
    root = removeNode(this.root, data);
}

/**
* @methods removeNode 移除节点函数
* @param { Object } node 根节点
* @param { Num } data 移除的数据
* @return { Object } 删除节点的下一个节点
*/
function removeNode(node, data){
    if(node == null){
        return null;
    }
    if(data == node.data){
        // 没有子节点的节点
        if(node.left == null && node.right == null){
            return null
        }
        // 没有左子节点的节点
        if(node.left == null){
            return node.right;
        }
        // 没有右子节点的节点
        if(node.right == null){
            return node.left;
        }
        // 有两个子节点的节点
        let tempNode = getSmallest(node.right);
        node.data = tempNode.data; // 右子树的最小值替换移除的值
        node.right = removeNode(node.right, tempNode.data); // 删除右子树最小节点的树
        return node;
    }else if(data < node.data){
        node.left = removeNode(node.left, data);
        return node;
    }else{
        node.right = removeNode(node.right, data);
        return node;
    }
}

```