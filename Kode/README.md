# Kode UTS Sains Data – Tindak Lanjut EDA (Estimasi Kedalaman Vena)

Penulis: Laily Maulidya Purwanti (NRP 1226800025)

## Struktur folder
```
kode/
├── config.py                          # jalur data & parameter (ubah di sini)
├── 01_eda_citra.py                    # EDA citra mentah + hash duplikat + frame gelap
├── 02_eda_label_sensitivitas.py       # statistik label YOLO-seg + sensitivitas rasio (eksak)
├── 03_uji_hipotesis.py                # uji asumsi + H1/H2 dari CSV
├── 04_preprocessing_sebelum_sesudah.py# resize & CLAHE pada citra yang sama + uji berpasangan (H3)
├── 05_analisis_dari_ringkasan.py      # H1, H2, S1-S3 dari angka ringkasan (TANPA data mentah)
├── requirements.txt
└── data/                              # TIDAK disertakan; letakkan data di sini
    ├── dataset_extract/dataset_1 ... dataset_26/
    └── labeled/{images,labels}/
```

## Instalasi
```
pip install -r requirements.txt
```

## Cara menjalankan
1. **Tanpa data mentah:** `python 05_analisis_dari_ringkasan.py` -> mencetak angka H1, H2, S1-S3 yang
   dipakai di laporan dan menyimpan CSV di `keluaran/`. Skrip ini bisa dijalankan siapa pun.
2. **Dengan data mentah:** letakkan data sesuai `config.py`, lalu jalankan berurutan
   `01 -> 02 -> 03 -> 04`. Skrip 03 membaca `keluaran/hasil_eda_citra.csv` dari skrip 01.
3. Di Google Colab, ubah `DATASET_DIR` dan `OUT_DIR` di `config.py` ke jalur Drive.

## Keluaran
- `keluaran/hasil_eda_citra.csv`, `frame_intensitas_rendah_untuk_tinjauan.csv`
- `keluaran/statistik_label.csv`, `sensitivitas_rasio_eksak.csv`, `kandidat_pencilan_rasio.csv`
- `keluaran/preprocessing_sebelum_sesudah.csv`
- `keluaran/ringkasan_per_dataset.csv`, `sensitivitas_rasio_rekonstruksi.csv`

## Status pengujian (jujur)
- `05_*` dijalankan; angka laporan berasal dari skrip ini.
- `01`-`04` **diuji pada data sintetis** hanya untuk memastikan tidak ada error; **belum dijalankan pada data asli**.
  Angka yang dihasilkan pada data asli harus diperiksa terhadap laporan sebelum dikumpulkan.
- Sensitivitas rasio (S3) pada laporan adalah **perkiraan dari histogram slide 20**; versi eksak = keluaran skrip 02.

## Parameter yang bisa diubah untuk demonstrasi lisan
`IQR_K`, `LOW_INTENSITY_CUTOFF`, `IMG_SIZE` (config.py); `clipLimit`/`tileGridSize` CLAHE dan ukuran sampel (skrip 04).
