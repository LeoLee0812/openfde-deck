# 看懂 openfde.net

[![部署](https://img.shields.io/badge/Vercel-已部署-17140D?style=flat-square&logo=vercel&logoColor=white)](https://deck.saveme505.help)
[![幻灯片](https://img.shields.io/badge/幻灯片-26_页-C4471F?style=flat-square)](https://deck.saveme505.help)
[![格式](https://img.shields.io/badge/SVG_+_PPTX-可下载-B8552E?style=flat-square)](./openfde-deck.pptx)
[![素材来源](https://img.shields.io/badge/逆向自-OpenFDE--WEB-6A6356?style=flat-square&logo=github&logoColor=white)](https://github.com/OpenFDEAI/OpenFDE-WEB)

> 一个网站，两个身份，三条路径——26 页讲完 [openfde.net](https://openfde.net) 到底在干什么，以及你该点哪里。

## 这是什么

openfde.net 内容不少，但路标不多：六个顶层导航（其中两个带二级下拉）加起来三十多个入口，
白皮书 16 章、信号库 1,251 条、11 个客户案例、4 个 Agent、4 种服务全部平铺在一层；
首页在讲「企业 AI 落地」，白皮书在讲「怎么转型当 FDE」——两个完全不同的读者共用一个首页。
于是最基本的那个问题反而没答案：**它到底是要卖你东西，还是要教你东西？**

这个站就是那个问题的答案。它把官网的素材从源码里逆向出来，重新组织成一份 PPT 风格的讲解：

| 部分 | 页数 | 讲什么 |
| --- | --- | --- |
| 站点地图 | P02–P06 | 两个身份、六个导航各回答什么问题、三条路径导航法 |
| 概念层 | P07–P13 | FDE 一句话定义、4C、四个关键数字、为什么是现在、谁在招、10 步工作流、8 维能力 |
| 商业层 | P14–P22 | 9 个行业、4 个场景、5 个招牌案例、交付平台、4 个专家 Agent、蒸馏引擎、信任边界、4 种服务 |
| 开源与参与 | P23–P26 | 16 章白皮书地图、1,251 条信号库、首批 20 人计划、入口对照表 |

一句话结论：**它只干三件事——定义一个岗位（免费开源）、卖一支队伍（收入来源）、攒一个网络（未来供给）。**

## 怎么用

- 在线看：[deck.saveme505.help](https://deck.saveme505.help)
- 键盘：`←` `→` 翻页，`空格` 下一页，`F` 全屏，`N` 开关讲解条，`T` 开关缩略图
- 手机：左右滑动翻页
- 深链：地址栏 `#p12` 直接跳到第 12 页
- 想拿去讲：右上角下载 PPTX（26 页，每页带讲稿备注、含页面切换与元素入场动画）

## 素材与数据来源

全部内容取自站点自己的源码仓库 [OpenFDEAI/OpenFDE-WEB](https://github.com/OpenFDEAI/OpenFDE-WEB)
（提交 `8fa397d`）：

- `src/data/site.ts` — 一句话定义、4C、四个关键数字、10 步工作流、8 维能力、在招公司
- `src/data/biz.ts` — 9 个行业、4 个场景、11 个案例、交付平台、4 个 Agent、蒸馏引擎、4 种服务
- `src/data/home-content.ts` · `src/content/nav.ts` · `src/i18n/dictionaries.ts` — 首页文案、白皮书章节、导航结构
- `src/app/globals.css` — 配色（暖米纸 `#F7F5EF` + 赭红 `#C4471F` + 墨黑 `#17140D`，与官网 `@theme` 同源）

**没有一个数字是编的**，页面上凡是引用数据的地方都标了出处。

## 技术

| 项 | 说明 |
| --- | --- |
| 幻灯片 | 26 个独立 SVG（1280×720），图标与图片已内嵌，单文件自包含 |
| 生成方式 | [ppt-master](https://github.com/anthropics/claude-code) skill：素材 → 设计规格 → 逐页手写 SVG → 质检 → 导出 PPTX |
| 配图 | 4 张 AI 生成底图（editorial 渲染 × warm-earth 调色），雨燕与 logo 复用官方素材 |
| 前端 | 单文件静态站，无框架、无构建、无依赖；SVG 用 `<img>` 加载，缩略图 `loading="lazy"` |
| 字体 | 标题 `Georgia, KaiTi, serif`；正文 `PingFang SC / Microsoft YaHei`；代码 `Consolas` |
| 部署 | 推送 `main` → Vercel 自动部署 |

## 目录

```
openfde-deck/
├── index.html            # 翻页播放器（键盘/触屏/缩略图/讲解条）
├── slides.js             # 26 页的文件名、标题与讲解文案
├── slides/*.svg          # 26 页幻灯片
├── openfde-deck.pptx     # 可下载的 PPTX（含讲稿备注）
├── favicon.svg
└── vercel.json           # cleanUrls + slides/ 长缓存
```

## 说明

这是**第三方讲解版**，不是 OpenFDE 官方材料，也不代表 OpenFDE 的立场。
观点部分（例如「难点只在蒸馏引擎第二步」「这条值得让法务重点核」）是我的判断，与官方无关。
官方信息请以 [openfde.net](https://openfde.net) 为准。
