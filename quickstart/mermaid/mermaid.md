# 1

## 2

### mermaid live editor

<https://mermaid-js.github.io/mermaid-live-editor>

### mermaid语法

<https://blog.csdn.net/fenghuizhidao/article/details/79440583>

<https://cloud.tencent.com/developer/article/1334691>

<https://blog.csdn.net/swinfans/article/details/89393853>

#### 图

```text
graph LR;
    A[aa bb]-->B(wo);
    A-->C((我是C));
    B-->D>我是D];
    C-->D;
    D-->E{我是E};
    C-->E;
    2-->E;
    _-->E;
```

1. 第一行的graph LR中graph指定是一个图，第二个LR指定图的方向，所有的方向关键词为:
TB BT RL LR

2. A,B,C等都是节点的标识（标识中不能使用空格），
节点默认只显示标识,但也可以通过如下方法控制其显示：

```text
A[aa bb] 显示字符串aa bb的方框
B(wo) 显示字符串wo的圆角框
C((我是C)) 显示我是C字符串的圆圈
D>我是D] 显示我是D的半方框
E{我是E} 显示我是E的正方形框
```

连线可以选择如下形式

```text
A-->B 箭头
A--B 无箭头线
A--hh dd--B或者A--|hh dd|B 线之间可以添加注释
A-.->B 虚线箭头
A-. hh .->B 添加了注释的虚线箭头
A==>B 加粗的箭头
A== hh ==>B 加注释加粗的箭头
```

#### 子图

可以使用subgraph id定义

```text
graph TB
    subgraph one
    a1-->a2
    end
    subgraph two
    b1-->b2
    end
    subgraph three
    c1-->c2
    end
    c1-->a2
```

节点添加点击行为
click nodeId callback, callback是javascript回调函数.

#### 节点样式

### 时序图

```text
sequenceDiagram
    participant Alice
    participant Bob
    Alice->John: Hello John, how are you?
    loop Healthcheck
        John->John: Fight against hypochondria
    end
    Note right of John: Rational thoughts <br/>prevail...
    John-->Alice: Great!
    John->Bob: How about you?
    Bob-->>John: Jolly good!
```

1.声明
时序图使用sequenceDiagram关键词声明
参与者使用participant声明
消息声明是使用[参与者][发送方式][参与者]:消息内容形式声明
发送方式有如下几种:

```text
    -> 无箭头的线
    --> 无箭头的虚线
    ->> 有箭头的实线
    -->> 有箭头虚线
    -x 有十字叉的实线
    --x 有十字叉的虚线
```

可以通过ote right of [参与者]: 信息的方式添加备注(多行信息请使用'br'节点)

2.添加循环
loop Loop text
... statements ...
end

3.添加判断
有选择的:

```text
    alt Describing text
    ... statements ...
    else
    ... statements ...
    end
```

确定的:

```text
    opt Describing text
    ... statements ...
    end
```

例子

```text
    sequenceDiagram
        Alice->>Bob: Hello Bob, how are you?
        alt is sick
            Bob->>Alice: Not so good :(
        else is well
            Bob->>Alice: Feeling fresh like a daisy
        end
        opt Extra response
            Bob->>Alice: Thanks for asking
        end
```

#### gantt

```text

gantt
    dateFormat  YYYY-MM-DD
    title Adding GANTT diagram functionality to mermaid

    section A section
    Completed task            :done,    des1, 2014-01-06,2014-01-08
    Active task               :active,  des2, 2014-01-09, 3d
    Future task               :         des3, after des2, 5d
    Future task2               :         des4, after des3, 5d

    section Critical tasks
    Completed task in the critical line :crit, done, 2014-01-06,24h
    Implement parser and jison          :crit, done, after des1, 2d
    Create tests for parser             :crit, active, 3d
    Future task in critical line        :crit, 5d
    Create tests for renderer           :2d
    Add to mermaid                      :1d

    section Documentation
    Describe gantt syntax               :active, a1, after des1, 3d
    Add gantt diagram to demo page      :after a1  , 20h
    Add another diagram to demo page    :doc1, after a1  , 48h

    section Last section
    Describe gantt syntax               :after doc1, 3d
    Add gantt diagram to demo page      : 20h
    Add another diagram to demo page    : 48h
```

使用关键词gantt声明甘特图
使用关键词title声明标题
使用关键词section声明板块
板块后是任务的名称，任务类型，开始时间，持续时间等

时间参数
| 参数 | 示例 | 含义
| --- | --- | --- |
| YYYY | 2014 | 4 digit year
| YY | 14 | 2 digit year
| Q | 1..4 | Quarter of year. Sets month to first month in quarter.
| M MM | 1..12 | Month number
| MMM MMMM | January..Dec | Month name in locale set by moment.locale()
| D DD| 1..31| Day of month
| Do | 1st..31st | Day of month with ordinal.
| DDD DDDD | 1..365 | Day of year
| H HH | 0..23 | 24 hour time
| h hh | 1..12 12 | hour time used with a A.
| m mm | 0..59 | Minutes
| s ss | 0..59 | Seconds

#### 脑图

<http://naotu.baidu.com>
<https://www.processon.com/>
<http://www.plantuml.com/plantuml/>
<https://mermaidjs.github.io/mermaid-live-editor/>
<https://online.visual-paradigm.com>
<https://coggle.it>

MindMaster，这是一款专业的思维导图软件，可以免费用，支持Windows、Mac和Linux，绘图功能强大，做出的思维导图效果好，也很容易上手，免费版本的功能就完全可以满足大多数人的需求。或者使用亿图图示（EdrawMax），它是一款综合类型的绘图软件，可以用来替代Visio，可以同时绘制思维导图、流程图、组织结构图、信息图、甘特图、BPMN、UML图、UI界面原型设计、iOS界面原型设计等等。

##### demo quickshot

1.vscode:
快速修复： Alt + F8 ---- Ctrl + . (修复键)

#### 数学公式
