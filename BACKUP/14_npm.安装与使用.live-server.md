# [npm 安装与使用 live-server](https://github.com/hadleysu/gitblog/issues/14)

# npm 安装与使用 `live-server`

## 1. 什么是 `live-server`？

`live-server` 是一个轻量级的开发服务器，具有实时重载功能。它可以在你修改 HTML/CSS/JavaScript 文件时自动刷新浏览器，非常适合快速开发和调试静态网站。

## 2. 安装 `live-server`

**步骤：**

1. 确保已经安装了 Node.js 和 npm。可以通过以下命令检查：

   ```bash
   node -v
   npm -v
   ```

2. 使用 npm 全局安装 `live-server`：

   ```bash
   npm install -g live-server
   ```

3. 安装完成后，检查 `live-server` 是否安装成功：

   ```bash
   live-server --version
   ```

   如果出现版本号，说明安装成功。

**注意事项：**

- 如果在安装过程中遇到权限问题，可以尝试以管理员身份运行命令提示符或 PowerShell。
- 如果在 Windows 上遇到 `EPERM` 错误或其他与权限相关的问题，可能需要检查系统文件夹的权限设置。

## 3. 使用 `live-server`

**基本用法：**

1. 打开命令行工具（如 Git Bash 或命令提示符或 PowerShell），导航到你的网站项目目录：

   ```bash
   cd path/to/your/project
   ```

2. 在项目根目录运行 `live-server`：

   ```bash
   live-server
   ```

3. 这将启动一个本地服务器，默认情况下在 `http://127.0.0.1:8080/` 打开你的项目，浏览器会自动加载这个地址。

**示例：**

假设你在 `C:\MyWebsite` 目录中有一个简单的 HTML 项目，你可以执行以下步骤：

```bash
cd C:\MyWebsite
live-server
```

浏览器将自动打开，并且你对项目文件的任何修改都会触发自动刷新。

## 4. 遇到的问题及解决方案

**问题 1：PowerShell 执行策略阻止了 `live-server` 的运行**

- 错误信息：

  ```powershell
  live-server : 无法加载文件 E:\installApp\program\nodejs\node_global\live-server.ps1，因为在此系统上禁止运行脚本。
  ```

- **解决方法：**

  1. 打开 PowerShell 并以管理员身份运行。
  2. 运行以下命令更改执行策略：

     ```powershell
     Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
     ```

  3. 重新运行 `live-server`。

- 注意：可以选择不修改 PowerShell 的执行策略，而改为在 Git Bash 下运行命令，就没有问题，你可以直接继续使用 Bash 来运行命令。因为 Bash 的执行策略与 PowerShell 不同，更加开放。

## 5. **常用配置**

- **指定端口：** 你可以通过 `--port` 参数指定 `live-server` 使用的端口，例如：

  ```bash
  live-server --port=8080
  ```

- **指定启动文件：** 如果你想指定一个特定的文件作为入口，可以使用 `--entry-file` 参数：

  ```bash
  live-server --entry-file=index.html
  ```

- 要查看 `live-server` 的常见配置参数，可以使用以下命令：

  ```bash
  live-server --help
  ```

  通过 `live-server --help`，你可以获取到所有的可选参数，并了解它们的用途。这是了解和使用 `live-server` 配置的最佳途径。

- 终止服务器：`ctrl + c`

## 6. 参考链接

- [live-server GitHub 仓库](https://github.com/tapio/live-server)
