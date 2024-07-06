

```
We recommend every repository include a README, LICENSE, and .gitignore.
```

### …or create a new repository on the command line



```
echo "# test" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/aoozoo/test.git
git push -u origin main
```

### …or push an existing repository from the command line



```
git remote add origin https://github.com/aoozoo/test.git
git branch -M main
git push -u origin main
```



![image-20240625170253937](http://imgs.ilee.xyz/img/image-20240625170253937.png)

克隆之后，git 远程，git 本地仓库，磁盘目录三者的状态是一样的

![image-20240625171319551](http://imgs.ilee.xyz/img/image-20240625171319551.png)

`git checkout -b my-feature` 一般下载代码之后，都是新建一个分支，开始工作，这样不会影响到 master 分支

![image-20240625171749768](http://imgs.ilee.xyz/img/image-20240625171749768.png)

如果想看看哪些文件发生了变化，可以使用 git diff 命令查看

![image-20240625172057223](http://imgs.ilee.xyz/img/image-20240625172057223.png)

`git commit` 会在 git 本地仓库生成一个提交

![image-20240625172148739](http://imgs.ilee.xyz/img/image-20240625172148739.png)

push 之后 git 远程仓库就会多出来一个 my-feature 分支，把 git 本地仓库的 my-feature 分支推送到 git 远程仓库

![image-20240625172312266](http://imgs.ilee.xyz/img/image-20240625172312266.png)

有其他同事在 git 远程仓库，做了一次名为 update 的提交，我们想看看当前的工作和那次提交是否兼容，所以要先把远程仓库的内容拉下来

![image-20240625172401346](http://imgs.ilee.xyz/img/image-20240625172401346.png)

先把本地切换到 main 分支

![image-20240625172428323](http://imgs.ilee.xyz/img/image-20240625172428323.png)



![image-20240625172514152](http://imgs.ilee.xyz/img/image-20240625172514152.png)

`git pull origin master` 之后，本地 git 仓库，和磁盘里面的状态，就和 git 远程仓库的状态一样了，都有了 update 这次提交后的状态

![image-20240625204747118](http://imgs.ilee.xyz/img/image-20240625204747118.png)

`git checkout my-feature` 之后，工作目录就只有 my-feature 分支中的代码

![image-20240625204947525](http://imgs.ilee.xyz/img/image-20240625204947525.png)

![image-20240625205126967](http://imgs.ilee.xyz/img/image-20240625205126967.png)

`git rebase main`  的意思是说，先不管 my-feature 分支 Init 之后的提交，先把 main 分支上的提交拿进来，最后再把 f-commit 放进来（相当于在最新的 `不管main上面有几次提交` main 的 分支上面，再加上 my-feature 分支的修改，`这也是使用 rebase 而不是 merge 的好出`），如果有冲突，这个时候需要手动解决冲突

![image-20240625212423848](http://imgs.ilee.xyz/img/image-20240625212423848.png)



![image-20240625213209056](http://imgs.ilee.xyz/img/image-20240625213209056.png)

因为做了，rebase 操作，所以 push 的时候一定要加上 `-f` 这个选项

![image-20240625213425951](http://imgs.ilee.xyz/img/image-20240625213425951.png)

通常认为 main 分支是属于项目的，大家不能够随便动，feature 分支是个人创建的，所以需要向项目的负责人，发起一个 pull request ，请求将 feature 分支的代码 pull 到 main 分支当中



![image-20240625213719482](http://imgs.ilee.xyz/img/image-20240625213719482.png)

为了 main 分支尽可能的简洁，并且保持main分支的代码都是生产可用的，feature 分支通常可能有多次提交，通常采用 `squash and merge` ，这样会把 feature 分支的改动，变成一次提交，合并进去 main 分支，main分支只会有一次提交产生，

通常情况，merge 之后，就会把 git 远程仓库中的 my-feature 分支删除



![image-20240625220439022](http://imgs.ilee.xyz/img/image-20240625220439022.png)

git 远程仓库当中 my-feature 分支被删除了，但是 git 本地仓库当中还有 my-feature 分支，

![image-20240625220546423](http://imgs.ilee.xyz/img/image-20240625220546423.png)

所以先切换到 main 分支上面，然后把 git 本地仓库中的 my-feature 分支删除



![image-20240625220711126](http://imgs.ilee.xyz/img/image-20240625220711126.png)

最后拉一次 git 远程仓库当中的 main 分支的最新的代码



![image-20240625220822558](http://imgs.ilee.xyz/img/image-20240625220822558.png)













































