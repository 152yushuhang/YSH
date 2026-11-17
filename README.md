# 公路工程 CAD 与航拍套合

`cad-aerial-overlay` 是面向公路、桥梁和匝道工程的 Agent 技能。它为 Codex 提供 CAD 与航拍影像套合、剩余挖填方汇报和航拍视频叠线的操作与核验流程，让读图的人能在同一画面里看清设计线位、现场进度和两者的差异。

*An agent skill for aligning highway and bridge CAD drawings with drone imagery, presenting earthwork profiles, and overlaying CAD geometry on aerial video.*

## 能做什么

| 任务 | 提供的资料 | 建议交付 |
| --- | --- | --- |
| CAD 与航拍套合 | DWG 或 DXF、航拍原图、可辨地物或测量控制点 | 可编辑 DWG、相对路径关联的影像底图、全图预览。返修时附局部前后对比。 |
| 剩余挖填方与立体纵断面 | 方量 DWG 或测量成果、实测三角网、平场标高或设计纵断面 | 带测区定位、短引线和就地小图的航拍总览，以及完整纵断面 PDF。 |
| 连续航拍视频叠加路线与桥梁线框 | 航拍原视频、路线 CAD、样片。三维桥梁展示还需要结构高程或模型。 | 连续试段用于核对跟踪、透视和标注，验证通过后用原片导出。 |

套图时先检查坐标和资料，再用桥台、路缘、坡顶等可辨地物配准。只更换底图或修正错位时，保留工程矢量和已经对齐的区域。截图箭头用于定位待检查的位置，错位原因以原影像和图纸为准。

普通照片或经局部变形的套图用于目视对照。涉及放样、验收或计量时，应按工程要求使用测量控制和独立检查点。方量采用原测量成果中已核对的汇总，缺测纵断面留空。视频中的结构线框应使用有依据的几何和经验证的镜头跟踪。

## 安装与调用

欢迎下载并在自己的项目中使用。可在 GitHub 仓库选择 **Code → Download ZIP**。解压后，把里面的 `cad-aerial-overlay` 文件夹完整复制到 Codex 项目下的 `.agents/skills/`。包含 `SKILL.md` 和 `references/` 的目录结构如下。

```text
你的项目/
└── .agents/
    └── skills/
        └── cad-aerial-overlay/
            ├── SKILL.md
            └── references/
```

在该项目里打开 Codex，输入 `$cad-aerial-overlay` 并描述任务。兼容 [Agent Skills](https://agentskills.io/) 的其他工具，可把同一个文件夹放到其指定的技能目录。实际读取、修改和出图需要相应的文件权限及 CAD、影像或视频工具。

## 使用示例

> `$cad-aerial-overlay` 把新航拍图套进这份匝道 DWG。用桥台和桥面边线定位，重点检查弯道中线和外侧坡顶，交付 DWG、配套底图和前后对比。

> `$cad-aerial-overlay` 根据方量 DWG 和实测三角网制作两页汇报 PDF。第一页在对应测区旁放立体纵断面小图，第二页完整展示沿程标高。请标出高差与剩余挖填方。

> `$cad-aerial-overlay` 对照参考视频，在原航拍的连续镜头里叠加设计路线、桩号和桥梁线框。先做一个短段检查线框漂移和抖动。

[查看 SKILL.md](cad-aerial-overlay/SKILL.md)
