# GitHub 仓库初始化指南

## 1. 创建新的存储库

当在GitHub上创建一个新的存储库时，GitHub会提供一些快速设置的提示。下面是如何在命令行中设置一个新的存储库。

### 步骤:

- **初始化本地存储库**: 使用 `git init` 命令初始化新的本地git存储库。
- **添加 README 文件**:
  - 创建一个名为 `README.md` 的Markdown文件，这是一个描述项目的文档。
  - 使用 `echo "# financial-management-system" >> README.md` 在README文件中添加项目标题。
  - 使用 `git add README.md` 将README文件添加到暂存区。
- **首次提交**: 使用 `git commit -m "first commit"` 做出第一次提交。
- **主分支**: 使用 `git branch -M main` 将分支重命名为 `main`。
- **添加远程仓库**: 使用 `git remote add origin [仓库URL]` 添加新的远程仓库。
- **推送到GitHub**: 使用 `git push -u origin main` 将代码推送到GitHub。

## 2. 推送现有的存储库

如果已经有了一个本地git存储库并想要将其与GitHub同步。

### 步骤:

- **添加远程仓库**: 使用 `git remote add origin [仓库URL]`。
- **重命名分支**: 使用 `git branch -M main` 将分支重命名为 `main`（如果需要）。
- **推送到GitHub**: 使用 `git push -u origin main` 将本地存储库推送到GitHub。

## 3. 从另一个存储库导入代码

GitHub允许从其他版本控制系统如Subversion, Mercurial, 或 TFS导入项目。

### 步骤:

- 点击 `Import code` 按钮。
- 按照GitHub的指引完成导入过程。

## 注意事项:

- 每个存储库建议包含 `README`、`LICENSE` 和 `.gitignore` 文件。
- `README.md` 文件是项目的入口点，应详细介绍项目。
- `.gitignore` 文件指定了git应该忽略的不需要版本控制的文件。
- `LICENSE` 文件说明了他人可以如何使用这个存储库中的代码。

以上就是基本的GitHub存储库初始化步骤。记得替换 `[仓库URL]` 为自己的仓库链接。
# Windows上创建SSH密钥对

SSH密钥对包括一个公钥和一个私钥，用于安全地进行身份验证。以下是在Windows系统上创建SSH密钥对的步骤。

## 前提条件

- 确保已安装Git，它包含Git Bash工具。

## 生成SSH密钥对

1. **打开Git Bash**:
   使用Windows搜索功能找到并打开Git Bash。

