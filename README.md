# MicYou Themes

MicYou 的主题目录与主题包仓库。

## 目录文件

仓库根目录的 `index.json` 是主题目录入口：

```json
{
  "version": 1,
  "themes": []
}
```

每个主题条目支持以下字段：

- `id`：主题唯一标识
- `name`：主题名称
- `version`：主题版本
- `author`：作者
- `description`：主题描述
- `preview`：预览图地址（可选）
- `entry`：主题入口文件（可选）
- `minAppVersion`：最低支持的 MicYou 版本（可选）
- `resourceUrl`：主题资源地址（可选）
- `hasScript`：是否包含脚本（可选）

## 安全说明

主题包未来可以包含 JSON 和 CSS。当前 MicYou 桌面端不会联网读取、下载或执行主题商城内容。

如果未来支持包含 TypeScript 的主题包，启用前必须经过用户明确确认。
