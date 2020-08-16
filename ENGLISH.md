![](https://powerlean.gitee.io/images/QQ%E5%9B%BE%E7%89%8720200816120219.jpg)

#### Power Collector is a plain package manager 
* View my [blog](https://powerlean.top)
* If you want to reference my code,please access my [repository](https://github.com/EdgeS5352/EdgeS5352.github.io/blob/master/blob/poco)

## 🏁Setup
`curl -s powerlean.top/blob/poco.setup | bash`

### 📋Usage：poco [command] [argument] [suffix]
Command:
- help         **Get help with poco**
- install     **Get a specified file**
- list        **List all files which can be download**
- remove      **Delete a specified file**
- search      **Search the software description**

suffix:
- -y          Skip confirmation
- -s          Silent mode

###  Structure

|  poco's OC  | Role |
|  ----  | ------------------------------ |
| [poco](https://github.com/EdgeS5352/EdgeS5352.github.io/blob/master/blob/poco)  | Power Collector's subject |
| [poco.setup](https://github.com/EdgeS5352/EdgeS5352.github.io/blob/master/blob/poco.setup) | Setup script |
| [poco.update](https://github.com/EdgeS5352/EdgeS5352.github.io/blob/master/blob/poco.update) | Update script |
| [poco.list](https://github.com/EdgeS5352/EdgeS5352.github.io/blob/master/blob/poco.list) | List of package |
| [poco.note](https://github.com/EdgeS5352/EdgeS5352.github.io/blob/master/blob/poco.note) | Release Note |
| [poco-rescue](https://github.com/EdgeS5352/EdgeS5352.github.io/blob/master/blob/poco-rescue) | Fix script|
| [poco.conf](https://github.com/EdgeS5352/EdgeS5352.github.io/blob/master/blob/poco.conf) | Config file |


### 部署可用下载源

**Power Collector**原理简单，部署下载源也非常容易，只需要一个有效网站便可部署。

**你需要在网站的根目录`/`下创建两个目录:**

- blob/
- tree/

*当然，文件夹也可以设置成其他名称，但需注意将两者进行区分。*
*请将软件包及其依赖全部存放至`blob/`目录。*
*[单击此处](https://github.com/EdgeS5352/Power-Collector/blob/master/README.md#依赖声明文件的编写格式)了解`tree/`目录下的文件编写规范。*

**在`blob/`目录下创建以下两个文件：**

- poco.conf
- poco.list

*请自行编写可执行文件将用户原先的`poco.conf`替换为你所编写的版本，请按照该文件内的批注规范填写指向地址。*
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

*程序不需要依赖的情况下仍然须填写依赖声明文件，否则`poco`将会被引导到错误的路径。*


**现在，可以开始部署你的下载源了！**

### 以上。
