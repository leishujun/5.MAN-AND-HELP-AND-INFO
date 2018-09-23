# MAN-AND-HELP-AND-INFO
# __MAN AND INFO AND HELP__  
手册页存放在/usr/share/man  
几乎每个命令都有man的“页面”  
man页面分组为不同的“章节”  
统称为Linux手册  
man命令的配置文件：/etc/man.config | man_db.conf  
MANPATH /PATH/TO/SOMEWHERE: 指明man文件搜索位置  
man -M /PATH/TO/SOMEWHERE COMMAND: 到指定位置下搜索  
COMMAND命令的手册页并显示 
中文man需安装包man-pages-zh-CN  

man各个章节的主题  
1：用户命令  
2：系统调用  
3： C库调用  
4：设备文件及特殊文件  
5：配置文件格式  
6：游戏  
7：杂项  
8：管理类的命令  
9：Linux 内核API   
  
查看man手册页  
man [章节] keyword  
列出所有帮助  
man –a keyword  
搜索man手册  
man -k keyword 列出所有匹配的页面  
使用 whatis 数据库  
相当于whatis  
man –f keyword  
打印man帮助文件的路径  
man –w [章节] keyword    

搜索方式   
/搜素内容  
？搜索内特  
n  
N  

# __info__  

man常用于命令参考 ，GNU工具info适合通用文档参考  

格式是  
info 命令  
比如  
info help  
就会显示help的详细信息


## __判断命令是内部命令还是外部命令__  

谷歌搜索精确搜索的方式  
比如说要搜索docker:  
docker filetype：pdf  
这样搜索到的文章都是会以pdf的格式显示出来的

内部命令：系统开机就会自启动的命令  
外部命令：需要用户调用库才会启动的命令

type command  查看命令的类型  

如果显示的是  
 xxx  is a shell builtin  就表示这个是内部命令  
 xxx  is /bin/ 这种带路径的就表示这个是外部命令

whatis command=man -f command  这个可以才看到到哪里去找帮助，以及一些这个命令的详细概述(whatis 若是刚装机的话可能会用不了，6用makewhatis，7用mandb这两个命令来激活这个命令)

whereis command  这个命令在哪，可以去哪里找到帮助文档  


## __内部命令的正确打开姿势：__

help command  查看内部命令的各种选项参数的详细释义
man bash    查看内部命令的各种选项参数的详细释义

enable  查看/bin/bash中各种shell命令可以使用的内部命令

enable  cmd 启用内部命令

enable  -n  cmd 禁用内部命令

enable  -n  查看所有禁用的内部命令

## __外部命令的正确打开姿势：__  

man command  
command --help  
command -h 
info command

which  -a 命令    查看所有“命令”的路径
which --skip-alias 命令  
查看路径并跳过显示别名

whereis   查看路径  

# __外部命令，哈希缓存__

hash  显示缓存  
hash -p 命令的存放路径 名字   给命令起别名  
hash -d  名字    清除某个命令的缓存
hash -r 清除所有命令的缓存

查看hash帮助的的姿势  
type hash  
查看得知hash是内部命令所以我们直接输入  
help hash  
里面看到所有的hash的选项与参数，如果觉得help里面的内容不够详细，那么我们可以继续用以下操作：  
whatis hash  
查看到列出两栏来  

hash (1)             - bash built-in commands, see bash(1)  
hash (1p)            - remember or report utility locations
  
那么我们可以使用以下命令来获取hash的更多的详细信息  

man 1 hash  

进去后发现并不像help那样直接能找到hash的使用方式，所以我们再这样操作  

按下&ensp;&ensp;&ensp;&ensp;/  
输入&ensp;&ensp;&ensp;&ensp;hash  
按下&ensp;&ensp;&ensp;&ensp;enter键  

这样就找到了hash的正确使用方式  

一般whatis中找到的命令的括号中如果只是数字的话比如说hash (1)，我们是可以查看到的hash 在man的第一章节可以查看到，而hash (1p)这个选项的括号中不仅仅有数字还有字母p的话，开发人员是比较关心这个的。我们只要大致上了解有这个东西就行。当然我们也可以看看里面的一些介绍。
