# 协作约定

## 分支与 PR

- `main` 是主干分支。任何改动先从 `main` 开新分支，在分支上提交并推送。
- 完成后向 `main` 提 PR，**不直接 commit 或 push 到 `main`**。
- PR 描述按仓库的 PR 模板写清四项：目的、影响范围、关键逻辑、验证步骤。
- PR 默认只提交审阅链接，由仓库维护者确认后再合并，**不自动合并**。

## 代码注释

- 只在**核心变化**和**容易误解**的地方加注释。
- 不把 PR 描述里的说明复述或抄进代码注释。

## 项目结构与改动注意

- `index.html`：单文件应用（云服务 SDK 走 CDN），不要拆出外部 CSS 依赖。
- `index.html` 含 49 个 `data-page-node-id`，是可视化编辑器节点标识，改样式时务必保留。
- `design-system/design-system.html`：Warm Canvas 设计系统的渲染/参考页；改样式时引用 `:root` 中的令牌，不写内联色值。
- Warm Canvas 规范原文不在本仓库内，改动视觉样式时请对照规范原文。
- 本地运行方式见 [README.md](README.md)。

## 本地认证

- 推荐 SSH：`git@github.com:kite39m/todo-list.git`。
- 也可用 HTTPS + Git 凭据管理器；不要在项目内保存访问令牌。
