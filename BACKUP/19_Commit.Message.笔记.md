# [Commit Message 笔记](https://github.com/hadleysu/gitblog/issues/19)

# Commit Message 笔记

- [Commit Message 笔记](#commit-message-笔记)
  - [常用的 Commit Message 前缀及其含义](#常用的-commit-message-前缀及其含义)
  - [Commit Message 示例](#commit-message-示例)
  - [代码仓库链接](#代码仓库链接)
  - [补充学习](#补充学习)

## 常用的 Commit Message 前缀及其含义

在撰写 commit message 时，遵循统一的前缀可以帮助团队成员快速理解每次提交的类型。以下是一些常用的前缀及其解释：

1. **`Feat` (Feature)**  
   用于添加新功能。

   - 示例：`Feat: add user login functionality`

2. **`Fix` (Bug Fix)**  
   用于修复 bug。

   - 示例：`Fix: resolve issue with form validation not triggering`

3. **`Refactor` (Code Refactor)**  
   用于重构代码，既不修复 bug 也不添加功能，通常是提高代码质量或性能。

   - 示例：`Refactor: optimize database query logic`

4. **`Style` (Styling Changes)**  
   用于代码格式的调整，不影响功能（如代码缩进、空格、标点符号等）。

   - 示例：`Style: apply consistent indentation across all files`

5. **`Test` (Tests)**  
   用于添加、更新或修复测试代码。

   - 示例：`Test: add unit tests for user service`

6. **`Docs` (Documentation)**  
   用于文档的更新和修改。

   - 示例：`Docs: update README with API usage details`

7. **`Chore` (Maintenance)**  
   用于构建、工具配置等与业务逻辑无关的维护工作。

   - 示例：`Chore: update dependency versions in package.json`

8. **`Perf` (Performance Improvement)**  
   用于优化性能的代码提交。

   - 示例：`Perf: improve image loading speed by using lazy loading`

9. **`Revert` (Reverting Changes)**  
   用于回滚之前的提交。

   - 示例：`Revert: revert "Feat: add user login functionality"`

10. **`CI` (Continuous Integration)**  
    用于 CI 配置文件的修改。

    - 示例：`CI: update CI pipeline to run integration tests`

11. **`Build` (Build System)**  
    用于构建系统或外部依赖项的变更。

    - 示例：`Build: update webpack config to support SCSS`

12. **`Security` (Security Fixes)**  
    用于安全性相关的修复。
    - 示例：`Security: fix XSS vulnerability in user input`

## Commit Message 示例

这里是一个成熟的 commit 流程的完整示例，从项目创建到代码完善，展示如何规范写 commit message：

1. **初次提交**

   - **Commit Message**: `Init: initial project setup with basic folder structure`
   - 描述：初始化项目，创建基础目录结构，如 `src`, `index.html`, `style.css` 等。

2. **添加基础功能**

   - **Commit Message**: `Feat: implement user authentication`
   - 描述：实现用户登录、注册等基础功能。

3. **修复问题**

   - **Commit Message**: `Fix: resolve issue with form validation in login form`
   - 描述：修复表单验证中的 bug，确保用户不能提交不完整的表单。

4. **优化代码**

   - **Commit Message**: `Refactor: clean up authentication logic by extracting helper functions`
   - 描述：重构代码，将认证逻辑提取到辅助函数中，提升代码可读性。

5. **性能优化**

   - **Commit Message**: `Perf: improve page load speed by compressing images`
   - 描述：通过压缩图片提高页面加载速度。

6. **文档更新**

   - **Commit Message**: `Docs: update API documentation with latest endpoints`
   - 描述：更新 API 文档，添加最新的端点信息。

7. **测试更新**

   - **Commit Message**: `Test: add integration tests for user login`
   - 描述：为用户登录功能添加集成测试，确保各部分功能能正确协同工作。

8. **持续集成配置**
   - **Commit Message**: `CI: configure Travis CI for automated testing`
   - 描述：配置持续集成工具（如 Travis CI），自动化测试流程。

## 代码仓库链接

以下是一些著名开源项目的代码仓库链接，这些项目有很好的提交历史记录，可以参考其提交信息的写作方式：

1. [React (GitHub)](https://github.com/facebook/react/commits/main)
2. [Vue.js (GitHub)](https://github.com/vuejs/vue/commits/main)
3. [Node.js (GitHub)](https://github.com/nodejs/node/commits/main)

## 补充学习

- [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/)
- [conventional-commits-cheatsheet.md](https://gist.github.com/qoomon/5dfcdf8eec66a051ecd85625518cfd13)
- [How to Write a Git Commit Message](https://cbea.ms/git-commit/)
- [Git Commit Msg](https://karma-runner.github.io/6.4/dev/git-commit-msg.html)
