# Undo / Redo Text Editor

Semester Genap 2025/2026

## Kelompok

- I Gede Anggara Suryantara (2501010013)
- Anak Agung Gede Anom Rangga Pratama (2501010017)

## BAB 1 — Rumusan Masalah dan Solusi

---

### 1.1 Rumusan Masalah

Berdasarkan permasalahan dalam fitur _undo/redo_ pada aplikasi _text editor_, dirumuskan beberapa pertanyaan pada laporan ini sebagai berikut:
1. Bagaimana konsep _stack_ (tumpukan) dengan prinsip LIFO (_Last In_, _First Out_) dapat digunakan untuk mengimplementasikan mekanisme _undo_ dan _redo_ pada sebuah _text editor_ secara efisien?
2. Bagaimana penggunaan dua buah _stack_ secara bersamaan, yaitu _undo stack_ dan _redo stack_, mampu mengelola riwayat perubahan teks sehingga pengguna dapat berpindah maju dan mundur antar kondisi?
3. Bagaimana implementasi _stack_ menggunakan _linked list_ di _Phyton_ mampu menyelesaikan permasalahan nyata pada _text editor_, yaitu mempertahankan histori perubahan teks secara dinamis tanpa batas kapasitas tetap?
   
---

### 1.2 Solusi yang Ditawarkan

Sistem yang dirancang memberikan solusi sebagai berikut:
1. Menggunakan dua _stack_ berbasis _linked list_: _Undo stack_ untuk menyimpan riwayat kondisi teks sebelumnya, dan _redo stack_ untuk menyimpan kondisi yang telah di-_undo_.
2. Setiap kali pengguna mengedit teks, kondisi teks sebelumnya di-_push_ ke _undo stack_, dan _redo stack_ dikosongkan (karena jalur histori berubah).
3. Operasi _undo_ meng-_pop_ dari _undo stack_ dan me-_push_ kondisi sekarang ke _redo stack_, sehingga pengguna dapat kembali ke kondisi sebelumnya.
4. Operasi _redo_ meng-_pop_ dari _redo stack_ dan me-_push_ kondisi sekarang ke _undo stack_, sehingga pengguna dapat maju kembali ke kondisi yang di-_undo_.
5. _Linked list_ digunakan agar kapasitas _stack_ bersifat dinamis, tidak terbatas, dan tidak memerlukan alokasi memori tetap di awal program.
   
---

## BAB 2 — Landasan Teori

---

### 2.1 Pengertian Struktur Data

Struktur data adalah representasi logis dari hubungan antar data yang disimpan dalam memori komputer. Menurut Cormen et al. (2009) dalam _Introduction to ALgorithms_, pemilihan struktur data yang tepat dapat mempercepat waktu eksekusi algoritma secara signifikan. Struktur data liniear seperti _stack_, _queue_, dan _linked list_ banyak digunakan dalam pengembangan perangkat lunak karena kemudahan implementasi dan efisiensinya dalam operasi akses sekuensial.

---

### 2.2 Konsep _Stack_ dan _Queue_

_Stack_ (tumpukan) dan _queue_ (antrean) adalah dua struktur data linier fundamental yang dibedakan oleh cara elemen diakses. _Stack_ adalah sekumpulan elemen di mana penambahan dan penghapusan data hanya terjadi pada satu ujung yang sama, yang dikenal sebagai bagian atas (_top_). Sebaliknya, _queue_ adalah struktur data yang memungkinkan penambahan elemen di satu ujung (_rear_) dan penghapusan di ujung lainnya (_front_). Menurut Weiss (2012) dalam _Data Structures and Algorithm Analysis in C++_, stack dan queue merupakan struktur data linier dengan mekanisme akses LIFO dan FIFO yang banyak digunakan dalam berbagai aplikasi komputasi.

---

### 2.3 Konsep LIFO dan FIFO

