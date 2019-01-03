## 链表

> 链表是由一组节点组成的集合。每个节点都使用一个对象的引用指向它的后继。指向另一个节点的引用叫做**链**。

下面实现下**单向链表**

```javascript
/**
* @method Node 创建节点类
* @param { String } element 实例化的元素
*/
function Node(element){
    this.element = elememt;
    this.next = null;
}
```

```javascript
/**
* @method LList 实现链表类
*/
function LList(){
    this.head = new Node('head');
    // 查找功能
    this.find = find;
    // 插入元素功能
    this.insert = insert;
    // 移除功能
    this.remove = remove;
    // 展示功能
    this.display = display;
}
```

```javascript
/**
* @method find 实现链表的查找功能
* @param { String } item 查找的元素
* @return { Object } 返回查找到的节点
*/
function find(item){
    let currNode = this.head;
    while(currNode.element != item){
        currNode = currNode.next;
    }
    return currNode;
}
```

```javascript
/**
* @method insert 实现链表的插入元素功能
* @param { String } newElement 要插入的元素
* @param { String } item 在指定的元素后（插入的元素）
*/
function insert(newElement, item){
    let newNode = new Node(newElement);
    let current = this.find(item);
    newNode.next = current.next;
    current.next = newNode;
}
```

```javascript
/**
* @method display 展现链表
*/
function display(){
    let currNode = this.head;
    while(!(currNode.next == null)){
        console.log(currNode.next.element + '\n');
        currNode = currNode.next;
    }
}
```

```javascript
/**
* @method findPrevious 查找链表指定元素的前一个节点
* @param { String } item 指定的元素
* @return { Object } 返回查找到的之前元素的前一个节点
*/
function findPrevious(item){
    let currNode = this.head;
    while(!(currNode.next == null) && (currNode.next.element = item)){
        currNode = currNode.next;
    }
    return currNode;
}

/**
* @method remove 删除链表指定元素
* @param { String } item 指定的元素
*/
function remove(item){
    let prevNode = this.findPrevious(item);
    if(!(prevNode.next == null)){
        prevNode.next = prevNode.next.next;
    }
}
```