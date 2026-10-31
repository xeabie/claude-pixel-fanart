# Claude 像素风表情包

> **本分支是 `lite` 轻量版**：图片统一压到 512×512 / 256 色，仓库归档约 **2.6 MB**，适合国内网络安装。
> `main` 分支保留 1254px 原图（归档约 **17.8 MB**）。安装时把 `ref` 填成 `lite` 即可。

以**橙发桂花少女**（头饰桂花与流苏，黑白橙配色）为主角的像素风 Q 版表情包，共 **18 张**图片、**12 个分类**，适用于 AstrBot 表情包管理器（meme_manager）等支持「AstrBot 表情包规范」的应用。

- 包 ID：`claude-pixel-fanart`
- 版本：`1.0.0`
- 清单模式版本：`schema_version: 1`
- 图片格式：PNG（RGB，无透明通道）
- 分辨率：512×512（全部，256 色调色板）

## 目录结构

```text
claude-pixel-fanart/        ← 包根目录（即本仓库根目录）
  manifest.json             ← 包清单
  README.md                 ← 本说明（不属于表情资源）
  previews/
    cover.png               ← 封面与预览图（同时作为 icon）
  memes/
    angry/    angry-pout.png
    color/    hands-on-cheeks-heart-eyes.png
    confused/ puzzled-question.png
    fool/     smug-grin.png
    happy/    content-smile.png  happy-hearts.png  happy-wave.png
    like/     thumbs-up-wink.png  wink-heart.png
    meow/     cat-hug-smile.png  wink-cat-paw.png
    sad/      teary-upset.png
    shy/      shy-hopeful.png  starry-eyes-serving-tea.png
    sigh/     speechless-ellipsis.png
    surprised/ shocked.png  starry-eyed-wow.png
    work/     reading-book.png
```

`memes/<分类>/<图片>` 中的分类目录名与 `manifest.json` 的 `categories` 键完全一致；每个已声明的分类至少有一张图片。

## 分类与图片对照

| 分类 | 图片文件 | 表情含义 | 使用场景 |
| --- | --- | --- | --- |
| happy | `content-smile.png` | 满足眯眼笑 | 惬意、被照顾好、心情不错 |
| happy | `happy-wave.png` | 张口大笑挥手 | 问好、再见、开心打招呼 |
| happy | `happy-hearts.png` | 闭眼微笑＋爱心 | 幸福、治愈、暖到 |
| like | `thumbs-up-wink.png` | 眨眼竖大拇指 | 点赞、认可、干得漂亮 |
| like | `wink-heart.png` | 眨眼双手比心 | 比心、喜欢、感谢 |
| surprised | `starry-eyed-wow.png` | 星星眼张嘴 | 惊喜、哇哦、太棒了 |
| surprised | `shocked.png` | 头顶感叹号瞪眼 | 震惊、没想到、被打断 |
| confused | `puzzled-question.png` | 头顶问号侧头 | 疑问、不解、需要澄清 |
| sad | `teary-upset.png` | 泪眼汪汪撇嘴 | 委屈、想哭、可怜巴巴 |
| angry | `angry-pout.png` | 皱眉鼓脸带汗滴 | 轻度生气、抗议、傲娇 |
| sigh | `speechless-ellipsis.png` | 面无表情＋省略号 | 无语、无奈、轻微吐槽 |
| shy | `shy-hopeful.png` | 脸红双手合十抵嘴 | 害羞、期待、拜托 |
| shy | `starry-eyes-serving-tea.png` | 星星眼双手奉茶 | 讨好、殷勤、请多关照 |
| meow | `wink-cat-paw.png` | 眨眼举猫爪 | 卖萌、撒娇、打招呼 |
| meow | `cat-hug-smile.png` | 微笑抱白猫 | 撸猫、治愈、闲暇 |
| fool | `smug-grin.png` | 斜眼坏笑捂嘴 | 得意、小恶魔、恶作剧得逞 |
| work | `reading-book.png` | 双手捧书 | 学习、查阅资料、专注处理中 |
| color | `hands-on-cheeks-heart-eyes.png` | 双手托腮＋爱心眼 | 心动、花痴、暧昧互动 |

## 安装与使用

1. **打包上传**：把本目录（`manifest.json`、`memes/`、`previews/` 同级）整体放进公开 Git 仓库根目录，目录名不必等于包 ID。
2. **在 AstrBot 中安装**：WebUI → 插件 → 表情包管理器 → 资源广场，用「从 GitHub 仓库安装」填入仓库地址即可；也可把本目录放到
   `data/plugin_data/meme_manager/packs/claude-pixel-fanart/` 下，再在页面中刷新。
3. **仓库地址**：本包已发布在 https://github.com/xeabie/claude-pixel-fanart ，
   清单中的 `source` 已指向该仓库（`ref: main`、`subpath: "."`），
   安装时仓库填 `xeabie/claude-pixel-fanart`，`ref` 填 `lite`（轻量版）或 `main`（原图），`subpath` 填 `.`。

## 关于图片

- 素材由本地目录 `claude-fannart-meme/` 整理而来：原始资料含中文命名与英文命名两套同内容文件（共 36 个文件），本包只保留 **18 张不重复图片**，统一使用语义化英文文件名。
- 图片按表情语义归类到模板提供的标准分类词表；未使用的分类（`baka`、`cpu`、`givemoney`、`morning`、`reply`、`see`、`sleep`）**未写入清单**，以避免出现「清单声明了分类、但 `memes/` 下没有对应目录」的不一致。
- 未附带 `semantic_metadata.json`（可选的语义扩展）。如需语义检索，可在插件的「语义化」页面生成后按分享版导出。

## 许可

`All Rights Reserved`（保留所有权利）。本包为角色二创素材，默认不授权再分发或商用；如需公开发布，请自行确认授权范围并替换 `manifest.json` 中的 `license` 字段。
