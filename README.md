# 为什么需要这个 Tap？

有时候我们需要使用特定版本的应用程序，而官方 Homebrew Cask 只提供最新版本。这个 Tap 专门收集和维护这些特定版本的应用程序，方便通过 Homebrew 进行安装和管理。

## 快速开始

### 1. 添加 Tap

```bash
brew tap ts-env/versions
```

### 2. 安装应用

添加 Tap 后，可以直接使用短名称安装：

```bash
# 推荐：使用短名称（添加 Tap 后）
brew install --cask alfred@3
brew install --cask typora@free

# 也可以使用完整名称（不需要先添加 Tap）
brew install --cask ts-env/versions/alfred@3
brew install --cask ts-env/versions/typora@free
```

## 卸载应用

```bash
brew uninstall --cask alfred@3
```

### 查看已安装的应用

```bash
brew list --cask
```

### 搜索可用版本

```bash
brew search typora
# 会显示: ts-env/versions/typora@free

brew search alfred
# 会显示: ts-env/versions/alfred@3
```

## 贡献

欢迎提交 Pull Request 来添加更多的应用版本！

### 添加新的 Cask 步骤

1. 在 `Casks/` 目录下创建新的 `.rb` 文件
2. 按照 Homebrew Cask 规范编写 cask 定义
3. 运行测试确保符合规范：

```bash
# 检查代码风格
brew style Casks/<cask-name>.rb

# 检查 cask 正确性
brew audit --cask ts-env/versions/<cask-name>
```

4. 提交 Pull Request

### Cask 命名规范

- 使用 `@` 符号分隔应用名称和版本号
- 版本号使用点分隔（如 `3.8.6`）
- 全部使用小写字母
- 示例：`alfred@3.rb`、`typora@free.rb`

## 测试

本项目使用 GitHub Actions 自动运行测试。每次提交和 Pull Request 都会触发：

- 代码风格检查（`brew style`）
- Cask 正确性检查（`brew audit`）
- 语法检查（`brew test-bot`）

## 许可证

本项目中的 Cask 定义文件遵循 Homebrew 的许可证。各应用程序本身的许可证请参考其官方网站。

## 维护者

- [@ts-env](https://github.com/ts-env)

## 相关链接

- [Homebrew 官方网站](https://brew.sh/)
- [Homebrew Cask 文档](https://docs.brew.sh/Cask-Cookbook)
- [如何创建 Homebrew Tap](https://docs.brew.sh/How-to-Create-and-Maintain-a-Tap)
