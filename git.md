- 初始化仓库

​		git init

- 绑定远程仓库（HTTPS 或 SSH 都可以）

​		git remote add origin https://github.com/HsuLele/xxx.git

- 初次提交，命名当前分支为 main（GitHub 默认分支名）

​		git branch -M main

- 查看文件状态（可选）

​		git status

- 添加全部文件到暂存区

​		git add .

- 提交改动（-m 后是提交说明）

​		git commit -m "xx内容"

- 推送到远程 main 分支

​		git push origin main



- 初次克隆（在另一台电脑上）

​		git clone https://github.com/HsuLele/RAG_note.git

- 拉取远程更新（同步新内容）

​		git pull origin main

git status						查看当前改动状态
git remote -v			  	查看远程仓库地址
git branch				   	查看当前分支
git log --oneline		 	查看提交记录



**SSH连接提交**

目前我已在github设置中 提供了个人的公钥（生成密钥并添加，见下）

## 1️⃣ 克隆远程仓库到本地（第一次获取仓库）

如果你还没有本地副本：

```
git clone git@github.com:用户名/仓库名.git
```

示例：

```
git clone git@github.com:HsuLele/RAG_note.git
```

> 注意：这里的 `git@github.com:` 是 SSH 形式，不是 HTTPS。

- 克隆完成后，本地会自动有一个名为 `origin` 的远程仓库指向 GitHub。

## 2️⃣ 已有本地仓库，切换远程地址为 SSH

如果你之前用 HTTPS 克隆了仓库，可以改为 SSH 连接：

```
cd path/to/your/repo
git remote set-url origin git@github.com:用户名/仓库名.git
```

- 用 `git remote -v` 查看是否修改成功：

```
origin  git@github.com:用户名/仓库名.git (fetch)
origin  git@github.com:用户名/仓库名.git (push)
```

## 3️⃣ 日常操作

之后的操作就完全自动了，无需每次输入账号密码。



## 一、生成 SSH Key

### 1️⃣ 个人默认账户（HsuLele）

打开命令行：

```
ssh-keygen -t rsa -b 4096 -C "你的GitHub邮箱"
```

- 按回车，使用默认路径 `~/.ssh/id_rsa`
- 生成两文件：
  - `id_rsa` → 私钥（不要泄露）
  - `id_rsa.pub` → 公钥

### 2️⃣ （可选）第二个账户或特殊仓库

```
ssh-keygen -t rsa -b 4096 -C "work_email@example.com" -f ~/.ssh/id_rsa_work
```

- `-f` 指定文件名
- 生成：
  - `id_rsa_work` → 私钥
  - `id_rsa_work.pub` → 公钥

------

## 二、把公钥添加到 GitHub

1. 登录 GitHub → **Settings → SSH and GPG keys → New SSH key**
2. 将 `id_rsa.pub` 或 `id_rsa_work.pub` 内容粘贴进去
3. 保存

> 这样你这把 Key 就可以访问你账户下的所有仓库了。
