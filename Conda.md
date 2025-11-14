## 🧩 一、基础操作

| 命令                 | 说明                                  | 示例                 |
| -------------------- | ------------------------------------- | -------------------- |
| `conda --version`    | 查看 conda 版本                       | `conda --version`    |
| `conda info`         | 查看 Conda 基本信息（包括环境路径等） | `conda info`         |
| `conda list`         | 查看当前环境已安装的包                | `conda list`         |
| `conda update conda` | 更新 Conda 自身                       | `conda update conda` |

------

## 🌱 二、环境管理命令

| 命令                                      | 说明                         | 示例                                  |
| ----------------------------------------- | ---------------------------- | ------------------------------------- |
| `conda env list` 或 `conda info --envs`   | 查看所有虚拟环境             | `conda env list`                      |
| `conda create --name env_name python=3.9` | 创建新环境并指定 Python 版本 | `conda create --name py39 python=3.9` |
| `conda activate env_name`                 | 激活环境                     | `conda activate py39`                 |
| `conda deactivate`                        | 退出当前环境                 | `conda deactivate`                    |
| `conda remove --name env_name --all`      | 删除整个环境                 | `conda remove --name py39 --all`      |
| `conda rename --name old_name new_name`   | 重命名环境（新版本可用）     | `conda rename --name py38 py39`       |
| `conda env export > environment.yml`      | 导出当前环境配置文件         | `conda env export > environment.yml`  |
| `conda env create -f environment.yml`     | 从配置文件创建环境           | `conda env create -f environment.yml` |
| `conda env remove -n env_name`            | 删除环境（与上面等价）       | `conda env remove -n py39`            |
| `conda clean --all`                       | 清理未使用的缓存和包         | `conda clean --all`                   |

------

## 📦 三、包管理命令

| 命令                                         | 说明             | 示例                               |
| -------------------------------------------- | ---------------- | ---------------------------------- |
| `conda install package_name`                 | 安装包           | `conda install numpy`              |
| `conda install package_name=1.21.0`          | 安装指定版本     | `conda install numpy=1.21.0`       |
| `conda install package_name -c channel_name` | 指定镜像源安装   | `conda install pytorch -c pytorch` |
| `conda update package_name`                  | 更新包           | `conda update numpy`               |
| `conda remove package_name`                  | 卸载包           | `conda remove numpy`               |
| `conda search package_name`                  | 搜索包信息       | `conda search numpy`               |
| `conda list -n env_name`                     | 查看指定环境的包 | `conda list -n py39`               |

------

## 🌍 四、源管理（换镜像源）

| 命令                                                         | 说明       | 示例                                                         |
| ------------------------------------------------------------ | ---------- | ------------------------------------------------------------ |
| `conda config --show channels`                               | 查看当前源 | `conda config --show channels`                               |
| `conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main/` | 添加清华源 | `conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main/` |
| `conda config --set show_channel_urls yes`                   | 显示包来源 | `conda config --set show_channel_urls yes`                   |
| `conda config --remove-key channels`                         | 清除所有源 | `conda config --remove-key channels`                         |

------

## 🧠 五、环境路径与信息

| 命令                                              | 说明                      | 示例                |
| ------------------------------------------------- | ------------------------- | ------------------- |
| `conda info --envs`                               | 查看所有环境路径          | `conda info --envs` |
| `conda info --base`                               | 查看 base 环境路径        | `conda info --base` |
| `where conda`（Windows） / `which conda`（Linux） | 查看 conda 可执行文件路径 | `where conda`       |