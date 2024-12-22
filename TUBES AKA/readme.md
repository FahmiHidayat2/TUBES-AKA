# <h1 align="center">Sistem Penilaian Popularitas Buku Berdasarkan Riwayat Peminjaman Mahasiswa pada Perpustakaan Telkom University Purwokerto.</h1>
<p align="center"></p>
# PENJELASAN CODE

### 1. **Import Libraries**
   - `import time`: Mengimpor modul `time` yang digunakan untuk mengukur waktu eksekusi dari kedua pendekatan (iteratif dan rekursif).
   - `import matplotlib.pyplot as plt`: Mengimpor modul `matplotlib.pyplot` untuk membuat grafik visualisasi.
   - `import pandas as pd`: Mengimpor modul `pandas` yang digunakan untuk manipulasi dan analisis data, terutama untuk mengolah data CSV.

### 2. **Membaca File CSV**
   - `file_path = '/content/data_peminjaman_buku_Perpustakaan_.csv'`: Menentukan path file CSV yang berisi data peminjaman buku.
   - `data = pd.read_csv(file_path)`: Membaca file CSV dan menyimpannya ke dalam variabel `data`.
   - `except Exception as e`: Menangani error jika terjadi kesalahan saat membaca file, seperti file tidak ditemukan atau format yang tidak valid.
   - `data = data.rename(columns=lambda x: x.strip())`: Membersihkan nama kolom dengan menghilangkan spasi di awal dan akhir nama kolom.

### 3. **Pemeriksaan Kolom dan Pembersihan Data**
   - `if 'Nama Buku' not in data.columns`: Mengecek apakah kolom 'Nama Buku' ada dalam data, jika tidak maka akan muncul pesan error.
   - `data = data.dropna(subset=['Nama Buku'])`: Menghapus baris yang memiliki nilai NaN pada kolom 'Nama Buku'.
   - `data['Nama Buku'] = data['Nama Buku'].str.strip()`: Menghapus spasi yang tidak diperlukan di sekitar nilai dalam kolom 'Nama Buku'.

### 4. **Menghitung Jumlah Buku yang Dipinjam**
   - `loan_counts = data['Nama Buku'].value_counts()`: Menghitung jumlah buku yang dipinjam berdasarkan nama buku dan menyimpannya dalam variabel `loan_counts`.
   - `n_values = loan_counts.values`: Mengambil nilai (jumlah peminjaman) dari `loan_counts` yang akan digunakan untuk iterasi.

### 5. **Menampilkan Jumlah Buku yang Dipinjam**
   - Dengan iterasi menggunakan `for`, kode ini menampilkan jumlah buku yang dipinjam berdasarkan nama buku, dengan format:
     ```
     Nama Buku: X kali dipinjam
     ```

### 6. **Pendekatan Iteratif dan Rekursif untuk Menghitung Popularitas Buku**
   - **Pendekatan Iteratif**:
     - Data dipangkas hingga `n` (jumlah buku yang dipinjam) dan diolah menggunakan `value_counts()` untuk menghitung jumlah buku yang dipinjam dengan cara iterasi.
     - Waktu eksekusi untuk pendekatan iteratif diukur menggunakan `time.time()` sebelum dan setelah eksekusi.
   - **Pendekatan Rekursif**:
     - Fungsi `calculate_popularity_recursive()` dibuat untuk menghitung jumlah peminjaman buku secara rekursif.
     - Fungsi ini mengambil data dalam bentuk list dan menghitung popularitas buku dengan menambahkan jumlah setiap buku ke dalam dictionary `book_counts`.
     - Waktu eksekusi untuk pendekatan rekursif juga diukur.

### 7. **Menyimpan Hasil Eksekusi**
   - Hasil dari perhitungan waktu eksekusi dan total jumlah buku yang dipinjam disimpan dalam list `results`, yang terdiri dari:
     - `n`: Jumlah buku yang dipinjam pada iterasi tertentu.
     - `Recursive Time (s)`: Waktu eksekusi untuk pendekatan rekursif.
     - `Iterative Time (s)`: Waktu eksekusi untuk pendekatan iteratif.
     - `Total Iterative`: Total jumlah peminjaman berdasarkan pendekatan iteratif.
     - `Total Recursive`: Total jumlah peminjaman berdasarkan pendekatan rekursif.

### 8. **Membuat Grafik Perbandingan Waktu Eksekusi**
   - `results_df = pd.DataFrame(results)`: Mengubah list `results` menjadi DataFrame untuk memudahkan manipulasi data.
   - `plt.figure(figsize=(10, 6))`: Menentukan ukuran grafik.
   - `plt.plot(...)`: Membuat grafik perbandingan antara waktu eksekusi pendekatan rekursif dan iteratif terhadap jumlah buku yang dipinjam (`n`).
   - `plt.xlabel`, `plt.ylabel`, `plt.title`: Menambahkan label pada sumbu X dan Y, serta judul grafik.
   - `plt.legend()`: Menampilkan legenda pada grafik.
   - `plt.grid()`: Menambahkan grid pada grafik untuk memudahkan pembacaan.
   - `plt.tight_layout()`: Menyesuaikan layout grafik agar lebih rapi.

### 9. **Menampilkan Tabel Hasil Eksekusi**
   - `print(results_df.to_string(index=False))`: Menampilkan tabel hasil perhitungan yang mencakup waktu eksekusi untuk pendekatan iteratif dan rekursif serta total buku yang dipinjam.

### 10. **Membandingkan Efisiensi**
   - `average_recursive_time = results_df['Recursive Time (s)'].mean()`: Menghitung rata-rata waktu eksekusi untuk pendekatan rekursif.
   - `average_iterative_time = results_df['Iterative Time (s)'].mean()`: Menghitung rata-rata waktu eksekusi untuk pendekatan iteratif.
   - Berdasarkan rata-rata waktu, kode akan mencetak pendekatan mana yang lebih efektif, apakah iteratif atau rekursif, berdasarkan waktu rata-rata eksekusi.

### Ringkasan
Kode ini membandingkan dua pendekatan (iteratif dan rekursif) dalam menghitung popularitas buku yang dipinjam dari data CSV. Hasilnya mencakup:
1. Perhitungan jumlah buku yang dipinjam.
2. Waktu eksekusi dari kedua pendekatan.
3. Grafik perbandingan waktu eksekusi.
4. Tabel yang menunjukkan hasil analisis waktu eksekusi.
5. Evaluasi efisiensi berdasarkan rata-rata waktu eksekusi.
