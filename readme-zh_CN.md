# 有了 CLI，还要什么 GUI

[![加入Spectrum社群（英文）](https://withspectrum.github.io/badge/badge.svg)](https://spectrum.chat/you-dont-need/GUI)

<details>
给新手用的命令行常用工具介绍 :)
</details>
<br/>

图形用户操作界面（Graphical User Interfaces, GUI）对用户很友好，易于上手，没有命令行操作界面（Command-Line Interfaces, CLI）这么陡峭的学习曲线。

![Xerox Star 8010 工作站](./Xerox_Star_8010_workstations.jpg)

但事实上，他们通常会消耗更多的计算资源，并且在自动化处理方面不如 CLI 那么容易且强大。

作为计算机专家，我们希望工作做得又快又好。当然我们也知道各种“黑话”一样的命令行可能不那么容易发现或者记住，所以我们试着在这儿列举一些常见的 GUI 操作是如何在 CLI 实现的。

<h2> 快速跳转 </h2>

- [拷贝一个文件](#拷贝一个文件)
- [创建文件副本](#创建文件副本)
- [拷贝一个目录](#拷贝一个目录)
- [创建目录副本](#创建目录副本)
- [移动一个文件](#移动一个文件)
- [重命名文件](#重命名文件)
- [移动一个目录](#移动一个目录)
- [重命名目录](#重命名目录)
- [合并目录文件](#合并目录文件)
- [创建新文件](#创建新文件)
- [创建新目录](#创建新目录)
- [显示文件或目录大小](#显示文件或目录大小)
- [显示文件或目录其他信息](#显示文件或目录其他信息)
- [用默认程序打开文件](#用默认程序打开文件)
- [压缩整个目录](#压缩整个目录)
- [解压目录的压缩包](#解压目录的压缩包)
- [速览压缩包中文件](#速览压缩包中文件)
- [删除一个文件](#删除一个文件)
- [删除一个目录](#删除一个目录)
- [显示目录中文件](#显示目录中文件)
- [显示目录下所有文件和子目录的文件树](#显示目录下所有文件和子目录的文件树)
- [找出陈旧文件](#找出陈旧文件)
- [显示日历](#显示日历)
- [计算未来日期](#计算未来日期)
- [使用计算器](#使用计算器)
- [强制退出应用程序](#强制退出应用程序)
- [查看服务器响应](#查看服务器响应)
- [查看文件内容](#查看文件内容)
- [检索文本内容](#检索文本内容)
- [查看一张图片](#查看一张图片)
- [查看磁盘大小](#查看磁盘大小)
- [查看计算机性能](#查看计算机性能)
- [技巧小贴士](#技巧小贴士)
- [热键](#热键)
- [我记不住这些神秘指令怎么办呢？](#我记不住这些神秘指令怎么办呢)

## 拷贝一个文件

**别再用拖拽或者 `CMD`/`CTRL` + `C`, `CMD`/`CTRL` + `V` 来复制文件了！** :-1:

将 `readme.txt` 拷贝到 `documents` 目录下

```shell
$ cp readme.txt documents/
```

## 创建文件副本

**不要再用`右键`来创建副本了！** :-1:

```shell
$ cp readme.txt readme.bak.txt
```

更高级的写法：

```shell
$ cp readme{,.bak}.txt
# 注: 注意这里的 {} 起什么作用，可以试试 touch foo{1,2,3}.txt 然后看看结果如何
```

## 拷贝一个目录

**也别拖拽目录了，也不要 `CMD`/`CTRL` + `C`, `CMD`/`CTRL` + `V` 来拷贝目录了！** :-1:

把 `myMusic` 整个目录拷贝到 `myMedia` 目录下面

```shell
$ cp -a myMusic myMedia/
# 或者你也可以写成
$ cp -a myMusic/ myMedia/myMusic/
```

## 创建目录副本

**也别用`右键`来创建目录副本了** :-1:

```shell
$ cp -a myMusic/ myMedia/
# 如果 `myMedia` 文件夹不存在的话
$ cp -a myMusic myMedia/
```

## 移动一个文件

**没有什么拖拽文件，也没有 `CMD`/`CTRL` + `X`, `CMD`/`CTRL` + `V` 来剪切** :-1:

```shell
$ mv readme.txt documents/
```

**一定** 要在移动文件时在目标目录的最后加上斜杠`/`。（[不然的话](http://unix.stackexchange.com/a/50533)，简言之会被当作[这样](#重命名文件)）

## 重命名文件

**别用`右键`-`重命名`了！** :-1:

```shell
$ mv readme.txt README.md
```

## 移动一个目录

**没有了拖拽文件夹，也没有 `CMD`/`CTRL` + `X`, `CMD`/`CTRL` + `V`** :-1:

```shell
$ mv myMedia myMusic/
# 或者也可以写成
$ mv myMedia/ myMusic/myMedia
```

## 重命名目录

**也别`右键`文件夹然后`重命名`了** :-1:

```shell
$ mv myMedia/ myMusic/
```

## 合并目录文件

**别再用拖拽来合并目录了！** :-1:

```shell
$ rsync -a /images/ /images2/   # 注: 当心！！同名的文件会被覆盖掉!
```

## 创建新文件

**别再用`右键`来新建文件了！** :-1:

```shell
$ touch 'new file'    # 如果文件已经存在，会更新它的权限和修改日期
# 或者也可以用
$ > 'new file'        # 注: 如果文件已经存在，会清空里面内容
```

## 创建新目录

**也别用`右键`来新建目录了！** :-1:

```shell
$ mkdir 'untitled folder'
# 或者可以用下面这样的写法新建一连串文件夹
$ mkdir -p 'path/may/not/exist/untitled\ folder'
```

## 显示文件或目录大小

**别再用`右键`点开来看属性了！** :-1:

```shell
$ du -sh node_modules/
```

## 显示文件或目录其他信息

**真的别用`右键`了！** :-1:

```shell
$ stat -x readme.md   # macOS 系统
$ stat readme.md      # Linux 系统
```

## 用默认程序打开文件

**没有双击，没有双击，没有双击** :-1:

```shell
$ xdg-open file   # Linux 系统
$ open file       # MacOS 系统
```

## 压缩整个目录

**别再用`右键`-`压缩`了！** :-1:

```shell
$ zip -r archive_name.zip folder_to_compress
```

## 解压目录的压缩包

**也别用`右键`-`解压`了！** :-1:

```shell
$ unzip archive_name.zip
```

## 速览压缩包中文件

**我们不要`WinRAR`** :-1:

```shell
$ zipinfo archive_name.zip
# 或者也可以用
$ unzip -l archive_name.zip
```

## 删除一个文件

**别再`右键`然后永久删除文件了！** :-1:

```shell
$ rm my_useless_file
```

非常重要：`rm` 指令会把 `my_useless_file` 永久删除，和把它移到回收站后再点 `清空回收站` 一样的效果！

## 删除一个目录

**也别再`右键`然后永久删除目录了！** :-1:

```shell
$ rm -r my_useless_folder
```

## 显示目录中文件

**别打开你的`访达`或者`文件浏览器`** :-1:

```shell
$ ls my_folder        # 简简单单
$ ls -la my_folder    # -l: 以列表格式显示. -a: 显示包括隐藏文件的所有文件. -la 结合以上两个选项.
$ ls -alrth my_folder # -r: 倒序显示. -t: 按修改时间排序. -h: 以易读的格式显示大小.
```

## 显示目录下所有文件和子目录的文件树

**别打开你的`访达`或者`文件浏览器`** :-1:

```shell
$ tree                                                        # Linux 系统
$ find . -print | sed -e 's;[^/]*/;|____;g;s;____|; |;g'      # MacOS 系统
# 注: 安装 homebrew (https://brew.sh) 后能让你在 MacOS 上也能用（部分） Linux 的功能（比如 tree）. 安装方法见下
# brew install tree
```

## 找出陈旧文件

**别用你的文件浏览器！** :-1:

找出所有最近一次修改在 5 天之前的文件

```shell
$ find my_folder -mtime +5
```

## 显示日历

**别用日历小部件来看几月几号是星期几了！** :-1:

显示一个文本风格的日历

```shell
$ cal
```

显示特定月份和年份的日历

```shell
$ cal 11 2018
```

## 计算未来日期

**别用在线日期计算器来干这活了！** :-1:

查看今天的日期

```shell
$ date +%m/%d/%Y
```

查看一周后的日期

```shell
$ date -d "+7 days"    # Linux 系统
$ date -j -v+7d        # MacOS 系统
```

## 使用计算器

**真的，抛开那些计算器小部件吧** :-1:

```shell
$ bc
```

## 强制退出应用程序

**别用 `CTRL` + `ALT` + `DELETE` 再选要终止的程序那一套了！** :-1:

```shell
$ killall program_name
```

## 查看服务器响应

**而不用开浏览器！** :-1:

```shell
curl -i umair.surge.sh
# curl 指令的 -i (--include) 选项会在让它输出中包含 HTTP 的响应头.
```

## 查看文件内容

**不需要双击** :-1:

```shell
$ cat apps/settings.py
# 如果文件太大，一页显示不下的话，你可以使用一个"翻页软件" (less) 来一次查看一页内容
$ less apps/settings.py
```

## 检索文本内容

**别用 `CMD`/`CTRL` + `F` 哦** :-1:

```shell
$ grep -i "Query" file.txt
```

![grep](./grep.jpg)

说明：`grep`能在文件中检索特定内容，图中是一些常见的配套命令行参数

- `-i`：大小写敏感
- `-A`/`-B`/`-C` `<N>`：顺带显示前后文，`-A`表示后面 N 行，`-B`表示前面 N 行，`-C`表示前后各 N 行
- `-E`：使用正则表达式来匹配
- `-v`：反选（输出不匹配的行）
- `-l`：只输出能匹配到内容的**文件名**
- `-F`：不要将检索内容视为正则表达式
- `-r`：递归匹配目录下所有文件的内容
- `-o`：只输出匹配上了的部分（而不是整行）
- `-a`：也对二进制文件进行检索，而不是忽略它们！

你也可以用别的一些指令来替代`grep`，比如`ack`，`ag`和`ripgrep`（更适合检索代码文本）

## 查看一张图片

**停止你的打开文件预览的行为！** :-1:

```shell
$ imgcat image.png
# 注: 需要 iTerm2 终端程序（仅MacOS）.
```

## 查看磁盘大小

**别`右键`点磁盘图标，也别开什么磁盘工具，想都别想！** :-1:

```shell
$ df -h
```

## 查看计算机性能

**别开你的`活动监视器`和什么`任务管理器`！** :-1:

```shell
$ top
```

## 技巧小贴士

![CLI tips](./cli_tips.jpg)

给 macOS 用户准备的，但是`bash`命令行环境应该也会有别的

```shell
$ !!                            # 再一次执行上一条指令
$ sudo !!                       # 以管理员身份执行上一条指令
$ !<word>                       # 加上特定命令行前缀再执行上一条指令
$ !<word>:p                     # 显示上一条指令加上前缀，但不要执行
$ <space>command                # 执行指令，但不要存到历史记录中
$ echo "ls -l" | at midnight    # 在特定时间执行指令
$ caffeinate -u -t 3600         # 接下来一小时内阻止你的mac休眠
$ ls -lhs                       # 将目录中文件按大小排序显示
$ qlmanage -p <file>            # 从命令行调用"速览"
$ top -o vsize                  # 查看是什么拖慢了你的mac
```

## 热键

```
Ctrl + A  跳转到你当前编辑的命令行行首
Ctrl + E  跳转到你当前编辑的命令行行尾
Ctrl + L  清屏，和 clear 指令类似
Ctrl + U  清除行中光标之前的内容（在行尾时即清除整行）
Ctrl + H  和退格一样
Ctrl + R  能让你搜索之前使用过的命令行记录
Ctrl + C  强制停止当前的程序
Ctrl + D  退出当前 shell （壳层/命令行界面）
Ctrl + Z  将当下运行的程序挂起，使用 fg 来恢复运行
Ctrl + W  删除光标前的一个词
Ctrl + K  清除行中光标之后的内容
Ctrl + T  交换光标前两个字符
Esc + T   交换光标前两个词
Alt + F   将光标移至行内下一个词处
Alt + B   将光标移至行内上一个词处
Tab       自动补全文件/目录的名称
```

## 我记不住这些神秘指令怎么办呢？

善用谷歌或者 `man` 指令来查看你不熟悉的那些指令。或者你也可以尝试 [`tldr`](https://github.com/tldr-pages/tldr)，这是一个由社区提供支持的简化后的 `man` 帮助页面合集。
