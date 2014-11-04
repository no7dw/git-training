
#basic usage

忘记svn ， 尽情享受git带来的新世界

----------


##clone

    git clone https://github.com/no7dw/lianlianpay.git

##pull

    git checkout the_branch_u_want
    git pull

##commit

    git add your/file/path
    #commit to local repos
    git commit -m 'commit log'

##branch

    #新开一个branch
    git branch your_new_branch
    git checkout your_new_branch

##Rules to follow


##merge

    git merge --no-ff fixbug-0.1

使用--no-ff参数后，会执行正常合并，在Master分支上生成一个新节点。为了保证版本演进的清晰，我们希望采用这种做法。关于合并的更多解释，请参考Benjamin Sandofsky的《Understanding the Git Workflow》。

    git check dev
    git fetch origin
    git merge origin/feture_xxx
    git commit -a -m 'if you have any to commit'
    git push origin dev

##Git发布分支
case: 准备发布，但是还有code 提交到dev分支
＃创建一个预发布分支：从Develop分支上面分出来的

    git checkout -b release-1.2 develop

确认没有问题后，合并到master分支：

    git checkout master
    git merge --no-ff release-1.2
    # 对合并生成的新节点，做一个标签
    git tag -a 1.2 

再合并到develop分支：

    git checkout develop
    git merge --no-ff release-1.2

最后，删除预发布分支：

    git branch -d release-1.2


----------

##Git的注意事项	

 - 功能分支：不要以人名命名，以具体功能命名 
 - hotfix分支：fixbug-xxx 
 - commit log：尽量详细 检查错误信息
 - 经常pull and push(>10/day)

