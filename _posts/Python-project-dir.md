

## python 项目文件目录常见的安排

Python 项目的目录结构可能会因项目的性质和大小而异，但以下是一个常见的约定成俗的目录结构：

```
project_name/               # 项目根目录
|-- .gitignore              # Git 忽略文件
|-- README.md               # 项目说明文件
|-- requirements.txt        # 项目依赖列表
|-- setup.py                # 安装、部署和分发的脚本
|-- project_name/           # 项目主要的 Python 模块
|   |-- __init__.py         # 初始化模块
|   |-- module1.py          # 一个模块文件
|   |-- module2.py          # 另一个模块文件
|-- tests/                  # 测试目录
|   |-- __init__.py         # 初始化测试模块
|   |-- test_module1.py     # 模块1的测试文件
|   |-- test_module2.py     # 模块2的测试文件
|-- docs/                   # 文档目录
|   |-- index.md            # 文档首页
|   |-- ...
|-- scripts/                # 脚本目录，用于存放一些运行脚本
|-- data/                   # 数据目录，用于存放数据文件
|-- config/                 # 配置文件目录
```

1. **project_name/**: 项目的根目录，通常以项目名称命名。
2. **.gitignore**: 列出 Git 应该忽略的文件和目录。
3. **README.md**: 项目的简介和使用说明。
4. **requirements.txt**: 列出项目的所有依赖。
5. **setup.py**: 用于项目的打包和分发。
6. **project_name/**: 存放项目的主要代码。
7. **tests/**: 存放所有的测试代码。
8. **docs/**: 存放项目的文档。
9. **scripts/**: 存放一些有用的脚本，例如数据库迁移脚本。
10. **data/**: 存放数据文件，如 CSV、SQLite 等。
11. **config/**: 存放配置文件。



---

---

## **第一种：**

```
工程
 - bin (程序入口)
　　- conf (配置文件setting)
　　- db (数据库)
　　- lib (公共类库，基类之类的)
　　- log (日志目录)
　　- src (逻辑目录
```





## **第二种：**

```
项目名
|-- bin
| |-- 启动脚本.py
|
|-- 项目名
| |-- tests
| | |-- __init__.py
| | |-- test_main.py
| |
| |-- __init__.py
| |-- main.py
|
|— conf
|— logs
|-- docs
| |-- conf.py
| |-- abc.rst
|
|-- setup.py
|-- requirements.txt
|-- README
```



## **第三种：**

## Python通用目录结构

```
**ProjectName**
│ readme 项目说明文档
│ requirements.txt 存放依赖的外部Python包列表
│ setup.py 安装、部署、打包的脚本
├─ bin 存放脚本，执行文件等
│ └─ projectname
├─ docs 文档和配置
│ └─ abc.rst
│ └─ conf.py 配置文件
└─ projectname 工程源码（包括源码、测试代码等）
│ main.py 程序入口
│ **init**.py
└─ tests 测试代码
└─ test_main.py
└─ init.py
```





