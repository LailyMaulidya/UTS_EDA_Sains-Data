# EDA Dataset Ultrasound Vena

Repository ini berisi kode dan hasil *Exploratory Data Analysis* (EDA) pada citra ultrasound untuk mendukung penelitian **Estimasi Kedalaman Vena Berbasis Ultrasound Menggunakan Deep Learning untuk Sistem Pengambilan Darah Otomatis**.

## Struktur Repository

| Folder | Deskripsi |
|---|---|
| `Hasil_Analisis_Sensitivitas/` | Hasil analisis sensitivitas terhadap kandidat *outlier*. |
| `Hasil_EDA_Awal/` | Hasil EDA sebelum pelabelan. |
| `Hasil_EDA_Setelah_Labelling/` | Hasil EDA pada citra setelah pelabelan. |
| `Hasil_Hipotesis1/` | Hasil pengujian hipotesis pertama. |
| `Hasil_Hipotesis2/` | Hasil pengujian hipotesis kedua. |
| `Hasil_Hipotesis3/` | Hasil pengujian hipotesis ketiga. |
| `Hasil_Perbandingan_Preprocessing/` | Hasil perbandingan karakteristik citra sebelum dan sesudah *preprocessing*. |
| `Kode/` | Notebook Python dan dependensi untuk menjalankan analisis. |
| `Mentah/` | Folder citra ultrasound mentah. |
| `SesudahLabel/` | Folder citra yang telah diberi label. |
| `SesudahPreprocessing/` | Folder citra setelah tahap *preprocessing*. |

## Teknologi

- Python
- Jupyter Notebook
- OpenCV
- NumPy
- Pandas
- Matplotlib
- SciPy

## Tahapan Analisis

1. Pemeriksaan kualitas dan struktur dataset.
2. Analisis resolusi dan intensitas citra.
3. Analisis statistik dan pengujian hipotesis.
4. Deteksi kandidat *outlier* dan analisis sensitivitas.
5. Analisis karakteristik citra setelah pelabelan.
6. Perbandingan karakteristik citra sebelum dan sesudah *preprocessing*.

## Menjalankan Kode

Buka folder `Kode/`, instal dependensi dari `requirements.txt`, kemudian jalankan notebook `EDA.ipynb` menggunakan Jupyter Notebook atau JupyterLab.

Hasil analisis digunakan sebagai dasar untuk merencanakan *preprocessing* dan pengembangan model segmentasi vena berbasis *deep learning*.

**Catatan:** EDA menggambarkan karakteristik dataset dan belum membuktikan kinerja segmentasi vena maupun akurasi estimasi kedalaman
