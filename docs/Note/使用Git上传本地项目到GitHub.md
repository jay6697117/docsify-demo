## 上传本地项目到GitHub

**在git bash界面输入GitHub名称和邮箱：**

    $ git config --global user.name  "***"
    
    $ git config --global user.email  "***"

**先创建一个本地的版本库（文件夹）,将项目复制到文件夹下，进入这个文件夹，右击打开Git bash命令行窗口。**
1. 通过命令`git init`把这个文件夹变成Git可管理的仓库
2. 通过命令`git add .`把项目添加到仓库
3. 用`git commit -m "备注信息***"` 把项目提交到本地仓库。
4. 在Github上创建好Git仓库之后和本地仓库进行关联
   ​	
   `$ git remote add origin https://github.com/****(github仓库地址)`

5. 把本地库的所有内容推送到远程仓库（Github）上

   `$ git push -u origin master`

    第一次上传要加上`-u`这个参数，下次再从本地库上传内容的时候只需		
    	
   `$ git push origin master`
   ​	

**使用git 对源代码进行push到gitHub时可能会出错**
出现错误的主要原因是github中的README.md文件不在本地代码目录中


    git pull --rebase origin master

执行上面代码后可以看到本地代码库中多了README.md文件

## 修改.gitignore文件
在本地`.gitignore`文件中加入

```java
 .idea 		  (idea自动生成) 
 .project     (eclipse自动生成)
  target
```

使在用git上传时屏蔽这两个文件夹

## 在GitHub上删除某个文件夹

    $ git rm -r --cached target              # 删除target文件夹
    $ git commit -m '删除了target'       
    $ git push -u origin master

本地项目中的target文件夹不受操作影响,删除的只是远程仓库中的target