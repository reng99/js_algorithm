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
* @param { String } data 元素数据
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

> 有待补充