---
name: 提交项目
description: 使用 git commit 将当前项目提交并推送到 Gitee 远程仓库 (https://gitee.com/xu-xinyu05/gw927xxy.git)
---

## 目标

将当前项目（`D:\AI Web`）的所有变更提交并推送到 Gitee 远程仓库：

```
https://gitee.com/xu-xinyu05/gw927xxy.git
```

## 工作流程

1. **查看变更**
   运行 `git status --short` 和 `git diff --stat` 了解当前未提交的变更。若分支还没有任何提交（`git log` 报错），说明这是首次提交。

2. **暂存文件**
   使用 `git add -A` 暂存所有变更（包括新文件、修改、删除）。

3. **创建提交**
   根据变更内容生成一条简洁的中文提交信息，然后执行：
   ```
   git commit -m "<提交信息>"
   ```
   提交信息应概括本次变更（例如 `添加 1012 练习页面`、`更新 index 导航与样式`）。

4. **确认远程仓库**
   运行 `git remote -v` 检查是否已配置远程：
   - 若没有任何远程，执行：
     ```
     git remote add origin https://gitee.com/xu-xinyu05/gw927xxy.git
     ```
   - 若 `origin` 指向其他地址，执行：
     ```
     git remote set-url origin https://gitee.com/xu-xinyu05/gw927xxy.git
     ```

5. **推送到远程**
   首次推送时使用 `-u` 建立跟踪关系：
   ```
   git push -u origin master
   ```
   若之后远程已有该分支，则直接 `git push`。

6. **验证**
   推送成功后运行 `git status` 确认工作区干净，并向用户报告提交哈希（`git log --oneline -1`）与推送结果。

## 注意事项

- 推送属于敏感操作，执行 `git push` 前先确认提交信息与暂存内容无误。
- 若 `git push` 因权限或网络失败，如实报告错误，不要伪造成功。
- 不要修改 `AGENTS.md`、`xu_prompt.md` 等项目约定文件，除非用户明确要求。
