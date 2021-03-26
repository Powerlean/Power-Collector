[中文用户请单击此处](https://github.com/EdgeS5352/Power-Collector/blob/master/READMECN.md)

![](https://ae01.alicdn.com/kf/Hec54846cf57c4cbfa0bff6cae6090ff1E.jpg)

#### Power Collector is a simple packages manager
* View [demo](https://powerlean.top/poco)
* View my [blog](https://powerlean.top)
* If you want to reference my code,please access my [repository](https://github.com/EdgeS5352/EdgeS5352.github.io/blob/master/blob/poco)

## 🏁Setup
`curl -s www.powerlean.top/blob/poco.setup | bash`

### 📋Usage：poco [command] [argument] [suffix]
Command:
- help         **Get help with poco**
- fetch     **Get a specified file**
- list        **List all files which can be download**
- remove      **Delete a specified file**
- search      **Search the software description**
- console     **Edit config file**
- status      **Show detail info about setting (Chinese)**

suffix:
- -y          **Skip confirmation**
- -s          **Silent mode**

###  Structure

|  poco's OC  | Role |
|  ----  | ------------------------------ |
| [poco](https://github.com/EdgeS5352/EdgeS5352.github.io/blob/master/blob/poco)  | Power Collector's subject |
| [poco.setup](https://github.com/EdgeS5352/EdgeS5352.github.io/blob/master/blob/poco.setup) | Setup script |
| [poco.update](https://github.com/EdgeS5352/EdgeS5352.github.io/blob/master/blob/poco.update) | Update script |
| [poco.list](https://github.com/EdgeS5352/EdgeS5352.github.io/blob/master/blob/poco.list) | List of packages |
| [poco.note](https://github.com/EdgeS5352/EdgeS5352.github.io/blob/master/blob/poco.note) | Release note |
| [poco-rescue](https://github.com/EdgeS5352/EdgeS5352.github.io/blob/master/blob/poco-rescue) | Fix script|
| [poco.conf](https://github.com/EdgeS5352/EdgeS5352.github.io/blob/master/blob/poco.conf) | Config file |


### Deploy your programs library

Deploy a programs library for **Power Collector**,you just need a **website**.

**Create both directories in the project root directory `/`**

- blob/
- tree/

*Also,you can rename these directory.*
*Please drag all programs into the`blob/`.*
*[Click here](https://github.com/EdgeS5352/Power-Collector/blob/master/ENGLISH.md#files-format-under-the-tree) to know about the file's format under the`tree/`.*

**Create both files in the `blob/`**

- poco.conf
- poco.list

*Please write a executable program to replace the user's `poco.conf`*

*Please  consult [poco.list's format](https://github.com/EdgeS5352/EdgeS5352.github.io/blob/master/blob/poco.list) to learn how to write packages list.*

###  File's format under the `tree/`

You need **declare the dependencies** for your programs：

If you have a program called `XXX`,then you must create a file called `XXX.tree`.

The file have a format,such as:

`export depends="XXX XXX XXX"`

**Examples**:

Now I have a program called `poco`,it relies on `poco.conf` and `poco-rescue`，like that,I need create a file called `poco.tree`,and  write the following contents:

`export depends="poco.conf poco-rescue"`

If the program don't need any dependency,then we need do such this:

`export depends=""`

*You must creates such this file for your all programs.*

### The end.
