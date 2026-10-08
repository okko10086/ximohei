# 戏墨黑 SC · Xi Mo Hei SC

一款基于**思源黑体 SC** 改造的现代黑体，六个字重，取「大字面、紧中宫、略窄挺」的调性。
**SIL Open Font License 1.1，免费商用。**

本仓库同时是这款字体的**发售落地页**（GitHub Pages）与网页字体分发点。

---

## 字体

| 文件 | 字重 | OS/2 字重值 |
|---|---|---|
| `XiMoHeiSC-Light.otf` | 细体 | 300 |
| `XiMoHeiSC-Normal.otf` | 常规 | 350 |
| `XiMoHeiSC-Regular.otf` | 标准 | 400 |
| `XiMoHeiSC-Medium.otf` | 中等 | 500 |
| `XiMoHeiSC-Bold.otf` | 粗体 | 700 |
| `XiMoHeiSC-Heavy.otf` | 特粗 | 900 |

另有**水墨标题体**两个字重（`XiMoHeiInkSC-Bold` / `Heavy`），轮廓带水渍边缘，用于大字号标题。

覆盖 65,535 字形 / 44,812 个 cmap 字符 / 20,976 个基本区汉字，含扩展 A 区、拉丁字母、
数字、注音、假名、谚文与全套中文标点。完整保留 `GPOS`/`GSUB` 与 `vhea`/`vmtx` **竖排**支持。

> 桌面 OTF 每个约 16.5 MB，仓库内只放**网页用 WOFF2 子集**。桌面版从 Releases 下载。

## 网页字体

```css
@font-face {
  font-family: 'Xi Mo Hei SC';
  src: url('fonts/ximohai-regular.woff2') format('woff2');
  font-weight: 400;
  font-display: swap;
}
body { font-family: 'Xi Mo Hei SC', sans-serif; }
```

- `fonts/ximohai-*.woff2` —— 落地页自用子集（210 字，约 81 KB / 字重）
- `fonts/full-ximohai-*.woff2` —— GB2312 完整子集（7,690 字符，约 3.2 MB），覆盖现代中文约 99.7%

## 设计说明

思源黑体的轮廓**已经合并**（一个「十」字只有一条闭合轮廓），无法按单条笔画加粗减细。
全部改造通过**全局坐标变形**完成，四个旋钮：

1. **中宫收紧 `k = 0.08`** —— 对局部缩放率建模，笔画只渐变变细、绝不增粗
2. **字面纵横比 `sx=1.005, sy=1.062`** —— 字面由源字体的 0.992 收窄到约 0.937
3. **字面率补偿** —— 抵消中宫收紧带来的字面缩小
4. **字重体系** —— 沿用思源黑体六字重骨架，保证 InDesign / Photoshop / CSS 里字重梯度正确

变形严格限定为 `x′=f(x)`、`y′=g(y)`，两者不交叉——这是 Type 2 charstring
编码正确性的硬约束（`hlineto` / `hvcurveto` 带隐式坐标，靠"相等"成立）。

## 授权

**SIL Open Font License 1.1**，全文见 [`OFL.txt`](OFL.txt)。

- **可以**：免费用于任何场景，包括商业用途；自由分发、嵌入、修改
- **不可以**：单独售卖字体文件本身；在衍生字体中使用保留字体名；以 Adobe 名义做宣传背书

保留字体名：`Xi Mo Hei` · `Xi Mo Hei SC` · `戏墨黑` · `戏墨黑 SC`

## 上游致谢

- **Source Han Sans SC**（思源黑体）© 2014–2021 Adobe，SIL OFL 1.1
  设计：Ryoko NISHIZUKA 西塚涼子、Frank Grießhammer、Wenlong ZHANG 张文龙 等
- 技术路径参考 **未来荧黑 Glow Sans**（welai/glow-sans）

## 诚实说明

本字体是思源黑体的衍生作品，依 OFL 第 5 条整体以 OFL 1.1 发布，
因此**不主张独占商用**，也不能申请外观设计专利（国家知识产权局已在提交 WIPO 的
正式答复中定性：*Typefaces/type fonts are currently not the subject matter for
design patent protection in China.*）。
