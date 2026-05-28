# Dataset KBBI Indonesia

Kamus Besar Bahasa Indonesia (KBBI) lengkap — 209.868 kata beserta arti dan kelas kata. Dilengkapi daftar kata baku dan tidak baku.

## Data

### 1. Kamus KBBI

**File:** `kbbi.csv`  
**Records:** 209.868 kata  
**Size:** ~24 MB  
**Delimiter:** koma (`,`)

| Kolom | Deskripsi | Contoh |
|-------|-----------|--------|
| `word` | Kata | `cinta` |
| `arti` | Definisi (HTML) | `suka sekali; sayang benar` |
| `type` | Kelas kata (integer) | `1` (nomina) |

### 2. Kata Baku — Tidak Baku

**File:** `kata-baku-tidak-baku.csv`  
**Records:** 1.453 pasangan  
**Size:** ~23 KB  
**Delimiter:** titik koma (`;`)

| Kolom | Deskripsi | Contoh |
|-------|-----------|--------|
| `salah` | Kata tidak baku | `praktek` |
| `benar` | Kata baku | `praktik` |

## Contoh

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

Gunakan [api-datasets-indonesia](https://github.com/prodhokter/api-datasets-indonesia) untuk akses via REST API:

```
GET /api/dictionary/search?q=cinta&limit=20
GET /api/dictionary/:word
GET /api/kata-baku?search=praktek
GET /api/kata-baku/check/:word
```

## Sumber

Badan Pengembangan dan Pembinaan Bahasa, Kemendikbud.

## Lisensi

Data bersumber dari institusi pemerintah Indonesia. Gunakan sesuai ketentuan yang berlaku.
