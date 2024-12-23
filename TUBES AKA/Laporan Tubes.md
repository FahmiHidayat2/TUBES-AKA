# <h1 align="center">Sistem Penilaian Buku Berdasarkan Riwayat Peminjaman di Perpustakaan.</h1>
<p align="center">

Nama Kelompok : Fahmi Hidayat | Mikhael Setia Budi
   
NIM      : 2311110063 | 2311110033

Kelas     : S1SD-04-B </p>

### A Deskripsi Studi Kasus Permasalahan 
   Pada era digital saat ini, sistem perpustakaan sering kali memiliki banyak data 
peminjaman buku yang dapat dimanfaatkan untuk menganalisis preferensi pengguna. Kami 
mengusulkan studi ini dengan judul "Sistem Penilaian Popularitas Buku Berdasarkan 
Riwayat Peminjaman Mahasiswa pada Perpustakaan Telkom University Purwokerto" 
karena judul tersebut unik dan jarang digunakan dalam penelitian serupa. Permasalahan 
yang kami coba selesaikan adalah bagaimana menentukan buku paling populer berdasarkan 
riwayat peminjaman secara efektif dengan menggunakan dua pendekatan algoritmik: 
iteratif dan rekursif. 

   Iteratif dan rekursif adalah sebuah algoritma yang memiliki ciri yang sama yaitu 
mengulangi langkah-langkah yang diinginkan. Namun, rekursif agak berbeda dari iterasi. 
Rekursif adalah sebuah algoritma yang berisi pemanggilan dirinya sendiri sehingga 
menghasilkan looping. Harus ada batasan di dalam rekursif sehingga looping dapat 
dibatalkan, jika tidak maka akan terjadi infinity loop dan dapat menyebabkan memori 
penuh. [1] Dengan melakukan analisis ini, diharapkan dapat memberikan wawasan kepada 
perpustakaan untuk mengetahui buku mana saja yang disukai oleh mahasiswa. 

### B Deskripsi Dua Algoritma yang Dipilih untuk Menyelesaikan Permasalahan 
#### a) Algoritma Iteratif 
Algoritma iteratif menghitung jumlah peminjaman setiap buku menggunakan 
metode perulangan secara langsung pada dataset. Pendekatan ini mengakses 
setiap data buku dan menambahkan jumlah peminjaman ke dalam struktur data 
yang sesuai, seperti dictionary atau dataframe. Kelebihan utama dari algoritma 
iteratif adalah efisiensi dan kemudahan implementasi dalam menangani dataset 
berukuran besar. 
#### b) Algoritma Rekursif 
Algoritma rekursif menghitung jumlah peminjaman buku dengan memecah 
dataset menjadi submasalah lebih kecil dan memprosesnya secara berulang 
menggunakan fungsi yang memanggil dirinya sendiri. Pendekatan ini memiliki 
sifat deklaratif yang memungkinkan solusi lebih intuitif untuk masalah tertentu. 
Namun, algoritma rekursif dapat menghadapi keterbatasan efisiensi dan risiko 
stack overflow pada dataset yang sangat besar.

### C Grafik Perbandingan Running Time 
Berikut adalah grafik perbandingan waktu eksekusi antara algoritma iteratif dan rekursif pada 
berbagai ukuran dataset:
![image](https://github.com/user-attachments/assets/b8c02ea1-11e1-4061-a33e-5ccde85bbfbe)
Grafik menunjukkan bahwa waktu eksekusi algoritma rekursif lebih cepat dibandingkan 
algoritma iteratif berdasarkan waktu rata-rata pada dataset ini. 

#### D Analisis Perbandingan Kedua Algoritma 
Data Ringkasan Eksekusi: 

<img width="452" alt="image" src="https://github.com/user-attachments/assets/de37bf64-0b4c-47d9-a7da-e5d295eda035" />

Analisis: 

#### 1. Algoritma Rekursif lebih cepat secara rata-rata dibandingkan algoritma iteratif pada 
dataset ini, yang disebabkan oleh ukuran dataset yang relatif kecil sehingga overhead 
pemanggilan rekursi tidak signifikan. 
#### 2. Algoritma Iteratif cenderung memiliki waktu eksekusi yang lebih tinggi karena sifat 
perulangan yang linear. 

### Kompleksitas Waktu
#### 1. Pendekatan Iteratif:
   - Total kompleksitasnya adalah (O(n)), dengan (n) sebagai total elemen dataset.

#### 2. Pendekatan Rekursif:.
   - Total kompleksitasnya adalah (O(n)), tetapi lebih lambat karena overhead stack rekursi.
### Kesimpulan: 
Penelitian ini menunjukkan bahwa analisis popularitas buku dapat dilakukan secara efektif 
menggunakan algoritma iteratif dan rekursif. Algoritma iteratif lebih efisien untuk dataset 
besar, sedangkan algoritma rekursif lebih cepat untuk dataset kecil meskipun memiliki 
keterbatasan pada dataset besar. Hasil analisis waktu eksekusi menunjukkan algoritma rekursif 
lebih cepat rata-rata pada dataset kecil. Dengan demikian, perpustakaan dapat memanfaatkan 
algoritma yang sesuai untuk mengidentifikasi tren peminjaman buku, memahami preferensi 
pengguna, dan mengelola koleksi secara lebih efisien. 
### Reference : 
[1] E. Lutfina dan F. L. Ramadhan, “Perbandingan Kinerja Metode Iteratif dan Metode 
Rekursif dalam Algoritma Binary Search,” Semin. Nas. APTIKOM, hal. 2019, 2019.
