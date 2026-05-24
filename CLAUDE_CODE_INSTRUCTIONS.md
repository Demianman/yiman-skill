# Claude Code 操作说明
# 把 yiman-skill 推到 GitHub

## 前提
- 已安装 git，已配置 GitHub 凭证（SSH key 或 HTTPS token）
- 已在 GitHub 上手动建好空仓库 `yiman-skill`（不要加 README/LICENSE，保持完全空）
  → 建仓库地址：https://github.com/new
  → 仓库名：yiman-skill
  → 建议 Public（这是要公开的 skill 包）
  → 不要勾选 "Add a README file"

## 操作步骤（复制给 Claude Code 执行）

```bash
# 1. 进入 skill 包目录
cd /mnt/user-data/outputs/yiman-skill

# 2. 确认文件结构（应该只有这几个文件）
ls -la
# 预期：.gitignore  CHANGELOG.md  LICENSE  README.md  SKILL.md

# 3. 初始化 git 仓库
git init
git branch -M main

# 4. 配置 git 用户信息（如果还没配过）
# git config user.name "Yiman Wu"
# git config user.email "你的邮箱"

# 5. 添加所有文件
git add .

# 6. 确认暂存区内容（检查没有多余文件）
git status

# 7. 第一次提交
git commit -m "feat: initial release of yiman-skill v1.0.0

Personality skill for Yiman Wu (吴宜蔓 / Nelly).
Distilled from public writing: application essays, graduation speech,
Weibo diaries, chat logs, anonymous Q&A, and a round of deep self-interview.

Includes: thinking OS, decision rules, voice-calibration spec,
bilingual few-shot examples (中文+EN), web-search protocol,
pre-output checklist."

# 8. 关联远程仓库（把 YOUR_USERNAME 换成你的 GitHub 用户名）
git remote add origin git@github.com:YOUR_USERNAME/yiman-skill.git
# 如果用 HTTPS：
# git remote add origin https://github.com/YOUR_USERNAME/yiman-skill.git

# 9. 推送
git push -u origin main
```

## 推完后检查

打开 https://github.com/YOUR_USERNAME/yiman-skill 确认：
- [ ] 仓库根目录只有：`.gitignore` `CHANGELOG.md` `LICENSE` `README.md` `SKILL.md`
- [ ] 没有出现：`人物分析报告.md` / `吴宜蔓素材库/` / `yiman-skill.md`（旧草稿）
- [ ] README 在仓库首页正常渲染
- [ ] SKILL.md 开头的 YAML frontmatter（`---` 到 `---`）完整显示

## 如果要用 SSH 但还没配 key

```bash
# 生成 SSH key
ssh-keygen -t ed25519 -C "你的邮箱"
# 把 ~/.ssh/id_ed25519.pub 的内容加到 GitHub Settings → SSH keys
# 测试连接
ssh -T git@github.com
```

## 后续更新 skill 时

```bash
cd /mnt/user-data/outputs/yiman-skill
# 编辑 SKILL.md 和 CHANGELOG.md 后：
git add SKILL.md CHANGELOG.md
git commit -m "fix: 描述你改了什么"
git push
```
