# Profile README 上线步骤

## 1. 建立 profile 仓库

仓库名必须**完全等于**用户名：`l1jiahao/l1jiahao`，且必须是 **public**。

```bash
cd ~/Code/github_manager
./publish-profile.sh
```

## 2. 打开私有贡献显示（关键）

当前你有 13 个私有仓库、0 个公开仓库。如果不开这个开关，贡献图全空、stats 卡片几乎为 0。

> https://github.com/settings/profile → **Contributions & Activity**
> 勾选 **"Include private contributions on my profile"**

效果：贡献热力图有真实数据，别人看到"有活动"，但看不到任何私有代码、仓库名或提交信息。
这是绝大多数在公司/实验室做私有项目的开发者的标准做法。

## 3. 触发 snake 动画

`.github/workflows/snake.yml` 已在仓库内。首次需手动跑一次：

> 仓库 → Actions → **Generate Snake** → Run workflow

约 30 秒后生成 `output` 分支，README 里的 `<picture>` 才会显示。

> GitHub Actions 对新仓库可能有约 1 分钟的启用延迟；若 Actions 标签页提示需要启用，点一下 Enable 即可。

## 4. 需要替换的占位内容

| 位置 | 当前值 | 说明 |
|---|---|---|
| badge `followers` | 动态拉取 | 自动更新，无需维护 |
| badge `fudan university` | 按 org 推断 | 如果不对，删掉这行 |
| badge `Shanghai-CN` | 猜测 | 改成实际城市或删除 |
| `selected work` 表格 | 4 个项目 | 只写你愿意公开提的；都是 private 仓库，写描述不泄露代码 |
| 底部引言 | `"Reproduce it first, then you understand it."` | 换成你自己的一句话，或删掉 |

## 5. 验证渲染

```bash
# 所有图片端点是否 200
./publish-profile.sh --check
```

## 备选方案

如果哪天你觉得这套"卡片堆叠"太常见了，两个更克制的方向：

- **纯终端**：去掉所有 stats 卡片，只留 `console` 代码块 + skillicons，靠文字取胜。信息密度高，加载快，最像"资深工程师"。
- **内容驱动**（tw93 风格）：用 GitHub Action 定时把最新 release / RSS 文章注入 README 的标记区块，README 变成活的更新流。需要你有博客或持续发版。

当前这套是**中间态**：视觉有科技感，但读取成本仍然很低。
