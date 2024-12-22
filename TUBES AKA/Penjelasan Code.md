# <h1 align="center">Sistem Penilaian Popularitas Buku Berdasarkan Riwayat Peminjaman Mahasiswa pada Perpustakaan Telkom University Purwokerto.</h1>
<p align="center"></p>

PENJELASAN CODE

1. Mengimpor Modul yang Diperlukan
   - import time: Untuk mengukur waktu eksekusi kode.
   - import matplotlib.pyplot as plt: Untuk membuat grafik visualisasi.
   - import pandas as pd: Untuk mengolah data dalam format tabel.

2. **Membaca Data dari File CSV**
   - file_path = '/content/data_peminjaman_buku_Perpustakaan_.csv'`: Menentukan lokasi file CSV yang berisi data peminjaman buku.
   - data = pd.read_csv(file_path): Membaca data dari file CSV dan menyimpannya dalam variabel data.
   - Jika terjadi kesalahan saat membaca file, program akan menampilkan pesan error dan berhenti.

3. **Membersihkan Data**
   - data = data.rename(columns=lambda x: x.strip()): Menghapus spasi di awal dan akhir nama kolom.
   - Memeriksa apakah kolom 'Nama Buku' ada dalam data. Jika tidak ada, program akan menampilkan pesan error dan berhenti.
   - data = data.dropna(subset=['Nama Buku']): Menghapus baris yang tidak memiliki nilai pada kolom 'Nama Buku'.
   - data['Nama Buku'] = data['Nama Buku'].str.strip(): Menghapus spasi yang tidak diperlukan di sekitar nama buku.

4. **Menghitung Jumlah Peminjaman Buku**
   - loan_counts = data['Nama Buku'].value_counts(): Menghitung berapa kali setiap buku dipinjam.
   - n_values = loan_counts.values: Mengambil jumlah peminjaman dari loan_counts untuk digunakan dalam perhitungan berikutnya.

5. **Menampilkan Jumlah Peminjaman Buku**
   - Menampilkan nama buku dan jumlah peminjamannya dalam format:
     ```
     Nama Buku: X kali dipinjam
     ```

6. **Perbandingan Waktu Eksekusi: Pendekatan Iteratif vs. Rekursif**
   - **Pendekatan Iteratif**:
     - Menggunakan metode value_counts() untuk menghitung jumlah peminjaman buku secara langsung.
     - Mengukur waktu yang dibutuhkan untuk proses ini.
   - **Pendekatan Rekursif**:
     - Membuat fungsi calculate_popularity_recursive() yang menghitung jumlah peminjaman buku dengan cara memanggil dirinya sendiri (rekursi).
     - Mengukur waktu yang dibutuhkan untuk proses ini.

7. **Menyimpan Hasil Perbandingan**
   - Menyimpan hasil perbandingan waktu eksekusi dan total peminjaman buku dalam sebuah tabel yang berisi:
     - n: Jumlah buku yang dipinjam pada iterasi tertentu.
     - Recursive Time (s): Waktu eksekusi untuk pendekatan rekursif.
     - Iterative Time (s): Waktu eksekusi untuk pendekatan iteratif.
     - Total Iterative: Total jumlah peminjaman berdasarkan pendekatan iteratif.
     - Total Recursive: Total jumlah peminjaman berdasarkan pendekatan rekursif.

8. **Membuat Grafik Perbandingan Waktu Eksekusi**
   - Menggunakan matplotlib untuk membuat grafik yang membandingkan waktu eksekusi antara pendekatan iteratif dan rekursif.
   - Grafik ini membantu visualisasi perbedaan kinerja antara kedua pendekatan.

9. **Menampilkan Tabel Hasil Perbandingan**
   - Menampilkan tabel yang berisi hasil perbandingan waktu eksekusi dan total peminjaman buku dari kedua pendekatan.

10. **Evaluasi Efisiensi**
    - Menghitung rata-rata waktu eksekusi untuk kedua pendekatan.
    - Menentukan pendekatan mana yang lebih efisien berdasarkan waktu rata-rata eksekusi.

**Ringkasan**
Kode ini membandingkan dua metode (iteratif dan rekursif) dalam menghitung popularitas buku yang dipinjam dari data CSV. Hasilnya mencakup:
1. Perhitungan jumlah peminjaman buku.
2. Waktu eksekusi dari kedua metode.
3. Grafik perbandingan waktu eksekusi.
4. Tabel yang menunjukkan hasil analisis waktu eksekusi.
5. Evaluasi efisiensi berdasarkan waktu rata-rata eksekusi. 