Konsep LIFO dan FIFO pada _stack_ dan _queue_ yang membedakan urutan pengolahan data. _Stack_ menerapkan prinsip LIFO (_Last In_, _First Out_), di mana data yang terakhir masuk akan menjadi yang pertama keluar. Sebaliknya, _queue_ menerapkan prinsip FIFO (_First In_, _First Out_), di mana data yang pertama kali masuk akan menjadi yang pertama keluar. Menurut Prata (2020) dalam _C++ Primer Plus_, pemahaman terhadap LIFO dan FIFO sangat penting dalam menentukan apakah sebuah program harus memprioritaskan data terbaru atau data yang paling lama menunggu.

---

### 2.4 Implementasi Menggunakan _Array_ atau _Linked List_

Dalam implementasinya, _stack_ dan _queue_ dapat dibangun menggunakan _array_ maupun _linked list_. Implementasi berbasis _array_ berukuran tetap (_fixed-size_) mengharuskan kapasitas ditentukan di awal, namun memiliki keunggulan dalam hal _locality of reference_ yang mendukung akses memori lebih cepat. Sebaliknya, menurut Goodrich dan Tamassia (2014) dalam _Data Structures and Algorithms in Python_, _linked list_ menggunakan alokasi memori dinamis sehingga tidak memerlukan kapasitas awal yang tetap. Oleh karena itu, _linked list_ lebih fleksibel untuk kasus di mana jumlah data dalam antrean atau tumpukan tidak dapat diprediksi sejak awal.

---

### 2.5 Referensi

-	Cormen, T. H., Leiserson, C. E., Rivest, R. L., & Stein, C. (2009). Introduction to Algorithms (3rd ed.). MIT Press.
-	Goodrich, M. T., & Tamassia, R. (2014). Data Structures and Algorithms in Python. Wiley.
-	Prata, S. (2020). C++ Primer Plus (6th ed.). Addison-Wesley.
- Weiss, M. A. (2012). Data Structures and Algorithm Analysis in C++ (4th ed.). Pearson.

---

## BAB 3 — Desain Sistem dan Implementasi

---

### 3.1 Deskrpsi Sistem

Sistem _undo/redo text editor_ adalah aplikasi berbasis _Phyton_ yang mensimulasikan mekanisme riwayat pengeditan teks. Pengguna dapat menuliskan teks baru, membatalkan perubahan (_undo_), mengulangi perubahan yang dibatalkan (_redo_), melihat elemen teratas _stack_ (_peek_), dan menampilkan seluruh riwayat perubahan (_display_). Sistem menggunakan dua _stack_ berbasis _linked list_ yang bekerja secara bersamaan.

---

### 3.2 Flowchart

---

### 3.3 Pseudocode

---

### 3.4 Implementasi Struktur Data

---

## BAB 4 — Kesimpulan

Berdasarkan hasil perancangan dan implementasi Sistem _Undo/Redo Text Editor_ menggunakan _Stack_ berbasis _Linked List_ di _Python_, dapat ditarik kesimpulan sebagai berikut:

1. Rumusan masalah pertama terjawab: Konsep _Stack_ dengan prinsip LIFO berhasil diterapkan untuk mengimplementasikan mekanisme _Undo_ pada _text editor_. Elemen yang terakhir dimasukkan selalu menjadi yang pertama dibatalkan, sesuai dengan perilaku _Undo_ pada editor nyata seperti _VS Code_ maupun _Microsoft Word_.
2. Rumusan masalah kedua terjawab: Dua _Stack_ yang bekerja sinkron berhasil mengelola navigasi riwayat dua arah. Saat _Undo_ dilakukan, kondisi teks berpindah ke Redo Stack; saat _Redo_ dilakukan, kondisi berpindah kembali ke _Undo Stack_, sepenuhnya sesuai dengan teori struktur data _Stack_.
3. Rumusan masalah ketiga terjawab: Implementasi menggunakan _Linked List_ menjadikan kapasitas _stack_ dinamis tanpa batas. Program telah lulus beberapa test dan menghasilkan _output_ benar pada seluruh skenario pengujian.

