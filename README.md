# Analisis Spasiotemporal Divergensi Hotspot & Coldspot (2010-2020)

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![License](https://img.shields.io/badge/License-MIT-green)
![Status](https://img.shields.io/badge/Status-Research-orange)

## Deskripsi Proyek

Repositori ini memuat *pipeline* otomatisasi untuk agregasi data tabular dan visualisasi tingkat lanjut terhadap kejadian titik panas (*Hotspot*) kebakaran hutan dan lahan di **Provinsi Jambi** selama periode 2010-2020. 

Skrip ini memproses data keluaran analisis autokorelasi spasial (nilai *Z-Score* dari *Getis-Ord Gi\** yang direpresentasikan melalui kolom `Gi_Bin`) dan mengubahnya menjadi **Laporan Tabular Terintegrasi (Excel)** serta grafik **Diverging Stacked Bar** beresolusi tinggi (300 DPI). 

## Fitur & Kapabilitas

1.  **Batch Processing**: Memuat dan menggabungkan data CSV tahunan ke dalam satu *DataFrame* utama secara otomatis.
2.  **Cross-Tabulation**: Menyusun matriks frekuensi kejadian berdasarkan Wilayah Administrasi Kabupaten (`WADMKK`) dan Kawasan Fungsi Hutan (`Prbh_Fungs`).
3.  **Excel Export**: Menyimpan hasil agregasi ke dalam format *spreadsheet* dengan arsitektur *multi-sheet*.
4.  **Diverging Stacked Bar Chart**:
    * **Sumbu Kanan (Positif):** Merepresentasikan klaster titik api yang signifikan (*Hot Spot*), dirender dengan gradasi warna hangat (Oranye hingga Merah Pekat).
    * **Sumbu Kiri (Negatif):** Merepresentasikan klaster titik api yang tidak signifikan/rendah (*Cold Spot*), dirender dengan gradasi warna dingin (Biru).
    * Penguncian *master index* memastikan sumbu Y (daftar kabupaten/hutan) tetap konsisten pada setiap tahun rilis, meskipun tidak ada kejadian yang tercatat pada wilayah tersebut.

## Struktur Direktori Lingkungan Kerja

Skrip ini dikonfigurasi untuk dieksekusi di dalam **Google Colab** dengan memanfaatkan integrasi Google Drive. Pastikan direktori kerja Anda memiliki hierarki sebagai berikut:

```text
/My Drive/Colab Notebooks/Skripsi/NASA-FIRMS Fire (New2)/Titik Panas 2010-2020/
├── Hotspot_2010_Hutan_Adm_Itc.csv      <-- (Data Input Tahunan)
├── Hotspot_2011_Hutan_Adm_Itc.csv
├── ...
├── Hasil_Analisis_Hotspot_2010_2020.xlsx   <-- (Output Excel: Auto-generated)
└── Hasil_Visualisasi_Per_Tahun/            <-- (Output Grafik: Auto-generated)
    ├── Kawasan_Hutan_2010.png
    ├── Wilayah_Administrasi_2010.png
    └── ...

```

## Prasyarat Instalasi

Pastikan pustaka komputasi numerik dan visualisasi berikut telah terinstal:

```bash
pip install pandas numpy matplotlib openpyxl

```

## Panduan Eksekusi

1. Letakkan seluruh file input (CSV) ke dalam folder target di Google Drive.
2. Buka skrip di Google Colab dan pastikan Anda telah memberikan izin *mounting* ke Google Drive.
3. Jalankan sel kode secara berurutan. Skrip akan menangani proses pembersihan observasi yang tidak signifikan (`Gi_Bin = 0`), melakukan tabulasi, dan merender grafik secara iteratif.

## Penulis

**Jariyan Arifudin** Mahasiswa Geografi Lingkungan

Universitas Gadjah Mada (UGM)

## Lisensi & Sitasi

Kode ini didistribusikan di bawah **MIT License**.
Jika Anda menggunakan metode ini untuk penelitian, silakan sitasi repositori ini:

> Arifudin, J. (2026). *Analisis Spasiotemporal Divergensi Hotspot & Coldspot (2010-2020)*. GitHub Repository.
