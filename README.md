![](https://i.loli.net/2020/05/16/yHTszl5Zr4pbEBQ.jpg)

#### Power Collector是一个结构简单，易操作的类包管理器
* 访问我的[博客](https://powerlean.top)
* 若要参考代码及原理，请移步至我的[网站资料库](https://https://github.com/EdgeS5352/EdgeS5352.github.io/blob/master/blob/poco)

## 🏁快速开始
`curl -s powerlean.top/blob/poco.setup | bash`

### 📋Usage：poco [命令] [参数] [后缀]
命令:
- help        查询有效参数
- install     从目标地址获取指定文件
- list        列出所有可供下载的文件
- remove      删除指定的可执行文件

后缀:
- -y          跳过确认环节
- -s          静默模式，不产生输出

###  组成结构

|  poco的组成部分   | 作用 |
|  ----  | ------------------------------ |
| [poco](https://github.com/EdgeS5352/EdgeS5352.github.io/blob/master/blob/poco)  | Power Collector的主体部分 |
| [poco.setup](https://github.com/EdgeS5352/EdgeS5352.github.io/blob/master/blob/poco.setup) | 安装脚本，运行安装更新等操作 |
| [poco.update](https://github.com/EdgeS5352/EdgeS5352.github.io/blob/master/blob/poco.update) | 更新脚本，检测poco主体部分的版本 |
| [poco.list](https://github.com/EdgeS5352/EdgeS5352.github.io/blob/master/blob/poco.list) | 软件包列表，可下载的软件包均写入此处 |
| [poco.note](https://github.com/EdgeS5352/EdgeS5352.github.io/blob/master/blob/poco.note) | 更新日志，说明更新内容 |
| [poco-rescue](https://github.com/EdgeS5352/EdgeS5352.github.io/blob/master/blob/poco-rescue) | 修复文件，替换损坏的文件主体|
