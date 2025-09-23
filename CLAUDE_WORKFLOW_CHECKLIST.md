# ✅ Claude GitHub 工作流操作顺序 Checklist

本清单配合流程图使用，帮助你在 GitHub 上通过 Issues → Claude → PR → Actions → Merge → Code → Insights 完成完整闭环。

---

## 一次性配置（仅需一次）
- [x] 安装并登录 GitHub CLI (`gh auth status` 显示已登录)  
- [x] 安装 Claude GitHub App，并赋予目标仓库权限  
- [x] 合并 Claude 自动生成的 PR，确认 `.github/workflows/` 下存在 workflow 文件  
- [x] 仓库 → **Settings → Actions → General**  
  - 打开 **Allow all actions**  
  - 打开 **Read and write permissions**

---

## 每次派活流程

### 1. 提需求 (Issues)
- [ ] 打开仓库 → **Issues → New issue**  
- [ ] 填写 **Title**（任务简述，例如 `Feat: 添加 hello.py`）  
- [ ] 在 **Description** 中写清楚需求和验收标准，并 **@claude**  
- [ ] 提交 Issue  

### 2. 触发 Claude 执行
- [ ] 在 Issue 下追加评论：  
@claude 请开始执行

- [ ] 等 Claude 在评论区回复，并自动创建分支 + PR  

### 3. 审查 PR (Pull requests)
- [ ] 打开 **Pull requests** → 查看 Claude 创建的 PR  
- [ ] 阅读 Claude 的自评审意见 + diff  
- [ ] 若需修改，在 PR 评论区再次 @claude 调整  
- [ ] 满意后点击 **Merge pull request → Confirm merge**  

### 4. 验证 Actions
- [ ] 打开 **Actions** → 确认 Claude 工作流运行成功并通过  

### 5. 本地同步
- [ ] 在本地仓库目录执行：  
```bash
git pull origin main
```
- [ ] 确认新代码已同步到本地


### 6. 本地同步 复盘与跟进 (Insights)


 - [ ] 打开 Insights → Pulse / Contributors 查看近期 PR、Issue 活跃度

 - [ ] 总结 Claude 的产出质量和本次任务效率

### 注意事项

- Claude 必须在 Issue/评论里被 @claude 提及，才会触发。

- Workflow 失败 → 去 Actions 查看日志，通常是权限或 token 配置问题。

- PR 必须 Merge 到主分支后，代码才会生效。

- 本地务必定期 git pull，保持远程与本地一致，避免冲突。
