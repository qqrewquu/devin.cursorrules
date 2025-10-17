# 附录 B：Git 工作流参考

> 供 Codex 或团队成员在需要时查阅。日常操作仍以 `AGENTS.md` 中的执行看板为准。

## 初始设置
1. 查看仓库状态：`git status`
   - 若尚未初始化：`git init`
   - 检查远程：`git remote -v`
2. 首次推送（示例）：
   ```bash
   git remote add origin https://github.com/username/repo.git
   git add .
   git commit -m "[Codex] Initial commit - Project setup"
   git push -u origin main
   ```

## 日常循环
1. 完成子任务后：
   ```bash
   git status
   git add .
   git commit -m "[Codex] Step X.Y: 简述本次改动"
   git push
   ```
2. 提交信息建议包含：
   - `[Codex]` 前缀，标记 AI 协助。
   - 步骤编号或里程碑。
   - 1 句话说明功能或修复。
3. 需要多行提交说明时：
   ```bash
   cat > commit_msg.txt <<'EOF'
   [Codex] Step 2: Major feature implementation

   - Added feature X
   - Updated feature Y
   - Fixed issue Z
   EOF

   git commit -F commit_msg.txt
   rm commit_msg.txt
   ```

## 版本控制最佳实践
- 保持 `main` 稳定，重大功能使用分支开发。
- 重大改动前确认已提交；协作时先 `git pull`。
- 回滚示例：
  ```bash
  git log --oneline
  git reset --hard <commit-hash>      # 强制回滚
  git revert <commit-hash>            # 生成反向提交
  ```
- Executor 在更新执行看板前，务必记录最新 commit 哈希与时间，保持可追踪性。
