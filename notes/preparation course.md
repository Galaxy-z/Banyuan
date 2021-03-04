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
  |         git pull         |       从远端库更新       |

