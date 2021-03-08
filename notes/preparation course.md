# markdown

## 标题

```markdown
# 一级标题
## 二级标题
### 三级标题
……
###### 六级标题
```

## 段落

### 字体

```markdown
*斜体文本*
_斜体文本_
**粗体文本**
__粗体文本__
***粗斜体文本***
___粗斜体文本___
```

### 分割线

```markdown
***
* * *
*****
- - -
----------	
```

### 删除线

```markdown
~~BAIDU.COM~~
```

### 下划线

```markdown
<u>带下划线文本</u>
```

### 脚注

```markdown
创建脚注格式类似这样 [^RUNOOB]。

[^RUNOOB]: 菜鸟教程 -- 学的不仅是技术，更是梦想！！！
```

### 列表

#### 无序列表

```markdown
* 第一项
* 第二项
* 第三项

+ 第一项
+ 第二项
+ 第三项


- 第一项
- 第二项
- 第三项
```

#### 有序列表

```markdown
1. 第一项
2. 第二项
3. 第三项
```

### 代码

~~~markdown
`printf()` 函数
```javascript
$(document).ready(function () {
    alert('RUNOOB');
});
```
~~~

### 区块

```markdown
> 区块引用
> 菜鸟教程
> 学的不仅是技术更是梦想
```

### 链接

```markdown
[链接名称](链接地址)

或者

<链接地址>
```

### 图片

```markdown
![alt 属性文本](图片地址)

![alt 属性文本](图片地址 "可选标题")
```

### 表格

```markdown
|  表头   | 表头  |
|  ----  | ----  |
| 单元格  | 单元格 |
| 单元格  | 单元格 |
```



---

# 命令行

|  命令   |                             功能                             |
| :-----: | :----------------------------------------------------------: |
|   man   |                     查看命令说明，q退出                      |
|   pwd   |                       显示当前完整路径                       |
|   cd    |                       指定要进入的目录                       |
|  mkdir  |                          创建文件夹                          |
|  rmdir  |                         删除空文件夹                         |
|   ls    | 列出当前目录的内容 -a 列出所有文件包括隐藏文件 -l 列出文件的具体信息 |
|  touch  | 若文件不存在，则创建一个新的文件；若文件存在，则更新文件修改时间 |
|   cat   |                   显示或把多个文件连接起来                   |
|   rm    |               -f 强制删除 -r递归删除目录及内容               |
|   cp    |                             拷贝                             |
|   mv    |                     改名或移入另一个目录                     |
|  open   |                     使用默认程序打开文件                     |
|   vim   |                使用vim文件编辑器进行文件编辑                 |
|  chmod  |                         修改文件权限                         |
|   cal   |                             日历                             |
|  date   |                             时间                             |
| history |                      历史记录 grep 搜索                      |
|  clear  |                             清屏                             |



---

# git

## 原理

<img src="/Users/edz/Library/Application Support/typora-user-images/image-20210303160810029.png" alt="image-20210303160810029" style="zoom: 25%;" />

## 命令

|           命令           |           功能           |
| :----------------------: | :----------------------: |
|         git init         |          初始化          |
|        git add *         |       增加到缓冲区       |
|   git commit -m '***'    | 提交缓存区修改到本地仓库 |
|        git status        |      查看git库状态       |
|    git diff filename     |       比较文件差异       |
|         git log          |         查看日志         |
|        git reset         |         版本回退         |
|         git push         |    本地仓库推送到远程    |
|        git reflog        |     查看仓库操作历史     |
|        git branch        |       查看分支情况       |
|       git checkout       |         切换分支         |
|        git merge         |       合并某个分支       |
|     git branch -d xx     |         删除分支         |
| git remote add origin x  |        增加远端库        |
| git remote remove origin |        删除远端库        |
|         git pull         |       从远端库更新       |

## 本地库链接远程库

1. 从已有的远程库克隆

   ```shell
   git clone git@github.com:Galaxy-z/Banyuan.git
   ```

2. 从已有的本地库上传

   ```shell
   git branch -M main
   git remote add origin git@github.com:Galaxy-z/Banyuan.git
   git push -u origin main
   ```

### SSH

