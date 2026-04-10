# 将本地现有项目推送到 Gitee 新建仓库（完整命令行指南）

> 适用场景：你本地已经有一个完整的项目文件夹（例如包含代码、模型权重等），想要将其**首次推送**到 Gitee 上新建的**空白仓库**。

---

## 一、在 Gitee 网页端创建空白仓库

1. 登录 [Gitee](https://gitee.com)，点击右上角 `+` → **新建仓库**。
2. 填写仓库名称（例如 `apex`），选择公开或私有。
3. **⚠️ 重要**：**不要勾选**“使用 Readme 文件初始化仓库”以及任何其他初始化选项。
4. 点击 **创建**，获得仓库地址，例如：  
   `https://gitee.com/zafu-liangdong/apex.git`

---

## 二、本地终端操作（请逐条复制执行）

> 以下命令请在你的本地项目**根目录**下执行。  
> 记得将 `<...>` 中的内容替换为你自己的实际路径和仓库地址。

```bash
# 1. 进入你的本地项目根目录（替换 <...> 为你的实际路径）
cd /path/to/your/project          # 例如：cd ~/Desktop/APEX
pwd                               # 确认当前路径正确

# 2. （可选）如果之前已初始化过 Git，删除旧仓库，确保干净重来
rm -rf .git

# 3. 初始化 Git 仓库并提交所有文件
git init
git add -A                        # 添加所有文件（包括大文件、权重等）
git commit -m "Initial commit: full project"

# 4. 关联远程 Gitee 仓库（替换 <你的仓库地址>）
git remote add origin <你的仓库地址>
# 示例：git remote add origin https://gitee.com/zafu-liangdong/apex.git

# 5. 查看当前本地分支名（通常为 main 或 master）
git branch

# 6. 强制推送到远程仓库（根据上一步的分支名选择对应命令）
#    如果分支名是 main：
git push -u origin main --force

#    如果分支名是 master：
git push -u origin master --force
