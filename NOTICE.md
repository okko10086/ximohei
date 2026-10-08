# 来源与版权声明 · NOTICE

本仓库（`ximohei`）用于发布字体 **戏墨黑 SC / Xi Mo Hei SC** 及其发售落地页。
为免歧义，逐项声明仓库内每类内容的来源。

---

## 一、字体文件（`fonts/*.woff2`）

- **来源**：由本项目基于 **Source Han Sans SC（思源黑体）** 改造而来。
  上游 © 2014–2021 Adobe，以 **SIL Open Font License 1.1** 发布。
- **授权链**：OFL 1.1 的授权写在 **第 1 条 PERMISSION & CONDITIONS**——
  原文为 "Permission is hereby granted, free of charge, to any person obtaining a copy of
  the Font Software, to use, study, copy, merge, embed, modify, redistribute, and sell
  modified and unmodified copies of the Font Software"。该授权**未按用途设限**，
  且第 1 条末段明确 "The requirement for fonts to remain under this license does not
  apply to any document created using the Font Software"，即**用本字体排出来的作品不受 OFL 约束**。
  SIL 官方 FAQ 亦直接确认可用于商业用途。本字体整体以 OFL 1.1 发布，全文见
  [`OFL.txt`](OFL.txt)，未附加任何额外限制。
- **保留字体名**：上游保留名为 `Source`；本字体未使用该名称。
  本字体自行声明的保留字体名为 `Xi Mo Hei` / `Xi Mo Hei SC` / `戏墨黑` / `戏墨黑 SC`。
- **未使用**任何商业字库的轮廓数据。全部改造由本项目自有脚本
  （整数查表 + 可分离坐标变形）完成，过程可复现。

> 本仓库内的 `fonts/ximohai-*.woff2` 是上述字体的 **Web 子集**（210 字），
> `fonts/full-ximohai-*.woff2` 是 **GB2312 子集**（7,690 字）。子集属于 OFL 意义上的
> Modified Version，同样以 OFL 1.1 发布。

## 二、图片（`img/*`）

**仓库内所有图片均由本项目代码程序化生成，不含任何第三方素材、图库图片或 AI 模型生成内容。**

| 文件 | 生成方式 |
|---|---|
| `paper-tile.png` | 值噪声 + fbm 合成的可平铺宣纸砖（四向镜像保证接缝残差 < 2/255） |
| `hero.jpg` / `ink-card.jpg` | 程序合成：纸底 + 水墨纹理（本工程 `inktexture.py` 生成的 fbm 纹理） |
| `ink-composite.jpg` | 程序合成：字形掩膜 × 纹理层正片叠底 |
| `spec-compare.png` | 程序绘制：同字号渲染思源黑体与戏墨黑的「国」字并按 alpha>64 实测墨迹框 |
| `seal.png` / `seal-bai.png` | 程序绘制印章 + 飞白斑驳 |
| `stroke-curve.svg` | 程序生成的矢量折线图 |

其中 `spec-compare.png` 内含思源黑体单个字形的渲染结果——字体字形以图像形式呈现属正常使用，
OFL 未对此设限。

## 三、代码（`index.html` / `style.css` / `script.js`）

本项目原创，无第三方 JS/CSS 依赖（无 CDN、无追踪脚本、无 Cookie、无分析工具）。
页面不收集任何访客数据，不加载任何外部域名资源。

## 四、不包含的内容

- ❌ 无桌面 OTF 字体二进制（每个约 16.5 MB，未随仓库分发）
- ❌ 无任何用户数据、访问日志、账号信息或 API 密钥
- ❌ 无第三方图标库、字体库、图片库素材
- ❌ 无 AI 生成图像（本仓库全部图片为程序化生成，不涉及 AIGC 标识义务）

## 五、免责与边界

- 本字体为 OFL 授权的**开源字体**。依 OFL 第 5 条，任何人（包括本项目）都
  **不能主张对它的独占商用权**，也不能就字形申请外观设计专利。
- 中国大陆境内，字库可作为**计算机软件**受著作权保护；本字体的著作权归属
  其权利人，并已按 OFL 向全世界免费许可。
- 使用本字体不构成对 Adobe 的任何形式的背书或关联。

---

更新日期：2026-10-08
