# FloatCTF - 开源 CTF 比赛平台

这是一个开源的 CTF (Capture The Flag) 比赛平台，支持团队赛和个人赛模式。

# 开发流程

本项目包含前端（React/Vite）和后端（Rust/Actix）两部分。

## 1. 安装依赖

在项目根目录运行以下命令安装所有必要的依赖：

```bash
pnpm install
```

## 2. 运行开发服务器

同时启动前端和后端开发服务器：

```bash
pnpm dev
```

*   `pnpm run frontend-dev`: 启动前端 Vite 开发服务器，通常在 `http://localhost:3000` 运行。
*   `pnpm run backend-dev`: 启动后端 Actix 服务器，并使用 `cargo watch` 监控 `src-actix/` 目录下的文件变化，自动重新编译和运行。

## 3. 构建项目

为生产环境构建前端应用：

```bash
pnpm build
```

此命令会使用 Vite 构建前端代码并进行 TypeScript 类型检查。

## 4. 运行测试

运行项目中的所有测试：

```bash
pnpm test
```

本项目使用 Vitest 进行测试。

## 5. 代码格式化与检查

使用 Biome 工具进行代码格式化和检查：

*   **格式化代码：**
    ```bash
    pnpm format
    ```
*   **检查代码风格和潜在问题：**
    ```bash
    pnpm lint
    ```
*   **同时进行格式化和检查：**
    ```bash
    pnpm check
    ```

# 协作开发 (GitHub)

本项目鼓励通过 GitHub 进行协作开发。请遵循以下流程贡献代码：

## 1. 派生 (Fork) 仓库

首先，将本项目的仓库派生到您的 GitHub 账户。点击 GitHub 页面右上角的 "Fork" 按钮。

## 2. 克隆 (Clone) 派生仓库

将您派生出的仓库克隆到本地机器：

```bash
git clone https://github.com/您的用户名/FloatCTF.git
cd FloatCTF
```

## 3. 添加上游 (Upstream) 仓库

为了保持与原始仓库的同步，请添加原始仓库为“上游”：

```bash
git remote add upstream https://github.com/原始仓库所有者/FloatCTF.git
```
（请将 `原始仓库所有者` 替换为实际的原始仓库所有者，例如 `FloatCTF`）

## 4. 创建新分支

在开始开发新功能或修复 Bug 之前，请从 `main` 分支创建一个新的特性分支：

```bash
git checkout main
git pull upstream main # 确保本地 main 分支是最新的
git checkout -b feature/your-feature-name # 创建并切换到新分支
```

## 5. 进行更改

在新分支上进行您的代码更改。

## 6. 提交更改

提交您的更改，并编写清晰的提交信息：

```bash
git add .
git commit -m "feat: 添加新功能" # 或 "fix: 修复某个Bug"
```

### 提交规范

本项目遵循 [Conventional Commits](https://www.conventionalcommits.org/zh-hans/v1.0.0/) 规范，以保持提交历史的清晰和可追溯性。提交信息应遵循以下格式：

```
<type>(optional scope): <description>

[optional body]

[optional footer(s)]
```

**范围 (scope) (可选)：**

范围表示本次提交影响的特定部分，例如 `feat(auth)` 表示认证模块的新功能，`fix(frontend)` 表示前端的 Bug 修复。范围应简洁明了，通常用小括号 `()` 包裹。

**类型 (type) 示例：**

*   `feat`: 新功能 (a new feature)
*   `fix`: Bug 修复 (a bug fix)
*   `docs`: 文档变更 (documentation only changes)
*   `style`: 不影响代码含义的更改 (whitespace, formatting, missing semicolons, etc.)
*   `refactor`: 代码重构 (refactoring production code)
*   `perf`: 性能优化 (a code change that improves performance)
*   `test`: 添加缺失的测试或纠正现有测试 (adding missing tests or correcting existing tests)
*   `build`: 影响构建系统或外部依赖的更改 (e.g. gulp, broccoli, npm)
*   `ci`: 更改 CI 配置文件和脚本 (e.g. Travis, Circle, BrowserStack, SauceLabs)
*   `chore`: 其他不修改 src 或 test 文件的更改 (e.g. build process, auxiliary tools, and libraries)
*   `revert`: 回滚之前的提交 (reverts a previous commit)

**描述 (description)：**

*   简明扼要地描述本次提交的主要内容。
*   使用祈使句，现在时态：“添加功能”而不是“添加了功能”。
*   首字母小写。
*   不以句号结尾。

**示例：**

```
feat(auth): 添加用户登录功能

此提交引入了用户登录功能，包括前端表单和后端认证逻辑。
解决了 #123 问题。
```

## 7. 推送更改

将您的本地分支推送到您派生出的 GitHub 仓库：

```bash
git push origin feature/your-feature-name
```

## 8. 创建拉取请求 (Pull Request)

在您的 GitHub 派生仓库页面，您会看到一个提示，引导您创建拉取请求。点击该提示，或手动导航到原始仓库的 "Pull requests" 页面，然后点击 "New pull request"。

请确保您的拉取请求描述清晰，说明您所做的更改、解决的问题或实现的功能。

