# DataVidia 2026

Proyek kompetisi data science untuk menganalisis data lingkungan dan kualitas udara di Jakarta, Indonesia.

## Ikhtisar Proyek

Proyek ini melibatkan analisis komprehensif data lingkungan Jakarta termasuk indeks kualitas udara (ISPU), pola cuaca, demografi penduduk, kualitas air sungai, dan kesehatan vegetasi. Tujuannya adalah membangun model prediktif dan mengekstrak insight dari beberapa dataset lingkungan yang saling terhubung dengan rentang tahun 2010 hingga 2025.

## Deskripsi Dataset

Proyek menggunakan beberapa sumber data yang diorganisir berdasarkan kategori:

### 1. Kualitas Udara (ISPU - Indeks Standar Pencemar Udara)
- **Lokasi**: `data/01-raw/ISPU/`
- **Rentang Waktu**: 2010-2025
- **Isi**: Indeks standar pencemar udara harian untuk DKI Jakarta
- **File**: Dataset tahunan dari 2010-2025, termasuk data komponen 2023-2025

### 2. Data Cuaca (Cuaca Harian)
- **Lokasi**: `data/01-raw/cuaca-harian/`
- **Isi**: Pengukuran cuaca harian dari 5 stasiun di Jakarta:
  - DKI1: Bundaran HI
  - DKI2: Kelapa Gading
  - DKI3: Jagakarsa
  - DKI4: Lubang Buaya
  - DKI5: Kebon Jeruk

### 3. Data Penduduk (Jumlah Penduduk)
- **Lokasi**: `data/01-raw/jumlah-penduduk/`
- **Rentang Waktu**: 2013-2021
- **Isi**: Demografi penduduk menurut kelompok usia dan jenis kelamin di DKI Jakarta

### 4. Kualitas Air Sungai (Kualitas Air Sungai)
- **Lokasi**: `data/01-raw/kualitas-air-sungai/`
- **Isi**: Pengukuran kualitas air sungai-sungai di Jakarta

### 5. Indeks Vegetasi (NDVI)
- **Lokasi**: `data/01-raw/NDVI (vegetation index)/`
- **Isi**: Data Normalized Difference Vegetation Index untuk Jakarta

### 6. Hari Libur Nasional & Akhir Pekan
- **Lokasi**: `data/01-raw/libur-nasional/`
- **Isi**: Data kalender untuk hari libur dan akhir pekan

## Struktur Direktori

```
.
├── README.md                 # Dokumentasi proyek
├── pyproject.toml           # Konfigurasi dan dependensi proyek
├── data/
│   ├── 01-raw/              # Data asli, belum diproses
│   │   ├── cuaca-harian/    # Data cuaca harian
│   │   ├── ISPU/            # Indeks kualitas udara
│   │   ├── jumlah-penduduk/ # Data penduduk
│   │   ├── kualitas-air-sungai/ # Kualitas air sungai
│   │   ├── libur-nasional/  # Kalender liburan
│   │   └── NDVI/            # Indeks vegetasi
│   ├── 02-cleaned/          # Data yang sudah diproses dan dibersihkan
│   └── sample_submission.csv # Format sampel submission
└── notebooks/               # Jupyter notebook untuk analisis
    ├── cleaning.ipynb      # Formatting dan pembersihan data
    └── notebook.ipynb       # Analisis data eksplorasi
```

## Memulai

### Prasyarat
- Python >= 3.12
- Virtual environment (disarankan)

### Instalasi

1. Clone repositori:
```bash
git clone <repository-url>
cd "DataVidia 2026"
```

2. Buat dan aktifkan virtual environment:
```bash
python -m venv .venv
# Di Windows:
.\.venv\Scripts\Activate.ps1
# Di macOS/Linux:
source .venv/bin/activate
```

3. Pasang dependensi:
```bash
pip install -e .
```

### Dependensi

Proyek menggunakan library kunci berikut:
- **pandas** & **numpy**: Manipulasi data dan komputasi numerik
- **matplotlib** & **seaborn**: Visualisasi data
- **ipython** & **ipywidgets**: Jupyter notebook interaktif
- **ydata-profiling**: Profiling dan pelaporan data otomatis

### Manajemen Branch

**Branch master** adalah branch utama yang berisi kode stabil dan siap produksi.

Untuk melakukan eksperimen atau pengembangan fitur baru, buat branch terpisah:

