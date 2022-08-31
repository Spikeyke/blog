## Git 四个工作区域  
> 工作目录（Working Directory）  
暂存区（Stage/Index）  
本地仓库（Local Repository 或 Git Directory）  
远程仓库（Remote Repository）  
## Git四个工作区域之间的转换关系  
![](https://upload-images.jianshu.io/upload_images/23885300-9fc53b2df3a1f80a.png?imageMogr2/auto-orient/strip|imageView2/2/w/1200/format/webp)  
> 1.在工作目录中添加、修改文件；  
2.将需要进行版本管理的文件放入暂存区域；  
3.将暂存区域的文件提交到git本地仓库;  
4.将git 本地仓库的文件推送到远程仓库;  
因此，git管理的文件有三种状态：  
    已修改（modified）,  
    已暂存（staged）,  
    已提交(committed)  
## 文件的四种状态
> 版本控制就是对文件的版本控制，要对文件进行修改、提交等操作，首先要知道文件当前在什么状态，不然
可能会提交了现在还不想提交的文件，或者要提交的文件没提交上。
GIT不关心文件两个版本之间的具体差别，而是关心文件的整体是否有改变，若文件被改变，在添加提交时
就生成文件新版本的快照，而判断文件整体是否改变的方法就是用SHA-1算法计算文件的校验和。  

![](https://upload-images.jianshu.io/upload_images/23885300-a42fc3a9887b7236.png?imageMogr2/auto-orient/strip|imageView2/2/w/1200/format/webp)  

> Untracked: 未跟踪, 此文件在文件夹中, 但并没有加入到git库, 不参与版本控制. 通过git add 状态变为Staged.   
> 
> Unmodify:  文件已经入库, 未修改, 即版本库中的文件快照内容与文件夹中完全一致. 这种类型的文件有两种去处, 如果它被修改, 而变为Modified.如果使用git rm移出版本库, 则成为Untracked文件  
> 
> Modified: 文件已修改, 仅仅是修改, 并没有进行其他的操作. 这个文件也有两个去处, 通过git add可进入暂存staged状态, 使用git checkout 则丢弃修改过, 返回到unmodify状态, 这个git checkout即从库中取出文件, 覆盖当前修改    
> 
> Staged: 暂存状态. 执行git commit则将修改同步到库中, 这时库中的文件和本地文件又变为一致, 文件为Unmodify状态.执行git reset HEAD filename取消暂存,文件状态为Modified  

## 文件状态的转变
![](https://upload-images.jianshu.io/upload_images/23885300-7d6f58d9cf882f29.png?imageMogr2/auto-orient/strip|imageView2/2/w/1200/format/webp)  
> 新建文件--->Untracked  
使用add命令将新建的文件加入到暂存区--->Staged  
使用commit命令将暂存区的文件提交到本地仓库--->Unmodified  
如果对Unmodified状态的文件进行修改---> modified  
如果对Unmodified状态的文件进行remove操作--->Untracked
