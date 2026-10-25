# SideNote 个人 fork

[English](README.md) | 简体中文

这是 [huaqian0226/side-note](https://github.com/huaqian0226/side-note)，基于
[mofukuru/side-note](https://github.com/mofukuru/side-note) 的 `23d0571` 提交。
保留原作者与 MIT 许可证；这是个人维护版本。

## 本次改进

`1.3.0-hq.1` 修复含已渲染表格的笔记打开时，插件初始化失败的问题：批注管理器创建后才刷新高亮。
新增回归测试分别覆盖没有批注和已有批注的数据。本版没有添加浮动工具栏，也没有改变批注格式。

## 安装与更新

1. 先备份现有 SideNote 插件目录，尤其是设置和批注数据。
2. 在 Obsidian 中打开 BRAT 设置，选择 Add beta plugin。
3. 输入 `huaqian0226/side-note`，选择最新 Release，安装并启用。
4. 后续通过 BRAT 更新这个 fork；社区市场中的原版会替换个人构建。

[Release 与安装文件](https://github.com/huaqian0226/side-note/releases)包含 `main.js`、`manifest.json` 和 `styles.css`。
保留插件 ID `side-note`，沿用原有批注数据，不需要额外启动第二个同名插件。

## 原版能力

- 对选中文字或整篇笔记添加批注，在侧栏或分屏查看。
- 跳转原文、编辑批注、设置颜色、搜索和标记解决／重新打开。
- 编辑时跟随选区位置，并处理原文删除后的孤立批注。
- 新批注和设置保存在库配置目录下的 `plugins/side-note/data.json`。
  Agent 需要显式读取该入口，并按文件和批注 ID 操作；只读正文会漏掉批注。
- 桌面与移动端支持；本 fork 的本轮运行验证只覆盖桌面。

完整的原版说明和历史见 [English README](README.md)。

## 开发方式

`main` 跟随上游，`my-features` 集成本人的自用改动。针对上游的修复保留独立提交，
从上游基线另开短分支，不携带个人版本号与安装文档。源码、测试、个人维护文档和发布版本分开记录。

```sh
npm ci
npm test
npx eslint src --ext .ts
npm run build
node --check main.js
```

修改 TypeScript 源码后重新构建，不能直接修改生成的 `main.js`。
Node 生命周期测试验证初始化顺序；显示和交互仍要在 Obsidian 中验证。