2. **运行SSH-Keygen**:
   输入以下命令，替换`your_email@example.com`为你的GitHub邮箱地址。

   ```bash
   ssh-keygen -t rsa -b 4096 -C "your_email@example.com"

3. **保存SSH密钥**: 系统将询问你保存密钥的位置。可以使用默认位置，或者提供一个新的文件路径。

4. **创建安全密码（可选）**: 你可以为你的私钥设置一个密码。这步是可选的，但推荐。

## 添加SSH公钥到GitHub

1. **查看公钥**: 使用`cat`命令查看你的公钥。

   ```
   bashCopy code
   cat ~/.ssh/id_rsa.pub
   ```

2. **复制公钥内容**: 复制显示的公钥内容。

3. **添加到GitHub**:

   - 登录GitHub账户。
   - 进入`Settings` > `SSH and GPG keys`。
   - 点击`New SSH key`或`Add SSH key`。
   - 在`Title`输入一个描述性名称。
   - 在`Key`字段粘贴你的公钥。
   - 点击`Add SSH key`确认。

## 测试SSH连接

1. **测试连接**: 运行以下命令，测试与GitHub的SSH连接。

   ```
   bashCopy code
   ssh -T git@github.com
   ```

2. **确认认证**: 如果是第一次连接GitHub，你会被询问是否信任GitHub服务器。回答`yes`继续。

如果一切顺利，你应该看到GitHub的欢迎消息。

# 远程仓库

+ 检查已存在的远程仓库： 您可以通过运行以下命令来检查 Git 仓库中已存在的远程仓库列表：

```
bashCopy code
git remote -v
```

这将显示当前配置的所有远程仓库及其 URL。

+ 重命名远程仓库（如果需要）

```ba
git remote rename origin new-remote-name
```

+ 添加新的远程仓库：

```ba
git remote add origin <远程仓库的URL>
```

+ 删除远程仓库

```ba
git remote remove <远程仓库的名称>
```

+ 修改远程仓库名字

```ba
git remote rename <旧的远程仓库名称> <新的远程仓库名称>
```

# 本地仓库

要查看本地 Git 仓库的状态和信息，您可以使用以下常用的 Git 命令：

1. 查看当前分支： 使用以下命令来查看当前所在的分支：

```bash
git branch
```

当前分支前会有一个星号（*）标记。

2. 查看所有分支： 若要查看所有本地分支（包括远程跟踪分支），可以使用以下命令：

```bash
git branch -a
```

3. 查看仓库状态： 使用以下命令来查看本地仓库的状态，包括未提交的更改、已暂存的更改和未跟踪的文件：

```bash
git status
```

这将显示仓库的当前状态信息。

4. 查看提交日志： 若要查看提交历史记录，可以使用以下命令：

```
git log
```

这会显示所有提交的详细信息，按时间顺序列出。

5. 查看配置信息： 要查看 Git 仓库的配置信息，包括用户名、邮箱和其他设置，可以使用以下命令：

```bash
git config --list
```

这将列出所有的 Git 配置信息。

# 用户名配置

1. 设置全局用户名：

```bash
git config --global user.name "Your New Name"
```

将 "Your New Name" 替换为您想要设置的新用户名。

2. 设置每个仓库的用户名：

如果您只想为特定仓库设置不同的用户名，可以进入该仓库的目录，然后运行以下命令：

```bash
git config user.name "Your New Name"
```

# Git 中的 HTTP 和 SSH 配置与切换方法

Git 支持多种数据传输协议，最常用的是 HTTP(S) 和 SSH。以下是这两种方法的配置步骤，以及它们之间的区别和切换方法。

## HTTP 和 HTTPS

### 配置方法

要通过HTTP(S)与GitHub交互，通常不需要做特别的配置。当你克隆仓库或推送代码时，Git 会提示你输入GitHub的用户名和密码（或个人访问令牌）。

### 切换到 HTTP(S)

如果你的仓库当前使用SSH，并且你想切换到HTTP(S)，可以修改远程仓库的URL：

```bash
git remote set-url origin https://github.com/username/repository.git
```

## SSH

### 配置方法

1. **生成SSH密钥**： 在终端中运行 `ssh-keygen` 并按指示操作。你可以为密钥设置密码。
2. **将SSH公钥添加到GitHub**： 将生成的公钥（通常是 `~/.ssh/id_rsa.pub`）复制并粘贴到GitHub账户的SSH密钥部分。

### 切换到 SSH

如果你的仓库当前使用HTTP(S)，并且你想切换到SSH，需要执行以下命令：

```bash
git remote set-url origin git@github.com:username/repository.git
```

同样，把 `username` 和 `repository` 替换为你的GitHub用户名和仓库名。

## 解释与区别

SSH（Secure Shell）和HTTPS（HyperText Transfer Protocol Secure）是两种常用的网络协议，用于安全地传输数据。在Git中，它们都用于安全地与远程仓库通信，如GitHub，但是它们在认证、配置和使用方面有一些关键的区别：

### SSH

- **认证方式**：SSH使用密钥对进行认证。用户需要生成一对密钥（公钥和私钥），并将公钥添加到GitHub账户。私钥保留在用户的计算机上。
- **连接设置**：SSH需要在用户的计算机上设置SSH密钥。这需要额外的初始配置，但一旦完成，用户就不必每次推送或拉取时都输入用户名和密码。
- **端口**：SSH默认使用端口22。
- **适用场景**：SSH特别适合开发者和那些需要频繁推送代码的用户，因为它可以避免频繁地输入凭据。
- **速度**：SSH可能在某些操作上比HTTPS快一些，尽管这个差异通常很小，对大多数用户来说几乎不可察觉。
- **防火墙和网络限制**：在某些网络环境中，SSH可能会被阻止，特别是在严格限制出站端口的企业网络环境中。

### HTTP(S)

- **认证方式**：HTTPS使用用户名和密码进行认证。对于GitHub，还可以使用个人访问令牌作为密码进行认证。
- **连接设置**：HTTPS不需要在客户端进行特殊的设置，只需使用GitHub账户的用户名和密码（或个人访问令牌）即可。
- **端口**：HTTPS使用端口443，这是网页浏览中使用的标准端口。
- **适用场景**：HTTPS是一种简单、便捷的方法，特别是对于那些偶尔需要与远程仓库交互的用户。
- **速度**：对于大多数操作，HTTPS的速度与SSH相当，用户不太可能注意到明显的差异。
- **防火墙和网络限制**：HTTPS很少受到防火墙的限制，因为它使用的是标准的互联网浏览端口。
