## 图【重点】

> 图由边的**集合**及顶点的**集合**组成。

**表示顶点：**

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

**表示边：**

我们将表示图的边的方法称为`临接表或者临接表数组`。这种方法将边存储为由顶点的相邻顶点列表构成的数组，并以此顶点作为索引。


**构造图**

```javascript
/**
* @method Graph 图的构造函数
* @param { Num } v 顶点的个数
*/
function Graph(v){
    this.vertices = v;
    this.edges = 0;
    this.adj = [];
    for(let i = 0; i < this.vertices; i++){
        this.adj[i] = [];
        this.adj[i].push('');
    }
    this.addEdge = addEdge;
    this.toString = toString;
}
```