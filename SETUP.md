# GitHub Profile 维护

更新于 2026-11-07。仓库：`l1jiahao/l1jiahao`（公开）。

## 当前展示

- 终端风格简介、研究方向、技术栈、SAVE Selected Work、贡献蛇动画。
- SAVE 已置顶到个人页；仓库是 `fdu-wangfeilab/sc-save`。
- 移除返回 HTTP 503 的第三方统计卡；streak 卡未启用。
- Skim 侧边栏已停止维护，按本人要求从当前项目和研究展示中移除。
- `fudan university`、`Shanghai-CN` 已由本人确认。
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

- 研究成果更新 `README.md` 中的 Selected Work，并优先链接组织内已公开的项目。
- 个人版 `sc-save` 是私有开发仓库，不需要为展示再次公开。
- 如果以后出现坏图，先运行 `--check`；第三方图片服务的错误可能是暂时的。
- 私有贡献显示设置位于 GitHub Profile → Contributions & Activity。