```bash
# Membuat dan beralih ke branch baru untuk eksperimen
git checkout -b dev-nama-anda

# Atau gunakan perintah modern
git switch -c dev-nama-anda
```

**Konvensi penamaan branch**:
- `dev-nama-anda` - Branch pengembangan personal
- `feature/deskripsi-fitur` - Untuk pengembangan fitur baru
- `bugfix/deskripsi-bug` - Untuk perbaikan bug
- `hotfix/deskripsi-urgent` - Untuk perbaikan mendesak

**Aturan Commit dan Push ke GitHub**:

Gunakan prefix pada pesan commit untuk konsistensi:

```bash
# Untuk dokumentasi
git commit -m "docs: menambahkan penjelasan branch management"

# Untuk perbaikan bug
git commit -m "fix: memperbaiki error pada proses cleaning data"

# Untuk fitur baru
git commit -m "feat: menambahkan fungsi preprocessing untuk ISPU data"

# Untuk refactoring
git commit -m "refactor: mengorganisir ulang struktur notebook"

# Untuk testing
git commit -m "test: menambahkan unit test untuk data validation"

# Untuk konfigurasi
git commit -m "config: update dependencies di pyproject.toml"
```

**Prefix yang direkomendasikan**:
- `feat:` - Fitur baru
- `fix:` - Perbaikan bug
- `docs:` - Perubahan dokumentasi
- `style:` - Perubahan style/format (bukan kode logika)
- `refactor:` - Refactoring kode
- `test:` - Penambahan atau perubahan test
- `config:` - Perubahan konfigurasi
- `perf:` - Perbaikan performa

**Langkah push ke GitHub**:

```bash
# Push branch ke remote (pertama kali)
git push -u origin dev-nama-anda

# Push perubahan selanjutnya
git push origin dev-nama-anda

# Setelah selesai, merge ke master melalui Pull Request di GitHub
# atau merge secara lokal:
git checkout master
git merge dev-nama-anda
git push origin master
```

## Pipeline Pemrosesan Data

### Tahap 1: Data Mentah (01-raw/)
- Dataset asli seperti yang diunduh dari sumber
- Tidak ada modifikasi yang diterapkan

### Tahap 2: Data Dibersihkan (02-cleaned/)
- Dataset yang diproses dan distandarkan
- Peningkatan kualitas data dan transformasi

## Analisis

Proyek mencakup notebook Jupyter untuk:
- **Analisis Data Eksplorasi**: Eksplorasi dan visualisasi data awal
- **Formatting Data**: Langkah pembersihan dan preprocessing
- Identifikasi pola dan feature engineering

## Tujuan Proyek

1. **Integrasi Data**: Menggabungkan beberapa dataset lingkungan
2. **Penemuan Pola**: Mengidentifikasi hubungan antara kualitas udara dan faktor lingkungan
3. **Pemodelan Prediktif**: Membangun model untuk memperkirakan kualitas udara dan metrik lingkungan
4. **Visualisasi**: Membuat insight melalui visualisasi data
5. **Submission Kompetisi**: Menghasilkan prediksi dalam format yang diperlukan

## Penggunaan

### Menjalankan Notebook
```bash
jupyter notebook notebooks/
```

### Menjalankan Notebook
```bash
jupyter notebook notebooks/
```

### Memuat Data
```python
import pandas as pd

# Muat data kualitas udara
ispu = pd.read_csv('data/01-raw/ISPU/data-indeks-standar-pencemar-udara-(ispu)-di-provinsi-dki-jakarta-komponen-data-2024.csv')

# Muat data cuaca
weather = pd.read_csv('data/01-raw/cuaca-harian/cuaca-harian-dki1-bundaranhi.csv')
```

## Sumber Data

Semua data bersumber dari database lingkungan dan demografi resmi Jakarta. Data mentah mempertahankan format dan enkoding aslinya untuk keterlacakan.

## Catatan

- Semua timestamp berada di zona waktu Jakarta (WIB - Waktu Indonesia Bagian Barat)
- Beberapa dataset mungkin memiliki celah dalam data historis
- Langkah pembersihan dan preprocessing data didokumentasikan di `notebooks/cleaning.ipynb`

## Lisensi

Proyek ini adalah bagian dari kompetisi DataVidia 2026.

## Kontak & Dukungan

Untuk pertanyaan atau masalah terkait proyek ini, harap merujuk pada panduan kompetisi.

---

Terakhir Diperbarui: 31 Januari 2026
