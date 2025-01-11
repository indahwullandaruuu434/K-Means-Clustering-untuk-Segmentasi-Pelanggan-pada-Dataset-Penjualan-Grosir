# K-Means Clustering untuk Segmentasi Pelanggan pada Dataset Penjualan Grosir

Kode ini mengimplementasikan algoritma K-Means untuk mengelompokkan pelanggan berdasarkan kebiasaan belanja mereka pada dataset penjualan grosir.

## Deskripsi

Program ini menganalisis data pengeluaran tahunan pelanggan pada berbagai kategori produk untuk mengidentifikasi segmen pelanggan yang berbeda. Algoritma K-Means digunakan untuk mengelompokkan pelanggan berdasarkan kesamaan pola pembelian mereka.

## Dataset

Dataset yang digunakan adalah **Wholesale customers Data Set** yang tersedia di UCI Machine Learning Repository.

*   **Sumber:** [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/Wholesale+customers)
*   **File:** `grosir.csv`
*   **Deskripsi:** Dataset ini berisi data pengeluaran tahunan dalam satuan moneter (m.u.) untuk berbagai produk yang dibeli oleh beragam pelanggan dari distributor grosir.
*   **Fitur:**
    *   `Channel`: Saluran distribusi (Horeca (Hotel/Restaurant/Cafe) atau Retail).
    *   `Region`: Wilayah geografis pelanggan.
    *   `Fresh`: Pengeluaran tahunan untuk produk segar.
    *   `Milk`: Pengeluaran tahunan untuk produk susu.
    *   `Grocery`: Pengeluaran tahunan untuk produk bahan makanan.
    *   `Frozen`: Pengeluaran tahunan untuk produk beku.
    *   `Detergents_Paper`: Pengeluaran tahunan untuk deterjen dan produk kertas.
    *   `Delicatessen`: Pengeluaran tahunan untuk produk makanan siap saji.

## Langkah-langkah

1.  **Import Library:** Mengimpor library Python yang diperlukan:
    *   `pandas` untuk manipulasi data.
    *   `sklearn.cluster.KMeans` untuk algoritma K-Means.
    *   `sklearn.preprocessing.StandardScaler` untuk normalisasi data.
    *   `sklearn.decomposition.PCA` untuk reduksi dimensi (visualisasi).
    *   `matplotlib.pyplot` dan `seaborn` untuk visualisasi.

2.  **Memuat Dataset:** Membaca file `grosir.csv` menggunakan pandas.

3.  **Preprocessing Data:**
    *   Menghapus kolom `Channel` dan `Region` karena fokus analisis adalah pada pola belanja berdasarkan produk.
    *   Melakukan normalisasi data menggunakan `StandardScaler` agar setiap fitur memiliki rata-rata 0 dan standar deviasi 1.

4.  **Menentukan Jumlah Cluster (k) Optimal:**
    *   Menggunakan metode Elbow untuk menentukan jumlah cluster yang optimal. Metode ini menghitung *inertia* (jumlah kuadrat jarak sampel ke pusat cluster terdekat) untuk berbagai nilai k. Grafik *inertia* vs. k akan membentuk "siku", dan titik siku tersebut sering dianggap sebagai nilai k yang baik.

5.  **Implementasi K-Means:**
    *   Menerapkan algoritma K-Means dengan jumlah cluster yang dipilih (misalnya k=3 berdasarkan metode Elbow).

6.  **Menambahkan Label Cluster:** Menambahkan label cluster yang dihasilkan oleh K-Means ke data asli.

7.  **Visualisasi:**
    *   Menggunakan Principal Component Analysis (PCA) untuk mereduksi dimensi data menjadi 2 komponen utama agar dapat divisualisasikan dalam plot 2D.
    *   Membuat scatter plot untuk menampilkan hasil pengelompokan, di mana setiap titik mewakili pelanggan dan diwarnai berdasarkan clusternya.

8.  **Analisis Karakteristik Setiap Cluster:**
    *   Menghitung rata-rata pengeluaran untuk setiap kategori produk per cluster.
    *   Membuat boxplot untuk memvisualisasikan distribusi pengeluaran untuk setiap kategori produk di setiap cluster.

## Menjalankan Kode

1.  **Prasyarat:**
    *   Python 3.x
    *   Install library yang diperlukan:
        ```bash
        pip install pandas scikit-learn matplotlib seaborn
        ```

2.  **Dataset:**
    *   Unduh dataset `grosir.csv` pada yang sudah di sediakan 

3.  **Eksekusi:**
    *   Simpan script Python dan dataset `grosir.csv` dalam direktori yang sama.
    *   Jalankan script Python dari terminal:
        ```bash
        python nama_file.py
        ```
        (Ganti `nama_file.py` dengan nama file script Anda)

## Hasil

*   **Elbow Method Plot:** Grafik yang menunjukkan nilai *inertia* untuk berbagai nilai k, membantu menentukan jumlah cluster yang optimal.
*   **Scatter Plot:** Visualisasi hasil clustering dalam 2 dimensi menggunakan PCA.
*   **Tabel Rata-Rata Pengeluaran per Cluster:** Menampilkan rata-rata pengeluaran untuk setiap kategori produk di setiap cluster, memberikan informasi tentang karakteristik belanja masing-masing segmen pelanggan.
*   **Boxplot:** Visualisasi distribusi pengeluaran untuk setiap kategori produk di setiap cluster, membantu memahami perbedaan pola belanja antar cluster.

## Kesimpulan

Program ini berhasil mengelompokkan pelanggan berdasarkan kebiasaan belanja mereka menggunakan algoritma K-Means. Hasil analisis dapat digunakan untuk memahami segmen pelanggan yang berbeda dan menyesuaikan strategi pemasaran yang sesuai untuk masing-masing segmen.