> # 版本操作&远程库
>
> 
>
> ### `github` 的使用
>
> 1. 创建账号(github网站操作)
>
>    <https://github.com/join>
>
> 2. SSH（22端口）是Secure Shell的简写，在进行数据传输之前，SSH先对联机数据包通过加密技术进行加密处理，加密后在进行数据传输。确保了传递的数据安全。
>
> 
>
>    使用密码登录，每次都必须输入密码，非常麻烦。SSH提供了公钥登录，可以省去输入密码的步骤。
>
>    所谓"公钥登录"，原理很简单，就是用户将自己的公钥储存在远程主机上。登录的时候，远程主机会向用户发送一段随机字符串，用户用自己的私钥加密后，再发回来。远程主机用事先储存的公钥进行解密，如果成功，就证明用户是可信的，直接允许登录shell，不再要求密码。
>
> 
>
> 3. 配置 `ssh-key` （github网站操作)
>
>    配置 `ssh-key` 的目的是为了使用 `ssh` 方式和 `github` 服务器建立连接，这样就不用输入用户名和密码。
>
>    这个步骤的思路是： a. 配置本机的 `ssh-key` ； b. 将本机的 `ssh-key` 的公钥配置在 `github` 上。下面是具体操作：
>
>    1. 删除别人的 `ssh-key`
>
>       > **注意**
>       >
>       > 如果你明白 `ssh-key` 是什么，而且确认这台电脑现在的 `ssh-key` 是你自己生成的，请不做这一步操作。
>
> 
>
>       ```shell
>       rm -f ~/.ssh/id_rsa*
>       ```
>
>    2. 打开终端，输入这条命令：
>
>       ```shell
>       cd ~/.ssh
>       ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
>       ```
>
>       > **注意**
>       >
>       > -   命令里面双引号的内容修改成你自己的邮箱
>       > -   该命令会有提示，一路回车就可以了
>
>    3. 到这里，你本地的 `ssh-key` 就创建好了，需要将它放到 `github` 上
>
>       终端里通过 `cat` 命令显示 ssh 公钥的内容：
>
>           cat ~/.ssh/id_rsa.pub
>
>       将下图中框内的内容都复制出来：
>
>       ![img](http://by-camp.oss-cn-shanghai.aliyuncs.com/prep/preparatory-course/img/ssh-4.png)
>
>    4. 使用注册申请好的账号和密码登陆你的 `github`
>
>    5. 选择你的头像右边的下拉框（在网页的右上方）
>
>       ![img](http://by-camp.oss-cn-shanghai.aliyuncs.com/prep/preparatory-course/img/ssh-1.png)
>
>    6. 选择如下的 `SSH and GPG keys`
>
>       ![img](http://by-camp.oss-cn-shanghai.aliyuncs.com/prep/preparatory-course/img/ssh-2.png)
>
>    7. 选中右上角的 `New SSH Key`
>
>       ![img](http://by-camp.oss-cn-shanghai.aliyuncs.com/prep/preparatory-course/img/ssh-3.png)
>
>    8. 将第3)步你复制的内容粘贴进去，再补充一个标题：
>
>       ![img](http://by-camp.oss-cn-shanghai.aliyuncs.com/prep/preparatory-course/img/ssh-5.png)
>
>    9. 最后一步，验证你是否完成了配置
>
>           ssh -T git@github.com
>
>       如果看到类似下面的 `successfully` 什么的，而且把你github的账号打印出来，则表示你成功了
>
>           linc@pop-os:~/agenda$ ssh -T git@github.com
>           Hi linc5403! You've successfully authenticated, but GitHub does not provide shell access.
>
> 4. 创建项目（github网站操作）
>
>    1. 来到github的首页，并登陆，选择左侧 `Repositories` 右边的那个 `New`:
>
>       ![img](http://by-camp.oss-cn-shanghai.aliyuncs.com/prep/preparatory-course/img/create-1.png)
>
>    2. 在创建项目的页面填好 `Repository Name` ，点击 `Create repository` 按钮，项目就创建好了。
>
>       ![img](http://by-camp.oss-cn-shanghai.aliyuncs.com/prep/preparatory-course/img/create-2.png)
>
>    3. 在上一步已经在 `github` 服务器上创建好了远程项目，接下来需要将它同步到你的本地。
>
>       你们需要重点看下面这张图：
>
>       ![img](http://by-camp.oss-cn-shanghai.aliyuncs.com/prep/preparatory-course/img/create-3.png)
>
> 5. 项目管理(本机操作)
>
>    项目管理的流程如下：
>
>    ![img](http://by-camp.oss-cn-shanghai.aliyuncs.com/prep/preparatory-course/img/git_flow.svg)
>
>    1. `git clone`
>
>       `git clone` 命令会在当前目录下下载远端的项目,例如：
>
>       - 先找到 `git` 仓库的地址，创建项目的最后一步：
>
>         ![img](http://by-camp.oss-cn-shanghai.aliyuncs.com/prep/preparatory-course/img/clone-1.png)
>
>       - 使用 `git clone` 将它下载下来：
>
>             git clone git@github.com:linc5403/for_git_demo.git
>
>         会将远端 `for_git_demo.git` 仓库下载下来，在当前目录下新创建目录名为 `for_git_demo` 的目录:
>
>         ![img](http://by-camp.oss-cn-shanghai.aliyuncs.com/prep/preparatory-course/img/clone-2.png)
>
>         进入 `for_git_demo` 目录后，可以看到其中有 `.git` 的隐藏文件夹；说明 `git` 仓库已经建立好了。
>
>    2. `git add`
>
>       当你对本地文件作了修改后，应当使用 `git add` 命令将你的变更告知git，此时可以缓存你的变更。
>
>       让我们在 `for_git_demo` 目录中新建一个README.md文件，并将它添加到git中:
>
>           linc@pop-os:~/for_git_demo$ echo "#this is my first git repo" >> README.md
>           linc@pop-os:~/for_git_demo$ git status
>           On branch master
>             
>           No commits yet
>             
>           Untracked files:
>             (use "git add <file>..." to include in what will be committed)
>             
>           	README.md
>             
>           nothing added to commit but untracked files present (use "git add" to track)
>           linc@pop-os:~/for_git_demo$ git add README.md
>
>    3. `git commit`
>
>       当你的变更可以固定下来后，应当使用 `git commit` 命令将变更固化下来，同时需要描述此次变更的内容，方便今后快速查找。
>
>       > **重要**
>       >
>       > 当你还不会使用命令行编辑器的时候，最好使用 `git commit -m “你想说的话"` 这种方式来进行提交
>
>           linc@pop-os:~/for_git_demo$ git commit -m "init repo"
>           [master (root-commit) 2c902a3] init repo
>            1 file changed, 1 insertion(+)
>            create mode 100644 README.md
>
>    4. `git push`
>
>       将你的本地项目同步到服务器，就不怕工作丢失了。
>
>           linc@pop-os:~/for_git_demo$ git push
>           Enumerating objects: 3, done.
>           Counting objects: 100% (3/3), done.
>           Writing objects: 100% (3/3), 234 bytes | 234.00 KiB/s, done.
>           Total 3 (delta 0), reused 0 (delta 0)
>           To github.com:linc5403/for_git_demo.git
>            * [new branch]      master -> master
>
> <a id="org9a89223"></a>
>
> ### 注意事项
>
> 1. 确认你的 `home` 目录下没有 `.git` 文件夹:
>
>    在终端上运行这两条命令：
>
>        cd ~
>        ls -la | grep "\.git"
>
>    如果有类似下面的回显：
>
>        drwxr-xr-x  8 linc linc  4096 Mar 13 08:29 .git
>
>    说明你的 `home` 目录被上一个同学放到了 `git` 中进行管理，请删除这个文件夹：
>
>        rm -rf ~/.git
>
> 2. 修改自己提交git的用户名和邮箱
>
>        git config --list
>
>    此时会有类似这样的显示：
>
>        user.name=lin chuan
>        user.email=linch1982@gmail.com
>        core.quotepath=false
>
>    如果出现的username和email不是你想要的，请使用如下命令进行修改:
>
>        git config --global user.name "你的名字,最好用英文字母"
>        git config --global user.email "你的邮箱地址"
>
>    > **注意** 上面两条 `config` 命令中的双引号不要省略
>
> 3. 如果你的git命令回显中出现中文的乱码
>
>    使用下面这条命令进行修正：
>
>        git config --global core.quotepath false
>
> 4. 你可以随时使用 `git status` 命令查看git的状态
>
> 5. 使用 `.gitignore` 来管理哪些文件/文件夹进入 `git`
>
>    -   列出不关心的文件类型或文件名
>    -   列出需要关心的内容(`!`)
>    -   文件夹(`/`)
>
>    示例:  
>
>        # Blacklist everything
>        *
>        # Whitelist all directories
>        !*/
>        # Whitelist the file you're interested in.
>        !*.c
>        !*.h
>        !Makefile
>        !*.dat
>        !.gitignore



****

 #  计算机导论

## 图灵模型与冯·诺依曼模型

图灵模型：在计算机的基础上，添加一个**程序**元素

程序：用来告诉计算机对数据进行处理的指令集合

<img src="/Users/edz/Documents/2131-basic/images/image-20210304173035343.png" alt="image-20210304173035343" style="zoom: 50%;" />

冯诺依曼模型：

4个子系统：

1. 存储器

   用来存储数据和程序

2. 算数逻辑单元ALU

   用来进行算数和逻辑运算

3. 控制单元

   对另外的三个子系统进行控制操作

4. 输入/输出

   负责与外部设备进行信息包括数据和程序的交换

<img src="/Users/edz/Documents/2131-basic/images/image-20210304174142825.png" alt="image-20210304174142825" style="zoom: 50%;" />

## 数据

8bit = 1byte，byte是计算机处理数据的最小单位

1KB = 1024Byte
1MB = 1024KB
1GB = 1024MB
1TB = 1024GB

## 数制

| 十进制 | 二进制 | 八进制 | 十六进制 |
| ------ | ------ | ------ | -------- |
| 0      | 0000   | 0      | 0        |
| 1      | 0001   | 1      | 1        |
| 2      | 0010   | 2      | 2        |
| 3      | 0011   | 3      | 3        |
| 4      | 0100   | 4      | 4        |
| 5      | 0101   | 5      | 5        |
| 6      | 0110   | 6      | 6        |
| 7      | 0111   | 7      | 7        |
| 8      | 1000   | 10     | 8        |
| 9      | 1001   | 11     | 9        |
| 10     | 1010   | 12     | A        |
| 11     | 1011   | 13     | B        |
| 12     | 1100   | 14     | C        |
| 13     | 1101   | 15     | D        |
| 14     | 1110   | 16     | E        |
| 15     | 1111   | 17     | F        |

## 进制转换

### 其他进制 -> 十进制

任何进制的数字都可以转换为**数(d) * 基数<sup>i</sup>**的多项式

<img src="/Users/edz/Documents/2131-basic/images/image-20210305105644807.png" alt="image-20210305105644807" style="zoom:50%;" />



### 十进制 -> 二进制

1. ![image-20210305092604211](/Users/edz/Documents/2131-basic/images/image-20210305092604211.png)

2. 把小的十进制数(通常小于256)转换为二进制数有一个变通的方法，即把这个数分解为下列二进制位置量对应数的和。

   | 位置量       |      | 27   | 26   | 25   | 24   | 23   | 22   | 21   | 20   |
   | ------------ | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- |
   | 十进制对等量 |      | 128  | 64   | 32   | 16   | 8    | 4    | 2    | 1    |

   使用该表可以转换165为二进制数(10100101)2,如下所示：

   | 十进制 | 165  | =    | **128** | +    | **0** | +    | **32** | +    | **0** | +    | **0** | +    | **4** | +    | **0** | +    | **1** |
   | ------ | ---- | ---- | ------- | ---- | ----- | ---- | ------ | ---- | ----- | ---- | ----- | ---- | ----- | ---- | ----- | ---- | ----- |
   | 二进制 |      |      | 1       |      | 0     |      | 1      |      | 0     |      | 0     |      | 1     |      | 0     |      | 1     |

### 二进制、八进制、十六进制相互转换

当二进制不足位数时，左侧补0，小数位转换的时候，不足位数右侧补0

<img src="/Users/edz/Documents/2131-basic/images/image-20210305102451832.png" alt="image-20210305102451832"  />

## 数据存储

### 整数存储

#### 无符号数存储

只能保存0和正整数

1. 确定存储单元大小
2. 将这个整数转换为二进制
3. 左侧不足存储单元的位数补0

#### 符号+绝对值存储

1. 确定存储单元大小
2. 最高位1bit为符号位，正数为0，负数为1
3. 将绝对值转换为二进制填入存储单元，除符号位以外其他位置补0

使用这种方案存储数据，会存在+0和-0的问题

#### 补码存储

1. 确定存储单元大小

2. 将整数绝对值变成n位的二进制数。
   1. 如果整数是正数或零，以其原样存储
   2. 如果是负数，转换为补码存储（负数经过转换后，补码最高位一定是1）

补码：

1. 从右边依次复制位，直到有1被复制；接着，反转其余的位。
2. 先取反码，然后将结果加1。

### 实数存储

#### 浮点表示法

IEEE (*Institute of Electrical and Electronics Engineers*)：电气电子工程师学会

745：754编号的标准

| IEEE754          | 存储单元 | 符号位 | 指数位 | 尾数位 |
| ---------------- | -------- | ------ | ------ | ------ |
| 单精度（余127）  | 4byte    | 1      | 8      | 23     |
| 双精度（余1023） | 8byte    | 1      | 11     | 52     |

#### (101.11)<sub>2</sub> 转单精度表示

1. 规范化 101.11 = 1.0111 x 2<sup>2</sup>
2. 计算指数位，2 + 127 = 129 转 8bit 无符号存储单元 => 10000001
3. 计算尾数位，尾数 0111后面补0，补够23位 => 0111 0000 0000 0000 0000 000
4. 确定符号位，正数符号位为0



|        | 符号位 | 指数位   | 尾数位                       |
| ------ | ------ | -------- | ---------------------------- |
| 单精度 | 0      | 10000001 | 0111 0000 0000 0000 0000 000 |



#### (10100001.111)<sub>2</sub>转双精度表示

1. 规范化 10100001.111 = 1.0100001111 x 2<sup>7</sup>
2. 计算指数位，7 + 1023 = 1030 转11bit无符号存储单元 => 100 0000 0110
3. 计算尾数位，尾数位0100001111 后面补0，补够52位 => 0100 0011 1100 0000 0000 0000 0000 0000 0000 0000 0000 0000 0000
4. 计算符号位，负数符号位为1

|        | 符号位 | 指数位        | 尾数位                                                       |
| ------ | ------ | ------------- | ------------------------------------------------------------ |
| 双精度 | 1      | 100 0000 0110 | 0100 0011 1100 0000 0000 0000 0000 0000 0000 0000 0000 0000 0000 |

### 文本存储

#### ASCII码

需要记忆的几个数字和字符映射关系

- a <-> 97
- A <-> 65
- 0 <-> 48

#### Unicode

Unicode字符集的符号范围：0 ~ 0x10FFFF 

每个字符对应一个数字，转换为16进制表示，作为这个字符的编号，也叫作码点(code point)。表示方式为`U+xxxx`

Unicode码点的范围：U+0000 ~ U+10FFFF

##### UTF-32

将Unicode码点高位补0，凑够2byte（32bit），这种编码方式就是UTF-32

如果直接使用码点不补足高位，那么有的字符是1byte，有的字符是2byte，解码时对应多个byte，无法确定用1个byte转码点还是2个byte转码点。

缺点：浪费空间，同样内容的英语文本，它会比 ASCII 编码大四倍。

##### UTF-16

一个字符码点编码为2或4byte

- 基本平面的字符（U+0000 到 U+FFFF）编码为 2 个byte，直接使用码点，高位不足则补0
- 辅助平面的字符（U+010000 到 U+10FFFF）编码为 4 个byte

辅助平面编码的4byte需要带有特征，方便在解码的时候能够识别是4byte进行反向转换。

在基本平面内，从 U+D800 到 U+DFFF 是一个空段，即这些码点不对应任何字符。将辅助平面的一个码点，通过某种运算方式转换为U+D800 到 U+DFFF区间的两个码点的组合。

##### UTF-8

**UTF-8 是目前互联网上使用最广泛的一种 Unicode 编码方式**，它的最大特点就是**可变长。它可以使用 1 - 4 个字节表示一个字符，根据字符的不同变换长度**。

根据字符码点在表格中第一列的范围，决定编码后的二进制规则，将码点的二进制依次填充到x所代表的的位置上完成编码

| Unicode 十六进制码点范围 | UTF-8 二进制                        |
| :----------------------- | :---------------------------------- |
| 0000 0000 - 0000 007F    | 0xxxxxxx                            |
| 0000 0080 - 0000 07FF    | 110xxxxx 10xxxxxx                   |
| 0000 0800 - 0000 FFFF    | 1110xxxx 10xxxxxx 10xxxxxx          |
| 0001 0000 - 0010 FFFF    | 11110xxx 10xxxxxx 10xxxxxx 10xxxxxx |







