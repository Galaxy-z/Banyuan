# 作业



1. 在任意文件夹内，创建一个文件夹banyuan_dir

   ```shell
   mkdir banyuan_dir
   ```

   

2. 在该文件夹内，创建2个子文件夹a,b

   ```shell
   cd banyuan_dir
   mkdir a
   mkdir b
   ```

   

3. 在a文件夹内创建aa1.txt、aa2.txt，在b文件夹内创建bb.txt

   ```shell
   cd a/
   touch aa1.txt
   touch aa2.txt
   touch ../b/bb.txt
   ```

   

4. aa1.txt内内容为'aa1内的内容'，aa2.txt内内容为'aa2内的内容'

   ```shell
   vim aa1.txt
   vim aa2.txt
   ```
   

   
5. b.txt内内容为 'b内的内容'

   ```shell
   vim ../b/bb.txt
   ```

   

6. 打印输出aa1与aa2文件联合的内容

   ```shell
   cat aa1.txt aa2.txt
   ```

   

7. 将aa1.txt移动到b文件夹中，并改名为bb1.txt

   ```shell
   mv aa1.txt ../b/bb1.txt
   ```

   

8. 将bb1.txt的权限设置为可读不可写

   ```shell
   cd ../b/
   chmod 444 bb1.txt
   ```

   

9. 最终将整个banyuan_dir移除

   ```shell
   cd ../../
   rm -rf banyuan_dir
   ```

   

