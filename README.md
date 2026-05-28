# Dataset KBBI Indonesia

[![License: MIT](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![API Status](https://img.shields.io/badge/api-live-green)](https://api.ibnuhabib.web.id/api/dictionary/search?q=cinta)
[![Records](https://img.shields.io/badge/records-211.321-orange)](#data)

Kamus Besar Bahasa Indonesia (KBBI) lengkap — 209.868 kata beserta arti dan kelas kata. Dilengkapi daftar 1.453 pasangan kata baku dan tidak baku.

## Data

### 1. Kamus KBBI

| File | Records | Size | Delimiter |
|------|---------|------|-----------|
| `kbbi.csv` | 209.868 | ~24 MB | `,` (koma) |

| Kolom | Deskripsi | Contoh |
|-------|-----------|--------|
| `word` | Kata | `cinta` |
| `arti` | Definisi (HTML) | `suka sekali; sayang benar` |
| `type` | Kelas kata (integer) | `1` (nomina) |

### 2. Kata Baku — Tidak Baku

| File | Records | Size | Delimiter |
|------|---------|------|-----------|
| `kata-baku-tidak-baku.csv` | 1.453 | ~23 KB | `;` (titik koma) |

| Kolom | Deskripsi | Contoh |
|-------|-----------|--------|
| `salah` | Kata tidak baku | `praktek` |
| `benar` | Kata baku | `praktik` |

## Contoh Data

**kbbi.csv:**
```csv
word,arti,type
"cinta","suka sekali; sayang benar",1
```

**kata-baku-tidak-baku.csv:**
```csv
salah;benar
praktek;praktik
atlite;atlet
```

## API

Gunakan [api-datasets-indonesia](https://github.com/prodhokter/api-datasets-indonesia) untuk akses REST API.

**Base URL:** `https://api.ibnuhabib.web.id`

```bash
# Prefix search — cari kata diawali "cinta"
curl "https://api.ibnuhabib.web.id/api/dictionary/search?q=cinta&limit=5"

# Exact match — satu kata spesifik
curl "https://api.ibnuhabib.web.id/api/dictionary/cinta"

# Cek kata baku
curl "https://api.ibnuhabib.web.id/api/kata-baku/check/praktek"
# → {"word":"praktek","is_baku":false,"correction":"praktik"}

# Cari pasangan baku-tidak baku
curl "https://api.ibnuhabib.web.id/api/kata-baku?search=praktek"

# Download CSV
curl -O "https://api.ibnuhabib.web.id/download/dictionary.csv"
curl -O "https://api.ibnuhabib.web.id/download/kata-baku.csv"
```

## Dataset Terkait

- [api-datasets-indonesia](https://github.com/prodhokter/api-datasets-indonesia) — REST API
- [dataset-sekolah-indonesia](https://github.com/prodhokter/dataset-sekolah-indonesia)
- [dataset-perguruan-tinggi-indonesia](https://github.com/prodhokter/dataset-perguruan-tinggi-indonesia)
- [dataset-program-studi-indonesia](https://github.com/prodhokter/dataset-program-studi-indonesia)
- [dataset-wilayah-indonesia](https://github.com/prodhokter/dataset-wilayah-indonesia)

## Sumber

Badan Pengembangan dan Pembinaan Bahasa, Kemendikbud.

## Lisensi

MIT — © 2025 [Ibnul Habib](https://github.com/prodhokter). Data bersumber dari institusi pemerintah Indonesia.
