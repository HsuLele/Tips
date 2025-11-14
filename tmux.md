[Tmux教程 （一文就够）-CSDN博客](https://blog.csdn.net/CSSDCC/article/details/121231906)

# ✔ 第 1 步：安装 tmux（如果已经安装会提示）

直接运行：

```
sudo dnf install -y tmux
```

这一步只需要执行一次。

------

# ✔ 第 2 步：创建一个 tmux 会话（类似无敌后台空间）

我们先给会话起名叫 **rag**：

```
tmux new -s rag
```

执行后你会看到界面变了，最底部有绿色条。
 这意味着你 **已经在 tmux 里面** 了。

------

# ✔ 第 3 步：在 tmux 内启动 LightRAG

通常你的运行方法类似：

```
python your_script.py
```

或者：

```
python examples/simple_rag.py
```

你只需要 **像平常一样跑程序**：
 例如：

```
python graph_visual_with_html.py
```

或你自己的 LightRAG 分析代码、RAG pipeline 启动脚本等。

🏁 **关键点：你在 tmux 内运行的程序，SSH 断线也不会退出。**

------

# ✔ 第 4 步：退出 tmux，但保持程序运行（最关键）

按键：

```
Ctrl + B，然后放开，再按 D
```

（不要一起按）

你会看到回到普通命令行，像这样：

```
[detached (from session rag)]
(LightRAG) llxu@fedora:~/LightRAG$
```

代表你已经 **成功从 tmux 分离，后台仍在运行，永不掉线**。

------

# ✔ 第 5 步：检查 tmux 是否仍在运行

任何时候你都可以：

```
tmux ls
```

你会看到：

```
rag: 1 windows (created ...)
```

------

# ✔ 第 6 步：重新进入正在运行的会话（例如 SSH 重连后）

执行：

```
tmux attach -t rag
```

你会回到之前运行 LightRAG 的终端，看到继续输出。

------

# ✔ 第 7 步：关闭 tmux 会话（如果任务结束）

如果程序自然结束，你可以关闭：

在 tmux 内输入：

```
exit
```

或外面执行：

```
tmux kill-session -t rag
```