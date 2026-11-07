# GitHub Profile 维护

更新于 2026-11-07。仓库：`l1jiahao/l1jiahao`（公开）。

## 当前展示

- 简洁研究简介、当前工作、SAVE / stDiff 代表作、教育背景；贡献蛇动画折叠展示。
- 与网站统一使用论文署名 Jiahao Li，移除打字动画、访问计数和技术栈徽章，使当前方向和成果优先显示。
- 当前研究为 WAM 记忆与原生长程训练，已有代码实验和初步结果，尚无正式论文；按本人于 11 月 7 日提供的信息呈现。硕士研究突出 diffusion models / flow matching 经验，本科研究简述为过往经历。
- SAVE 已置顶到个人页；仓库是 `fdu-wangfeilab/sc-save`。
- 移除返回 HTTP 503 的第三方统计卡；streak 卡未启用。
- Skim 侧边栏已停止维护，按本人要求从当前项目和研究展示中移除。
- 复旦硕士经历、`Shanghai-CN` 已由本人确认；复旦以教育经历呈现，不用作当前单位标签。
- 私有贡献显示此前已开启；私人仓库的内容不会因此公开。

## 发布

从管理工作区运行：

```bash
./publish-profile.sh --check
./publish-profile.sh
```

发布脚本要求 profile 是独立仓库、位于 main、origin 指向正确仓库、暂存区为空。
它先 fetch 并检查远端是否领先，只暂存 README、SETUP 和 snake workflow；提交或推送失败立即退出。
其他文件不会被自动加入提交。脚本兼容 macOS 自带 Bash 3.2。

## 贡献蛇动画

`.github/workflows/snake.yml` 在 main 推送、手动触发和每 12 小时的计划任务中运行；
有 concurrency 防止争抢 output 分支。GitHub 的计划任务可能延迟，不保证准点执行。

生成地址：
- `https://raw.githubusercontent.com/l1jiahao/l1jiahao/output/snake-dark.svg`
- `https://raw.githubusercontent.com/l1jiahao/l1jiahao/output/snake-light.svg`

检查运行：`gh run list -R l1jiahao/l1jiahao --workflow snake.yml --limit 3`。

## 内容维护

- 过往研究成果更新 `README.md` 中的 Selected Work，并优先链接组织内已公开的项目；当前研究更新 Current Research。
- 个人版 `sc-save` 是私有开发仓库，不需要为展示再次公开。
- 如果以后出现坏图，先运行 `--check`；第三方图片服务的错误可能是暂时的。
- 私有贡献显示设置位于 GitHub Profile → Contributions & Activity。
