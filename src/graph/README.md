## 图【重点】

> 图由边的**集合**及顶点的**集合**组成。

表示顶点：

```javascript
/**
* @method Vertex 顶点类
* @param { String } label 标识顶点
* @param { Boolean } wasVisited 是否访问过
*/
function Vertex(label, wasVisited){
    this.label = label;
    this.wasVisited = wasVisited;
}
```