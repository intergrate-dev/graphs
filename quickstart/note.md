# 题目  

## 主题  

### table

| 时间 | 地点 | 计划 |
| --- | --- | --- |
| 20200212 | company | working |
| 20200213 | home | resting |

#### flow graph

```flow
st=>start: 页面加载
e=>end: End:>http://www.google.com
op1=>operation: get_hotel_ids|past
op2=>operation: get_proxy|current
sub1=>subroutine: get_proxy|current
op3=>operation: save_comment|current
op4=>operation: set_sentiment|current
op5=>operation: set_record|current
cond1=>condition: ids_remain空?
cond2=>condition: proxy_list空?
cond3=>condition: ids_got空?
cond4=>condition: 爬取成功??
cond5=>condition: ids_remain空?
io1=>inputoutput: ids-remain
io2=>inputoutput: proxy_list
io3=>inputoutput: ids-got
st->op1(right)->io1->cond1
cond1(yes)->sub1->io2->cond2
cond2(no)->op3
cond2(yes)->sub1
cond1(no)->op3->cond4
cond4(yes)->io3->cond3
cond4(no)->io1
cond3(no)->op4
cond3(yes, right)->cond5
cond5(yes)->op5
cond5(no)->cond3
op5->e
```

```flow
start=>start: start
condition1=>condition: 全量目录是否为空？
operation1=>operation: maxNum = 20191115
operation2=>operation: 取全量目录下最大
的日期目录----M1

condition2=>condition: 增量目录是否为空？
operation3=>operation: maxNum = M1
operation4=>operation: 取全量目录下最大
的日期目录----M2

condition3=>condition: M1 > M2?
operation5=>operation: maxNum = M2

condition4=>condition: 要拉取目录的名称或者
时间是否在(maxNum, date)
时间窗口内?
operation6=>operation: 增量目录下创建前一天日期的目录；
全量目录下创建前一天日期的目录；
拉取文件到全量及增量对应的目录下

end=>end: end

start->condition1
condition1(yes)->operation1->condition4
condition1(no,bottom)->operation2->condition2

condition2(yes)->operation3->condition4
condition2(no,bottom)->operation4->condition3

condition3(yes)->operation5->condition4
condition3(no)->operation3

condition4(yes)->operation6->end
condition4(no)->end
```

#### sequence graph

```sequence
bgbiao-> bianbian: good morning
note left of bgbiao: man
bianbian -> bgbiao: eat something
note right of bianbian: woman
  
note over bgbiao: test
```

#### mermaid graph

以mermaid形式嵌入，显示出现问题，节点呈黑色块，线条不显示。
使用mmd文件，其图形效果比graphviz更美观。

#### graphviz(dot)

```dot
digraph finite_state_machine {
    rankdir=LR;
    size="8,5"

    node [shape = doublecircle]; S;
    node [shape = point ]; qi
    node [shape = circle];
    qi -> S;
    S  -> q1 [ label = "a" ];
    S  -> S  [ label = "a" ];
    q1 -> S  [ label = "a" ];
    q1 -> q2 [ label = "ddb" ];
    q2 -> q1 [ label = "b" ];
    q2 -> q2 [ label = "b" ];
}
```

```dot
graph graphname {
    a -- b [color=blue]
    b -- c [color=blue]
    b -- d [color=blue]
    c -- e [color=blue]
    c -- f [color=blue]
    d -- g [color=blue]
    d -- h [color=blue]
}
```


```dot
digraph g {
    a->b;
    b->c;
    c->a;
}
```

```dot
digraph X{
    size = "6, 100"; //宽度6
    main [shape=box];
    main -> parse [weight=4];
    parse -> execute;
    main -> init [style=dotted];
    main -> cleanup;
    execute -> { make_string; printf}
    init -> make_string;
    edge [color=red]; // 设置生效
    main -> printf [style=bold,label="100 times"];
    make_string [label="make a\n字符串"];
    node [shape=box,style=filled,color=".7 .3 1.0"];
    execute -> compare;
}
```

##### 子图

```dot
digraph g {
    //定义一个子图, subgraph定义子图
    subgraph cluster0 {
        node[style=filled, color=white];  //定义子图中的节点的样式
        style=filled; //定义子图的样式
        color=red; //定义子图的填充色
        a0->a1->a2->a3; //定义节点, 及节点之间的关系
        label="process #1"; //定义子图的标签
     }

   //又定义一个子图
   subgraph cluster1 {
      node[style=filled, color=white];
      style=filled;
      color=blue; //定义子图的填充色
      b0->b1->b2->b3; //定义节点及其关系
      label="process #2";
      labelColor=white;
   }

    //定义子图之间的关系
    start->a0;
    start->b0;
    a1->b3;
    b2->a3;
    a3->end;
    b3->end;
}
```

```dot
digraph G {
    compound=true;
    subgraph cluster0 {
        a -> b;
        a -> c;
        b -> d;
        c -> d;
    }
    subgraph cluster1 {
        e -> g;
        e -> f;
    }
    b -> f [lhead=cluster1];
    d -> e;
    c -> g [ltail=cluster0,
    lhead=cluster1];
    c -> e [ltail=cluster0];
    d -> h;
}

```

##### 箭头标记

```dot
digraph g {
  //edge[style=dashed]; //定义边的样式, 虚线
  node[peripheries=2, style=filled, color="#eecc80"];
  a->b [color=red, style=dashed]; //定义边的颜色, 红色 (b和方括号之间必须有空格)
  b->c; //箭头, 三角形; 箭尾, 菱形
  b->d [arrowhead=box]; //箭头, 长方形
  b->e [dir=none]; //没有箭头
  d->f [dir=both]; //双向箭头
  f->h [label=go]; //定义edge的标签
  f->k [arrowhead=diamond]; //更改箭头形状 (更多箭头形状请参考官方文档: http://www.graphviz.org/content/arrow-shapes)
  k->y [headlabel="哈哈", taillabel="洗洗"];
}
```

参考：
<https://www.jianshu.com/p/e44885a777f0>
