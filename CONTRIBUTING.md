# 贡献指南 (Contributing)

本仓库是一个个人主页仓库：一份 README、一张会动的 SVG 名片、一个每天刷新名片数字的工作流，以及一份部署在 GitHub Pages 上的单页。

这里没有可构建的代码，也没有可修改的程序。

## 最有用的贡献

页面上的数字不对、链接打不开、某个结论经不起复核 —— 请开 issue。这是这里最需要的贡献。

`stats/` 里的数字由 GitHub Actions 每天从 GitHub API 重新生成，`profile-anim.svg` 里五个 `<text id="stat-*">` 的值由同一份数据写入。正文与它们矛盾，就是正文的 bug。

## 提交

仓库里唯一的自动提交来自 `github-actions[bot]`。

如果你确实要提 PR：每个提交都需要 `Signed-off-by`（`git commit -s`），否则 `.github/workflows/dco.yml` 会失败。没有 CLA。

## 许可证

本仓库没有许可证文件。

#5 曾引入 AGPLv3 与 DCO，#6 随后移除了许可证文件与展示，但这份指南里的 AGPLv3 段落一直留到现在 —— 那是遗留，不是现行条款。现在按默认版权处理：想复用这里的任何内容，先开 issue 谈。
