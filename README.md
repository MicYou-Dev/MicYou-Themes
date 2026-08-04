# MicYou Themes

MicYou 的主题目录与主题包仓库。

## 仓库结构

```text
/
├── index.json                 # 收录所有主题
└── theme/
    └── <theme-id>/
        ├── manifest.json      # 主题元数据
        ├── theme.css          # 主题样式
        ├── preview.png        # 可选预览图
        └── theme.ts           # 可选脚本，当前不执行
```

根目录 `index.json` 收录主题清单。每个主题目录至少包含 `manifest.json` 和 CSS 入口文件；预览图和 TypeScript 脚本是可选的。

## 当前主题

- `default-blue`：MicYou 默认蓝色主题，包含浅色和深色 Material 3 变量。

## 安全说明

当前 MicYou 桌面端不会联网读取、下载或执行主题商城内容。未来如果支持包含 TypeScript 的主题包，启用前必须经过用户明确确认。
