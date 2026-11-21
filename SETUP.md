# GitHub Profile 维护

更新于 2026-11-21。仓库：`l1jiahao/l1jiahao`（公开）。

## 当前展示

- 采用**深空青绿科技风**（Deep-Space Emerald Lab）视觉设计，双主题自适应 GitHub 深色 / 浅色模式：
  - `assets/hero-dark.svg` / `assets/hero-light.svg`：顶部定制 Hero Banner（工程网格 + 长程记忆轨迹示意图 + 研究标签）。
  - `assets/research-map-dark.svg` / `assets/research-map-light.svg`：生成模型底座 → 具身智能 WAM 的能力迁移与研究阶段图谱。
  - `assets/cover-save.png` / `assets/cover-stdiff.png`：Selected Work 左图右文卡片方法缩略图（复用自学术主页已核验封面）。
- 仅使用仓库内静态 SVG 与统一配色 `shields.io` `flat-square` 徽章，不依赖不稳定第三方统计卡（如 `github-readme-stats` / `capsule-render`）。
- 保留终端速览块、分领域 Tech Stack 徽章表，以及底部直接展开的贡献蛇动画。
- 当前研究为 WAM 记忆与原生长程训练，已有代码实验和初步结果，尚无正式论文；结合 simulation、robotics benchmarks 与 RL post-training 开展验证。硕士研究突出 Latent VAE、OT Flow Matching、Diffusion Models、DiT 与 CFG 经验，本科及学历保留为背景。
- SAVE 已置顶到个人页；仓库是 `fdu-wangfeilab/sc-save`，README 附 OpenReview、arXiv 与 Code 链接；stDiff 链接 `fdu-wangfeilab/stDiff`。
- GitHub 个人资料栏（`https://github.com/settings/profile`）建议统一为：`Jiahao Li`、具身智能与 WAM 简介、`https://l1jiahao.github.io`、`Shanghai, China`（因当前 `gh` token 无 `user` scope，需在网页设置或刷新 scope 后更新）。
- 私有贡献显示此前已开启；私人仓库的内容不会因此公开。

## 发布

从管理工作区运行：

```bash
./publish-profile.sh --check
./publish-profile.sh
```

发布脚本要求 profile 是独立仓库、位于 main、origin 指向正确仓库、暂存区为空。
它先 fetch 并检查远端是否领先，自动暂存 README、SETUP、snake workflow 及 `assets/`；提交或推送失败立即退出。
其他文件不会被自动加入提交。脚本兼容 macOS 自带 Bash 3.2。

## 贡献蛇动画

`.github/workflows/snake.yml` 在 main 推送、手动触发和每 12 小时的计划任务中运行；
当前使用 `#58A6FF`（深色）与默认浅色配色，有 concurrency 防止争抢 output 分支（若需调整 workflow 文件中的蛇色，需在 GitHub 网页直接编辑或为 token 补充 `workflow` scope 后推送）。GitHub 的计划任务可能延迟，不保证准点执行。

生成地址：
- `https://raw.githubusercontent.com/l1jiahao/l1jiahao/output/snake-dark.svg`
- `https://raw.githubusercontent.com/l1jiahao/l1jiahao/output/snake-light.svg`

检查运行：`gh run list -R l1jiahao/l1jiahao --workflow snake.yml --limit 3`。

## 内容维护

- 过往研究成果更新 `README.md` 中的 Selected Work，并优先链接组织内已公开的项目；当前研究同步更新 Hero / Research Map SVG。
- 个人版 `sc-save` 是私有开发仓库，不需要为展示再次公开。
- 如果以后出现坏图，先运行 `--check`；第三方图片服务的错误可能是暂时的。
- 私有贡献显示设置位于 GitHub Profile → Contributions & Activity。
