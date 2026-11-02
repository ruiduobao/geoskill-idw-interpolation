---
name: geoskill-idw-interpolation
description: '反距离权重(IDW)空间插值，支持幂参数和搜索半径，输出插值栅格GeoTIFF'
---

# 反距离权重插值 | IDW Interpolation

Inverse Distance Weighting (IDW) spatial interpolation: the value at a target point is the distance-weighted average of known point values in its neighborhood, with weights w = 1/d^p. Supports tuning of the power parameter p, search radius limits, and nearest-neighbor search. Vectorized implementation; outputs an interpolated raster.

## Core Algorithm / 核心算法

- IDW distance-weighted formula
- Power parameter and nearest-neighbor search
- Exact-hit handling

## Dependencies / 依赖

```bash
pip install numpy rasterio scipy
```

## Usage / 使用方法

### Example 1 (Synthetic data, offline)

```bash
python geoskill-idw-interpolation.py --bbox 116.0 39.0 117.0 40.0 --synthetic --output-dir ./out
```

### Example 2 (Custom region + quiet)

```bash
python geoskill-idw-interpolation.py --bbox 121.0 31.0 122.0 32.0 --synthetic --output-dir ./out2 --quiet
```

### Example 3 (Real input)

```bash
python geoskill-idw-interpolation.py --input <your data file> --output-dir ./out3
```

### Example 4 (Tiny-region boundary test)

```bash
python geoskill-idw-interpolation.py --bbox 116.39 39.90 116.40 39.91 --synthetic --output-dir ./out4 --quiet
```

## Output / 输出

| File | Format | Description |
|---|---|---|
| `idw_result.tif` | GeoTIFF/GeoJSON/JSON | Primary output |
| `output-manifest.json` | JSON | Run manifest |

## Data Source / 数据源 / Source

- Synthetic mode: generates physically consistent simulated data locally, with no external data sources.
- Real mode: reads local input files, with no network requests.

## Privacy / 隐私声明 / Privacy

- Runs fully offline by default; makes no network requests.
- `--synthetic` mode reads no external data.
- All computation is performed locally; user data is never uploaded.

## License / License

MIT

---

> 中文完整版：需要时再读 [references/SKILL.zh-CN.md](references/SKILL.zh-CN.md)，不要默认全量加载。
