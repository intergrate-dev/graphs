
# 1

## 2

### Graphviz和DOT

Graphviz 是一个由AT&T实验室启动的开源工具包，用于绘制DOT语言脚本描述的图形。类似微软的visio，但是和visio也有很大的不同，他是使用一种名为dot的语言绘图，对于绘制复杂的流程图，类图等非常好用。 这种设计使得用户更关注于逻辑关系，实现“所思即所得”。Graphviz 的自动布局功能，无需人为干预就可以做到“最小化连线交叉”。

#### dot(graphviz)语法

<https://www.jianshu.com/p/e44885a777f0>


<http://www.graphviz.org/doc/info/shapes.html>

文字：
plaintext   plain

常用图形：
box          ellipse             circle            point
diamond      parallelogram       doublecircle
rect         rectangle           square            star

特殊图形:
underline       cylinder
note            folder      component

箭头:
rarrow      larrow

##### 设置图

<https://blog.csdn.net/geecky/article/details/51912111>

图大小：
size="数字,数字";  ，如size="2,2";    单位为英寸，此语句可放在函数的任意位置。

设置整张图的label
label="显示在图上的内容";

全局边设置：
edge [边的属性设置语句]; 如 edge [color=red,style=dotted];  辖域是这句话之后构建的所有的边。

全局节点设置：
node[节点的设置语句]；如node [fontname = Verdana, color=navy, shape=record, height=.1]; 辖域是这句话之后所有的节点。

##### 方向

竖直方向的位置：
labelloc=参数值，参数值有b（bottom）和t（top）。如果不设置的话，默认为bottom。

水平方向上的位置：
labeljust=参数值，参数值有l（left）和r（right），其他任意值代表middle。如果不设置的话，默认middle。

##### 边

设置边属性：
edge [边的属性设置语句]; 如 edge [color=red,style=dotted];  辖域是这句话之后构建的所有的边。
优先级按出现顺序来决定，后出现的优先级比先出现的高，也就是说可以被新的同属性语句覆盖。

设置边方向：
rankdir=参数值；参数值有LR（从左到右），RL，BT，TB，表示节点结构是水平放置还是竖直放置。没设置的话默认为TB。
可以放在代码的任意位置。
节点的设置和边的构造不能同时进行，比如a[color=red]->b; 是不可以的

##### 节点

设置节点属性：
node[节点的设置语句]；如node [fontname = Verdana, color=navy, shape=record, height=.1]; 辖域是这句话之后所有的节点。
优先级按出现顺序来决定，后出现的优先级比先出现的高，也就是说可以被新的同属性语句覆盖。

设置节点填充：
默认不填充。节点文字内容[style=filled];，填充颜色同设置的边框颜色，没有设置边框颜色就默认用灰色填充。

##### 节点框

设置节点的框的形状：
节点文字内容[shape=框的风格名称]; 比如：a[shape=box];  不设置的话默认是椭圆。如果是 plaintext就只有文字，没有边框。

设置节点边框的大小：
节点文字内容[width=值,height=值]。例如a[width=.1,height=2.5];  单位为英寸。

设置节点边框的颜色：
节点文字内容[color=颜色名称]; 比如：a[color=red];

节点边框层数：
节点文字内容[peripheries=层数]; 比如：a[peripheries=3]; 效果就是有3条边缘线。

##### 其他

设置边的射出与射入位置：
节点 : 参数值->节点 : 参数值，
参数值有：
1、系统中的 "n", "ne","e", "se", "s", "sw", "w" 和 "nw",  
2、 自己在多语句节点里面设置的地址标签。

冒号之后的参数就表示此节点与边连接的位置。可以不设置，默认为两节点之间最近的位置，比如：如果rankdir是竖直情况的话，a->b的默认就是a:s->b:n;     默认都是中间。

设置边的权重：
节点文字内容->节点文字内容[weight=数值];   如：a->b[weight=2];  不设置的话权值默认为1。

设置边的风格：
节点文字内容->节点文字内容[style=风格名称]; 如：a->b[style=dotted];   会画出一条从a到b的有向虚线段。

设置边的颜色：
节点文字内容>节点文字内容[color=颜色名称]; 如：a->b[color=red]; 

设置边的标签：
节点文字内容->节点文字内容[label="想在边上显示的文字"]; 如：a->b[label="This is a label"]; 

设置两节点间边的方向：
节点文字内容>节点文字内容[dir = 方向名称];  如：a->b[dir=both];     a--b[dir=back];

方向名称有：4个系统方向名称：both（a<->b），none(a--b)，back(a<-b)，forward(a->b)。有向图中默认为forward，无向图中默认为none。
