# 🌍 开放数据图谱 · Open Data Atlas

2,121 个经过核实的开源数据集，每条含**中英双语介绍** + URL 核实状态 + 许可证 + 去重 + 引用网络 + 尺寸信息。

🔗 **在线**: https://lust0yixiong.github.io/geodata-atlas/

[![data-license](https://img.shields.io/badge/data-CC--BY--4.0-blue)](https://creativecommons.org/licenses/by/4.0/) [![datasets](https://img.shields.io/badge/datasets-2,121-22c55e)](https://lust0yixiong.github.io/geodata-atlas/) [![bilingual](https://img.shields.io/badge/descriptions-zh%2Fen%20100%25-blue)](https://lust0yixiong.github.io/geodata-atlas/) [![verified](https://img.shields.io/badge/verified-96%25-22c55e)](https://lust0yixiong.github.io/geodata-atlas/)

## 入口

| 链接 | 用途 |
|---|---|
| **[在线 dashboard](https://lust0yixiong.github.io/geodata-atlas/)** | 多类别浏览/筛选/可视化，每条带双语介绍 |
| [`data/catalog.csv`](./data/catalog.csv) | 主目录 (33 列, 2121 行) — Excel/Python/R |
| [`data/catalog.parquet`](./data/catalog.parquet) | 列式压缩 — DuckDB/pandas |
| [`data/datapackage.json`](./data/datapackage.json) | Frictionless Data Package |
| [`data/croissant.jsonld`](./data/croissant.jsonld) | Croissant/Google Dataset Search 兼容 |
| [`data/atlas_report.md`](./data/atlas_report.md) | 深度叙述报告 (39 章节) |

## 速览

```
2,121 datasets · 33 columns · 16 themes (Vector·Geospatial)
   ↓ 每条带中英双语介绍 (desc_zh / desc_en, 100% 覆盖)
   ↓ 96% URL 核实 (lychee)
   ↓ 多源去重 (规则 + Splink 概率匹配)
   ↓ 20 旗舰 × 135 下游派生品引用网络
```

## Python

```python
import pandas as pd
df = pd.read_csv('https://lust0yixiong.github.io/geodata-atlas/data/catalog.csv')
print(df[['name','desc_zh','license_now','url']].head())
```

## 如何扩展（其它类别数据）

本仓库是**生成产物**。数据源 + 工具链在主项目 `GeoData_Learn/`：
- `AGENTS.md` — Codex 入口，按它的 SOP 加新类别
- `scripts/merge_catalog.py` / `build_dashboard.py` 等
- 详见 `docs/PIPELINE_PLAYBOOK.md`

## License

数据 CC BY 4.0 · 网站代码 MIT · catalog 内各数据集各有独立许可证（见 `url`）

---
*Open Data Atlas · 单文件 dashboard · 中英双语 · 由 14 阶段 pipeline 生成*
