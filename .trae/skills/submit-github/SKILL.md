---
name: 提交到 GitHub
description: 使用 git commit 将整个项目提交并推送到 GitHub 远程仓库 (https://github.com/xxy27/xxy_Gw.git)，SSH 公钥已配置。当用户要求"提交到 GitHub"、"push 到 GitHub"、"同步到 GitHub"时使用此 skill。
---

## 目标

将当前项目（`D:\AI Web`）的所有变更提交并推送到 GitHub 远程仓库：

```
https://github.com/xxy27/xxy_Gw.git
```

SSH 公钥已设置，推送统一使用 SSH 地址（避免交互式输入凭据）：

```
git@github.com:xxy27/xxy_Gw.git
```

## 远程命名约定

- `origin` 固定指向 Gitee（https://gitee.com/xu-xinyu05/gw927xxy.git），**不要改动**。
- GitHub 使用独立远程名 `github`，两仓库互不影响，可分别推送。

## 工作流程

1. **查看变更**
   运行 `git status --short` 和 `git diff --stat` 了解当前未提交的变更。

2. **暂存文件**
   使用 `git add -A` 暂存所有变更（包括新文件、修改、删除）。

3. **创建提交**
   根据变更内容生成一条简洁的中文提交信息，然后执行：
   ```
   git commit -m "<提交信息>"
   ```
   提交信息应概括本次变更（例如 `添加 1026-1 数七游戏页面`）。

4. **确认远程仓库**
   运行 `git remote -v` 检查是否已配置 `github` 远程：
   - 若没有 `github` 远程，执行：
     ```
     git remote add github git@github.com:xxy27/xxy_Gw.git
     ```
   - 若 `github` 已存在但指向其他地址，执行：
     ```
     git remote set-url github git@github.com:xxy27/xxy_Gw.git
     ```
   - 注意：PowerShell 5 不支持 `&&`，多命令用 `;` 分隔。

5. **推送到远程**
   首次推送使用 `-u` 建立跟踪关系：
   ```
   git push -u github master
   ```
   之后远程已有该分支时直接 `git push github`。

6. **验证**
   推送成功后运行 `git status` 确认工作区干净，并向用户报告提交哈希（`git log --oneline -1`）与推送结果。

## 注意事项

- 推送属于敏感操作，执行 `git push` 前先确认提交信息与暂存内容无误。
- 若推送因 SSH 认证或网络失败，可运行 `ssh -T git@github.com` 检查连通性，并如实报告错误，不要伪造成功。
- 不要修改 `AGENTS.md`、`xu_prompt.md` 等项目约定文件，除非用户明确要求。
- 不要动 `origin`（Gitee）的配置；如用户同时要求同步到 Gitee，调用 `submit-project` skill。
