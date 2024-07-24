# Git 学习

## 一、说明

​	本仓库是本人主要用来存放学习git的一些命令以及心得。

## 二、项目上传

[^注释]: 将项目上传到`github`的主要操作流程

1. 在`github`新建仓库，记住不要勾选`添加README.md文件`的选项

2. 在本地新建一个文件夹

3. 将项目文件放入该文件夹

4. 打开Git Bash软件，在命令行输入 `cd` 命令，进入该文件夹

5. 初始化仓库：`git init` 

6. 添加内容到**暂存区**：`git add "文件/文件夹名"`

7. 将暂存区内容添加到本地仓库：`git commit -m "备注信息"`

8. 将当前分支（默认分支：master）强制重命名为`main` 分支

   -  `git branch -M main`

     - `-M` 表示强制重命名
       - `m`是move的缩写
       - `M`是强制版本

     - 若`main`已经存在，则先删除现有的 `main` 分支，再进行重命名操作。如果只使用 `-m` 选项，Git 会报错提示目标分支已存在。

9. 将一个远程仓库添加到本地 Git 仓库

   - `git remote add origin git@github.com:用户名/仓库名.git` 
     - `git remote add`：这是用于添加远程仓库的 Git 命令。你可以在本地仓库中添加一个或多个远程仓库，以便与它们进行交互。
     - `origin`：这是你给远程仓库起的一个名字，通常默认使用 `origin` 这个名字。你也可以使用其他名字，但 `origin` 是一个惯例，表示默认的远程仓库。

10. 将本地 `main` 分支的内容推送到远程仓库，并设置跟踪关系

    - `git push -u origin main`
      - `git push`：这是将本地提交的更改推送到远程仓库的命令。
      - `-u` 或 `--set-upstream`：这个选项设置本地分支和远程分支之间的跟踪关系。这样，以后在执行 `git pull` 或 `git push` 时，不需要再指定远程分支的名称。
      - `origin`：这是远程仓库的名称，在你之前使用 `git remote add origin <URL>` 时指定的名字。
      - `main`：这是你要推送的本地分支的名称。

## 三、示例

[^注释]: 上传`README.md`文件

从第5步开始演示：

```bash
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin git@github.com:Handoly/Git-Learnng.git
git push -u origin main
```

## 四、常见错误

- `error: failed to push some refs to 'github.com:Handoly/weather-forecast.git'`

  ​	在发送`git push -u origin main`后出现这个错误，有可能是因为在github远程仓库进行了操作（如上传文件等），从而导致远程仓库发生了变化而本地仓库却没有更新，导致仓库不匹配，此时应该先将远程仓库拉取到本地仓库进行更新，再进行推送。操作如下：

  - `git pull origin main` 

## 五、其他

### 1.本地与远程仓库的连接





