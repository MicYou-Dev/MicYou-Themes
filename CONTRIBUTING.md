# 主题贡献指南

感谢你为 MicYou 贡献主题！主题贡献只需要提交主题目录中的元数据、CSS 和可选预览图。

## 主题目录

在 `theme/` 下新建一个主题目录：

```text
theme/<directory-name>/
├── manifest.json
├── theme.css
└── preview.png       # 可选，但建议提供
```

目录名建议使用小写 kebab-case。`manifest.json` 中的 `id` 必须在仓库内唯一，并建议保持稳定；发布后不要随意修改。

## manifest.json

最小示例：

```json
{
  "id": "my-theme",
  "name": "My Theme",
  "version": "0.1.0",
  "author": "Your Name",
  "description": "简短描述主题的视觉特点。",
  "entry": "theme.css",
  "preview": "preview.png",
  "minAppVersion": "2.0.0-alpha1",
  "controlsThemeColor": true
}
```

字段说明：

| 字段 | 必填 | 说明 |
| --- | --- | --- |
| `id` | 是 | 主题唯一标识，建议使用小写 kebab-case。 |
| `name` | 是 | 面向用户显示的主题名称。 |
| `version` | 是 | 主题版本号。 |
| `author` | 是 | 作者或组织名称。 |
| `description` | 是 | 简短的主题描述。 |
| `entry` | 是 | CSS 入口文件，必须位于主题目录内。 |
| `preview` | 否 | 预览图路径，文件必须位于主题目录内。 |
| `minAppVersion` | 否 | 主题要求的最低 MicYou 版本。 |
| `controlsThemeColor` | 否 | 是否接管主题色生成器，默认为 `true`；仅调整布局或形状时设为 `false`。 |
| `resourceUrl` | 否 | 不要手工填写，生成脚本会根据主题目录自动写入。 |

## CSS 约定

- 主题包只支持 CSS，不要提交 JavaScript、脚本或可执行代码。
- 尽量使用 MicYou 已有的 CSS 变量和 Material 3 变量，避免覆盖无关功能样式。
- 只调整布局、形状等视觉细节的主题应将 `controlsThemeColor` 设为 `false`。
- `entry` 指向的文件必须存在，CSS 语法应保持有效。

## 预览图

如果提供 `preview`，文件必须存在于主题目录内。README 会自动读取该文件并在当前主题表格中显示。

建议预览图清楚展示主题的主要界面，并避免包含个人信息或受版权保护的素材。

## 本地检查

在仓库根目录执行：

```sh
bun install
bun run format
bun run check
```

生成脚本会自动扫描所有主题，检查必填字段、重复 ID、入口 CSS 和预览图，并更新 `README.md` 与 `index.json`。不要手工编辑这两个生成文件；如需预览生成结果，可执行：

```sh
bun run generate
```

## 提交 Pull Request

提交 PR 前请确认：

- 主题目录只包含必要的主题资源。
- `manifest.json` 中的描述、版本和作者信息准确。
- `preview` 与 `entry` 路径均可用。
- `bun run check` 通过。
- PR 描述中说明主题的视觉变化，以及是否接管主题色。
