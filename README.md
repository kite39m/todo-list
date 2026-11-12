# 今日待办清单

一个以收集箱为默认任务列表的单页应用，采用 Warm Canvas 暖色画布风格。登录后可以查看全部任务，并添加、完成或删除。

## 本地打开

克隆仓库后，在项目根目录启动一个本地静态服务（不建议直接用 `file://` 打开，以免登录和云端请求受阻）：

```bash
python -m http.server 8080
```

浏览器访问 [http://localhost:8080/](http://localhost:8080/) 即可打开应用。

## 登录方式

使用手机号加短信验证码登录或注册，两者是同一个入口。输入 11 位手机号，点击「获取验证码」，收到验证码后再点「登录 / 注册」。已登录时刷新页面会尝试恢复会话。

## 云端依赖

任务数据和登录都依赖 [WorkBuddy Cloud](https://www.workbuddy.cn/)，前端通过官方 SDK 连接云端应用。

- 登录：短信验证码（OTP）
- 数据：云数据库表 `todos`（字段包括 `id`、`title`、`done`、`created_at`、`date`）
- `date` 为可空日期字段，当前仅保留在数据结构层；新任务不设置该字段（保存为 `NULL`），界面不展示、不使用，也不按日期筛选
- 使用本应用需要该云端应用和数据表已就绪，并保持网络畅通

连接地址和公钥写在 `index.html` 中。

## 设计系统

Warm Canvas 设计系统说明页在 [`design-system/design-system.html`](design-system/design-system.html)。本地启动服务后，访问 [http://localhost:8080/design-system/design-system.html](http://localhost:8080/design-system/design-system.html) 即可查看颜色、字体、间距和组件规范。
