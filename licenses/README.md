# 素材与字体来源

本目录随网页一同发布，保留第三方素材的原始许可文本。

| 素材 | 来源与版本 | 许可与归属 |
| --- | --- | --- |
| Noto Serif SC，400 / 600 字重 | [Fontsource Noto Serif SC](https://fontsource.org/fonts/noto-serif-sc)，npm `@fontsource/noto-serif-sc` 5.3.0；上游 [Google Fonts](https://github.com/google/fonts/tree/main/ofl/notoserifsc) | Google Inc.；[SIL Open Font License 1.1](./Noto-Serif-SC-OFL.txt) |
| Noto Sans SC，400 字重 | [Fontsource Noto Sans SC](https://fontsource.org/fonts/noto-sans-sc)，npm `@fontsource/noto-sans-sc` 5.3.0；上游 [Google Fonts](https://github.com/google/fonts/tree/main/ofl/notosanssc) | Google Inc.；[SIL Open Font License 1.1](./Noto-Sans-SC-OFL.txt) |
| Phosphor 界面图标 | [Phosphor Icons React](https://github.com/phosphor-icons/react)，npm `@phosphor-icons/react` 2.1.10 | Copyright (c) 2020 Phosphor Icons；[MIT License](./Phosphor-Icons-MIT.txt) |
| 剧情背景音乐（五首器乐） | [Scott Buckley 官方曲库](https://www.scottbuckley.com.au/library/)；保留原始 MP3 | Scott Buckley；[CC BY 4.0 曲目、署名与下载记录](./music.md) |

## 字体发布方式

`scripts/prepare-fonts.mjs` 扫描 `src/` 中的文本文件，根据其中出现的字符及上游 CSS 的 `unicode-range` 选择需要的 WOFF2 分片。原始字体二进制、字体名称、字重与 Unicode 覆盖范围保持不变。生成文件保存在 `public/fonts/`，样式保存在 `src/fonts.css`；未引入外部字体服务。

编辑文案、新增章节、在 CSS 中添加文字或更新字体依赖后，执行 `node scripts/prepare-fonts.mjs`。`node scripts/prepare-fonts.mjs --check` 只读检查当前资源与源码是否一致。脚本扫描所有当前源码文字，保守地包括注释和代码中的字符；未来从远程加载的文案需要先进入本地源码，或另行扩充字体准备流程。

`public/fonts/.font-manifest.json` 记录生成文件及 SHA-256 摘要。再次执行时只会清理上次清单记录、已不再需要且摘要仍匹配的字体，不清理其他素材或手工修改的文件。

## 项目原创素材

- `assets/kobe-rookie-illustration.png`：内置 ImageGen 绘制的少年科比黑金插画，1024×1536；不是历史照片。提示词保存在 `docs/asset-prompts/kobe-rookie.txt`。
- 当前球场由圆圈、号码和姓名构成平面示意；以下早期人物精灵与木纹素材已不用于球场渲染。

- `assets/kobe-portrait.png`、`assets/kobe-hold-wide.png`、`assets/kobe-shot-wide.png`：早期原型的 ImageGen 艺术重绘，当前开场已不使用；并非真实历史照片。它们不适用上表中第三方字体及图标的开源许可。
- `assets/court-texture.png`、`assets/player-gold-atlas.png`、`assets/player-gather.png`：依据用户选定的视觉稿，用内置 ImageGen 制作的暗木纹与球员动作线描素材。
- 球场示意、球员号码、姓名、动画时序、交互效果及程序合成音效：本项目实现。球场示意用于解释游戏情境，不声称逐帧复现历史录像。

## 历史内容依据

当前真实开场与终章照片的出处、摄影者、年份和 Creative Commons 许可详见 [historical-photos.md](./historical-photos.md)。原文件保留原尺寸，页面采用灰度、裁切与暗部叠加显示。照片改编沿用原许可，许可范围不扩展到本游戏所有代码。

第一章回望另采用 Paul Kucher 于 2005 年拍摄的达美中心外景，CC BY 2.0，详见 [chapter-one-photos.md](./chapter-one-photos.md)。它没有被标为 1997 年现场。

2010 年总决赛第七场的日期、比分与主要回合锚点参考 [NBA 官方比赛记录](https://statsdmz.nba.com/pdfs/20100617/20100617_BOSLAL_book.pdf)。对白、内心描述、具体空间安排与改写结果属于游戏创作。
