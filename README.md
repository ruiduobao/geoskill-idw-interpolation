# Inverse Distance Weighting Interpolation (geoskill-idw-interpolation)

> Inverse Distance Weighting (IDW) spatial interpolation with adjustable power parameter and search radius; outputs an interpolated GeoTIFF raster

---

## 1. Overview

Inverse Distance Weighting (IDW) spatial interpolation: the value at a target point is the distance-weighted average of known point values in its neighborhood, with weights w = 1/d^p. Supports an adjustable power parameter p, search-radius limits, and nearest-neighbor search. Vectorized implementation; outputs an interpolated raster.

## 3. Quick Start

```bash
pip install -r requirements.txt
python geoskill-idw-interpolation.py --bbox 116 39 117 40 --synthetic --output-dir ./out
```

## 4. CLI Parameters

Run `python <skill>.py --help` for the full list. Common parameters:

| Parameter | Type | Description |
|---|---|---|
| `--bbox` | `float[4]` | WGS84 bounding box `min_lon min_lat max_lon max_lat` |
| `--input` | `path` | Local input file (GeoJSON/GeoTIFF/etc.) |
| `--output-dir` | `path` | Output directory (default `./output`) |
| `--synthetic` | `flag` | Use synthetic data instead of real input |
| `--quiet` | `flag` | Suppress non-essential stdout |

## 5. Input / Output

| File | Format | Description |
|---|---|---|
| `idw_result.tif` | GeoTIFF/GeoJSON/JSON | Primary output |
| `output-manifest.json` | JSON | Run manifest |

## 6. Technical Principle

- IDW distance-weighted formula
- Power parameter and nearest-neighbor search
- Exact-hit handling

## 8. License

MIT License. See [`LICENSE`](./LICENSE) for full text.

---

> 中文完整版：[references/SKILL.zh-CN.md](references/SKILL.zh-CN.md)
