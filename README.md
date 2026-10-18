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

> 桌面 OTF 每个约 16.5 MB，**未随本仓库分发**——本仓库只放网页用 WOFF2 子集。

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

## 更新记录

### v1.1（2026-10-18）· 西文字距均匀化

**改了什么**：只改西文字母的**侧边距（side bearing）**，字形轮廓一个点都没动。

**为什么改**：原版西文的侧距极不均匀 —— 实测 `A` 的侧距只占 advance 的 3.9%，
而 `H` 占 30.1%、`n` 占 31.0%、`i` 占 55.6%。两个字母并排时，
中间空白 = 左字的右间距 + 右字的左间距，所以会出现 `A B C  D E F G` 那种忽紧忽松。

**改法**：把每个字母两侧的留白统一成 **60/1000 em**。
任意两个字母并排，中间空白恒为 120/1000 em —— 跟汉字一样处处相同。

**实测**：

| | 改前 | 改后 |
|---|---|---|
| `ABCDEFG` 六处间隙 | `37 35 46 53 51 30` | `36 36 36 36 36 36` |
| 极差比（Regular） | 1.90× | **1.00×** |
| Light | 2.11× | 1.00× |
| Heavy | 1.79× | 1.04× |
| 水墨 Bold | 2.55× | 1.00× |

**中文零改动**：抽样 565 个汉字逐字比对 advance 与包围盒，0 个变化。

> 覆盖安装即可替换旧版。家族名不变（仍是 `Xi Mo Hei SC`），
> 版本号从 `1.000` 升到 `1.100`。

---

## 设计说明

思源黑体的轮廓**已经合并**（一个「十」字只有一条闭合轮廓），无法按单条笔画加粗减细。
全部改造通过**全局坐标变形**完成，四个旋钮：

1. **中宫收紧 `k = 0.08`** —— 对局部缩放率建模，笔画只渐变变细、绝不增粗
2. **字面纵横比 `sx=1.005, sy=1.062`** —— 字面由源字体的 0.992 收窄到约 0.937
3. **字面率补偿** —— 抵消中宫收紧带来的字面缩小
4. **字重体系** —— 沿用思源黑体六字重骨架，保证 InDesign / Photoshop / CSS 里字重梯度正确

变形严格限定为 `x′=f(x)`、`y′=g(y)`，两者不交叉——这是 Type 2 charstring
编码正确性的硬约束（`hlineto` / `hvcurveto` 带隐式坐标，靠"相等"成立）。

## 来源与版权

仓库内每一类内容的来源、授权链与不含项，见 [NOTICE.md](NOTICE.md)。
**仓库内全部图片均为程序化生成，不含第三方素材，也不含 AI 模型生成内容。**

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
