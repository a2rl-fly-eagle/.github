### Git仓库拉取流程

git clone 仓库链接（http或ssh） //推荐使用ssh。例：

```
git clone git@github.com:a2rl-fly-eagle/Planning.git  //克隆Planning仓库
```

#### SSH生成流程（linux版）

1.生成新的SSH密钥，根据流程提示回车

```
ssh-keygen -t rsa -b 4096 -C "your_email@example.com" 
```

2.列出生成的私钥和公钥，默认目录/home/your_username/.ssh/id_rsa(id_rsa.pub)

```
ls -l ~/.ssh/id_rsa*
```

3.将id_rsa.pub添加到github设置里

4.测试ssh协议是否连接正常

```
ssh -T git@github.com
```

在第一次连接时，会提示The authenticity of host 'github.com (IP_ADDRESS)' can't be established.属于正常现象，输入yes回车就可以。

### Github提交流程

##### 新功能添加时，务必在子分支中上传，待联调测试完成后再将稳定版本合并至主分支

1.查看目前git状态，包含所在分支，是否有改动未提交

```
git status
```

2.拉取合并该分支最新代码，例：git pull origin main在本地拉取合并主分支代码。

```
git pull origin 分支名
git fetch  //仅拉去该分支最新代码
git merge  //合并代码
```

git fetch加git merge等于git pull，根据情况选择是否需要手动合并。

在计划推送新代码时，务必先进行最新代码拉取，以防代码冲突。

3.添加修改文件，如果将所有更改一次性添加，使用git add --all。建议分情况添加，并伴有commit说明。

```
git add 文件名
```

4.添加说明，双引号里填写修改内容，尽量简洁

```
git commit -m "简要说明修改内容"
```

5.推送代码至远程仓库，例：git push origin main

```
git push origin 分支名
```



### 分支设置流程

1.查看本地分支

```
git branch
```

2.创建，切换子分支。分支名建议按照个人名字或者功能版本命名

```
git checkout -b 分支名  //创建并切换至子分支
git checkout 分支名  //切换至该分支
```

3.继续提交流程

### 代码审核及合并流程

1.新功能添加时，需要在子分支中上传。

2.在子分支经过测试后，网页端点击pull request提交合并请求。 //若在本地操作，直接拉取该分支代码就行

3.再次确认无误后，点击merge合并分支。  //若在本地操作，解决代码冲突后使用git merge “分支名”，再次使用提交流程。

4.确认无需该子分支后，本地仓库删除本地子分支

```
git branch -d 子分支名
```

5.删除远程仓库子分支  

```
git push origin --delete 子分支名
```

//第4步与第5步也可以在网页端完成，在分支按钮下有对应的设置方式。

### Project工作流程

1.点击To Do列表下方Add item，再次点击对话框左侧的加号后，在弹出的对话框上方Blank issue里选择自己对应的库（组）。

2.在标题和介绍里填写任务。

3.下方Assignee选择工作完成人，Label根据提示选择类型（例如enhancement表示新功能，document表示文档类型的任务等），点击Create创建issue。

4.创建的Issue会显示在To Do列表里，表示要完成的工作。再次点击该issue，在右侧列表里的project选择start date和end date，表示任务开始时间和最晚结束时间。

5.点击右上角x号，关闭编辑。

6.在开始工作后，点击该issue，再点击右侧列表里面的project里的status，选择In Progress。

7.工作完成后，点击该issue，将状态改为Done，对应的Issue会自动关闭。

### 软件栈结构

![git软件栈](https://github.com/user-attachments/assets/644578a5-d30e-456b-b9cf-bfdd3add8d72)
