# markdown

- 标题

  ```markdown
  # 一级标题
  ## 二级标题
  ### 三级标题
  ……
  ###### 六级标题
  ```

- 段落

  - 字体

    ```markdown
    *斜体文本*
    _斜体文本_
    **粗体文本**
    __粗体文本__
    ***粗斜体文本***
    ___粗斜体文本___
    ```

  - 分割线

    ```markdown
    ***
    * * *
    *****
    - - -
    ----------	
    ```

  - 删除线

    ```markdown
    ~~BAIDU.COM~~
    ```

  - 下划线

    ```markdown
    <u>带下划线文本</u>
    ```

  - 脚注

    ```markdown
    创建脚注格式类似这样 [^RUNOOB]。
    
    [^RUNOOB]: 菜鸟教程 -- 学的不仅是技术，更是梦想！！！
    ```

- 列表

  - 无序列表

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

  - 有序列表

    ```markdown
    1. 第一项
    2. 第二项
    3. 第三项
    ```

- 代码

  ~~~markdown
  `printf()` 函数
  ```javascript
  $(document).ready(function () {
      alert('RUNOOB');
  });
  ```
  ~~~

- 区块

  ```markdown
  > 区块引用
  > 菜鸟教程
  > 学的不仅是技术更是梦想
  ```

- 链接

  ```markdown
  [链接名称](链接地址)
  
  或者
  
  <链接地址>
  ```

- 图片

  ```markdown
  ![alt 属性文本](图片地址)
  
  ![alt 属性文本](图片地址 "可选标题")
  ```

- 表格

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
|  Clear  |                             清屏                             |



---

# git

- 原理

<img src="/Users/edz/Library/Application Support/typora-user-images/image-20210303160810029.png" alt="image-20210303160810029" style="zoom: 25%;" />

- 命令

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
  |         git pull         | 从远端库更新链接git hub  |

- 本地库链接远程库

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

- SSH

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
  >

  