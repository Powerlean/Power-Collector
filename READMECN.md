[Engllish user please click here](https://github.com/EdgeS5352/Power-Collector/blob/master/README.md)

![](https://ae01.alicdn.com/kf/Hec54846cf57c4cbfa0bff6cae6090ff1E.jpg)

#### Power Collector是一个基于BASH编写的的程序包管理器
* 访问[概览页面](https://www.powerlean.top/poco-cn)
* 访问我的[博客](https://www.powerlean.top)
* 若要参考代码及原理，请移步至我的[网站资料库](https://github.com/EdgeS5352/EdgeS5352.github.io/blob/master/blob/poco)

## 🏁快速开始
`curl -s www.powerlean.top/blob/poco.setup | bash`

### 📋Usage：poco [命令] [参数] [后缀]
命令:
- help        展示帮助信息
- fetch       安装程序包
- list        列出所有可下载程序
- remove      删除指定的可执行文件
- search      查找指定程序的概述
- console     编辑配置文件
-status       显示poco的运行状态和参数

后缀:
- -y          跳过确认环节
- -s          静默模式，不产生输出

###  构成

|  组成部分   | 应用 |
|  ----  | ------------------------------ |
| [poco](https://github.com/EdgeS5352/EdgeS5352.github.io/blob/master/blob/poco)  | 主体 |
| [poco.setup](https://github.com/EdgeS5352/EdgeS5352.github.io/blob/master/blob/poco.setup) | 安装脚本，运行安装更新等操作 |
| [poco.list](https://github.com/EdgeS5352/EdgeS5352.github.io/blob/master/blob/poco.list) | 软件包列表，载入各软件包的描述 |
| [poco.note](https://github.com/EdgeS5352/EdgeS5352.github.io/blob/master/blob/poco.note) | 更新日志，发布更新内容 |
| [poco-rescue](https://github.com/EdgeS5352/EdgeS5352.github.io/blob/master/blob/poco-rescue) | 修复文件，替换损坏的文件主体|
| [poco.conf](https://github.com/EdgeS5352/EdgeS5352.github.io/blob/master/blob/poco.conf) | 控制文件，存放指向路径|
| [poco-remove](https://github.com/EdgeS5352/EdgeS5352.github.io/blob/master/blob/poco-remove) | 移除poco及其所有缓存文件|

### 部署可用下载源

得益于**Power Collector**极简的原理，部署软件源非常容易，**只需一个站点（site）**。

**你需要在网站的根目录`/`下创建两个目录:**

- blob/
- tree/

*当然，文件夹也可以设置成其他名称，但需注意将两者进行区分。*
*请将软件包及其依赖全部存放至`blob/`目录。*
*[单击此处](https://github.com/EdgeS5352/Power-Collector/blob/master/README.md#依赖声明文件的编写格式)了解`tree/`目录下的文件编写规范。*

**在`blob/`目录下创建以下两个文件：**

- poco.conf
- poco.list

*请编写一个机壳脚本将用户原先的`poco.conf`替换为你所编写的版本，请按照该文件内的批注规范填写指向地址。*
*请参考本项目中的[poco.list](https://github.com/EdgeS5352/EdgeS5352.github.io/blob/master/blob/poco.list)格式来了解如何编写软件包列表。*

### 依赖声明文件的编写格式

每个软件包都必须对应一个**依赖声明文件**，它们的命名有一个固定的格式：

假设`blob/`目录下现存放有文件`XXX`,那么它的对应依赖声明文件必须命名为`XXX.tree`。

**依赖声明文件**的内容也有固定的格式，格式如下:

`export depends="XXX XXX XXX"`

**实例**:
现有一个名为`poco`的程序，它需要依赖于`poco.conf`和`poco-rescue`才能运行，则需要在它的依赖声明文件`poco.tree`中编写以下内容:

`export depends="poco.conf poco-rescue"`

*列表中每两个依赖程序名称之间用一个空格分隔。*


假设某程序不需要任何依赖，则将变量内容留空:

`export depends=""`

### 调用poco内置的事务后函数
poco脚本内预设有4种不同的事务后函数（截至3月26日）

- pack   组合包类型
- script 脚本类型
- rename 重命名类型
- arch 判断架构类型

**pack**
表示仅将该文件作为一次性引导，以安装其他程序（安装完成后立即删除引导文件）。

**script**
表示将该文件设置为脚本（仅运行而不安装）。

**rename**
表示该文件在被下载完成后需要被重命名（需设定名称变量）。

**arch**
表示该文件已经过编译，需要配对指定架构进行安装（函数将检测设备架构并拣取对应文件）。

**route**
表示不做任何处理。

**调用：**
在每个程序包对应的依赖声明文件`XXX.tree`中编写以下内容:

`export class="函数类型"`

rename函数需要额外添加名称变量:

`export class="rename"`
`export rename="命名后的名称"`

### 以上。
