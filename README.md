# 🌍 开放数据图谱 · Open Data Atlas

**6,492 个**经过核实的开源数据集，跨 **7 大类别**，每条含**中英双语介绍** + URL 核实状态 + 许可证 + 去重 + 尺寸信息。

🔗 **在线**: https://lust0yixiong.github.io/geodata-atlas/

[![data-license](https://img.shields.io/badge/data-CC--BY--4.0-blue)](https://creativecommons.org/licenses/by/4.0/) [![datasets](https://img.shields.io/badge/datasets-6,492-22c55e)](https://lust0yixiong.github.io/geodata-atlas/) [![categories](https://img.shields.io/badge/categories-7-0891b2)](https://lust0yixiong.github.io/geodata-atlas/) [![bilingual](https://img.shields.io/badge/descriptions-zh%2Fen%20100%25-blue)](https://lust0yixiong.github.io/geodata-atlas/)

## 七大类别

| 类别 | 数据集数 | 说明 |
|---|---:|---|
| **Vector · Geospatial** 矢量地理 | 2,121 | 行政边界/交通/水文/POI/建筑/灾害/保护区等 16 主题 |
| **Raster · Hyperspectral Imagery** 高光谱影像 | 1,137 | AVIRIS/EMIT/EnMAP 机载星载成像光谱、矿物/植被/水色光谱库 |
| **Infrared · Remote Sensing** 红外遥感 | 1,024 | Landsat/MODIS 地表温度与发射率、热红外产品 |
| **Radar · SAR** 合成孔径雷达 | 876 | Sentinel-1、星载/机载 SAR 及云平台档案 |
| **Geophysics · Geomagnetism** 地磁地球物理 | 612 | INTERMAGNET 台站、WMM/IGRF 地磁场模型、地磁观测 |
| **Geophysics · Gravity** 重力地球物理 | 389 | ICGEM 全球重力场模型、EGM2008、时变重力 |
| **Optical · Multispectral Remote Sensing** 多光谱遥感 | 333 | Sentinel-2 MSI、Landsat C2、多光谱地表反射率 |

> 在线 dashboard 左侧"类别"筛选可单独查看任一类别，每条数据集均有中英双语介绍、核实状态色块、来源证据。

## 入口

| 链接 | 用途 |
|---|---|
| **[在线 dashboard](https://lust0yixiong.github.io/geodata-atlas/)** | 多类别浏览/筛选/可视化，每条带双语介绍 |
| [`data/catalog.csv`](./data/catalog.csv) | 矢量主目录 (33 列, 2121 行) |
| [`data/hyperspectral_catalog.csv`](./data/hyperspectral_catalog.csv) | 高光谱目录 |
| [`data/infrared_catalog.csv`](./data/infrared_catalog.csv) | 红外目录 |
| [`data/sar_catalog.csv`](./data/sar_catalog.csv) | SAR 目录 |
| [`data/geomagnetic_catalog.csv`](./data/geomagnetic_catalog.csv) | 地磁目录 |
| [`data/gravity_catalog.csv`](./data/gravity_catalog.csv) | 重力目录 |
| [`data/multispectral_catalog.csv`](./data/multispectral_catalog.csv) | 多光谱目录 |
| [`data/catalog.parquet`](./data/catalog.parquet) | 矢量列式压缩 — DuckDB/pandas |
| [`data/datapackage.json`](./data/datapackage.json) | Frictionless Data Package |
| [`data/croissant.jsonld`](./data/croissant.jsonld) | Croissant/Google Dataset Search 兼容 |
| [`data/atlas_report.md`](./data/atlas_report.md) | 矢量深度叙述报告 (39 章节) |

## 速览

```
6,492 datasets · 5 categories · 中英双语 100%
   ↓
Vector 2,121 + Hyperspectral 1,137 + Infrared 1,024 + SAR 876 + Geomagnetism 612 + Gravity 389 + Multispectral 333
   ↓
URL 核实 (lychee) · 多源去重 · 来源证据留痕
```

## Python

```python
import pandas as pd

# 矢量
vec = pd.read_csv('https://lust0yixiong.github.io/geodata-atlas/data/catalog.csv')
# 高光谱 / 红外 / SAR
hsi = pd.read_csv('https://lust0yixiong.github.io/geodata-atlas/data/hyperspectral_catalog.csv')
ir  = pd.read_csv('https://lust0yixiong.github.io/geodata-atlas/data/infrared_catalog.csv')
sar = pd.read_csv('https://lust0yixiong.github.io/geodata-atlas/data/sar_catalog.csv')

print(vec[['name','desc_zh','license','url']].head())
```

## 方法

每个类别由独立的多阶段 pipeline 整理：LLM agent 发现/判断 + lychee URL 核验 + 规则/概率去重 + 中英双语介绍 + 来源证据留痕。矢量类工具链与方法论见主项目 `GeoData_Learn/`（`AGENTS.md`、`docs/PIPELINE_PLAYBOOK.md`、`scripts/`）。各遥感类别（高光谱/红外/SAR）由独立工作流维护、版本化迭代，统一汇入本 dashboard 按类别展示。

## License

数据 CC BY 4.0 · 网站代码 MIT · catalog 内各数据集各有独立许可证（见各条 `url`）

---
*Open Data Atlas · 单文件 dashboard · 5 类别 · 中英双语 · 6,492 datasets*
