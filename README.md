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

主题清单中的 `controlsThemeColor` 用于声明主题是否接管 MicYou 的主题色生成器：

- `true` 或未填写：主题 CSS 可以接管主题色设置。
- `false`：主题只调整布局、形状等视觉细节，应用继续使用系统/预置主题色。

## 当前主题

- `default-blue`：MicYou 默认蓝色主题，包含浅色和深色 Material 3 变量。
- `square-corners`：实验性直角界面主题，只调整形状，不接管主题色。

## 安全说明

当前 MicYou 桌面端不会联网执行主题 TypeScript。安装主题时只下载清单和 CSS，CSS 会在独立的主题包样式节点中应用；未来如果支持包含 TypeScript 的主题包，启用前必须经过用户明确确认。
