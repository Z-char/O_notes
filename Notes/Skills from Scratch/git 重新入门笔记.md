~~你问我为什么要重新入门，当然是因为我忘了啊~~。
```git
git init
```
这个指令还是没忘的，意思是将目前的文件夹初始化为一个 git 仓库。
那么 git 仓库有什么好处？为什么要初始化一个 git 仓库出来？
1. git 仓库可以很方便的管理很多个版本，这样的话如果写错了也能复盘回去，相当于给了你一个免费的 file recovery。
2. 第二点好处就是可以和 remote repo 进行同步，这意味着你不管换了什么设备，只要另一个设备支持 git，你就可以 `git clone` 把你的文件拿回来。
现在，你有了一个 git 管理的文件夹了，你可以用 `git status` 查看 git 管理的状态。
接下来，假设你这个文件夹里本来有一些文件或者你添加了一些文件，git 不会自动管理这些文件，所以你需要使用 `git add` 指令来添加对他们的控制，注意 git 有几个不同的区划分，工作区，暂存区，和你的版本库。`git add` 会把工作区的文件扔到暂存，这时候可以用 `git commit` 去把他们提交到版本管理里面，注意一般都要写 `git commit -m "message related to this commit"`，为了明确每次提交都是什么。当然了，你直接写 `git commit` 也可以就是了，他会进入一个界面让你填写提交消息。
>这里发现 `git commit` 的时候会提示你需要 "登陆账号" 或者准确的说 "需要知道提交者是谁"，于是你需要 `git config` 去配置用户邮箱和名字，加深了我对于这个东西的理解。
>另一点理解就是，其实你英语只要足够好，基本上下载好 `git bash` 这个东西，会使用 `git help` 指令，就能自行入门了。

~~写到这里的时候电脑突然像那种坏了的显示屏一样闪了几下然后关了，感觉需要加入任务清单去修一下电脑~~。
好了，那么我们介绍完了第一个好处，可以管理我们的文件了，接下来就是第二个好处 remote repo。
为了把信息同步到远程库，首先我们需要一个远程库，可以打开 GitHub 然后创建一个新的库，事实上 GitHub 就会提示你如何把两个库关联起来。
`git remote add origin git@github.com:Z-char/O_notes.git` 用这个把远程库加入选择链接，`origin` 是这个远程库的名字你可以自选，后面是你建立的库的地址，我这个是 ssh，你也可以用 https 去加入。
接下来你需要用 `git push -u origin master` 去把本地的 master 分支 push 到远端的 origin 库，需要注意的是，推送的话你需要有权限才能更改云端的内容，具体来说，你需要在 GitHub 里面先把你的 ssh 公钥传上去，这样 GitHub 就能识别你的电脑了，push 的时候就可以 push 上去，具体创建 ssh-key 可以看 [这里](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)。
基础内容介绍完了，已经可以支持写内容和同步了，分支和标签有机会了再介绍吧。