# Jobsheet Review Use Case Diagram: Jadwal Kuliah (P02)

## Tujuan

1. Memahami elemen dasar use case diagram, yaitu aktor, use case, boundary sistem, dan asosiasi.
2. Mengidentifikasi aktor dan use case dari skenario pengelolaan serta penayangan jadwal kuliah.
3. Meninjau kesesuaian hubungan antara aktor dan use case pada diagram yang dibuat.
4. Menentukan perbaikan agar diagram sesuai dengan skenario dan kaidah UML.

## Dasar Teori

**Use case diagram** adalah diagram UML yang menggambarkan fungsi sistem dari sudut pandang pengguna. Diagram ini menunjukkan siapa yang berinteraksi dengan sistem dan fungsi apa yang disediakan sistem bagi mereka.

**Elemen utama:**

- **Aktor**: pihak di luar sistem (orang, perangkat, atau sistem lain) yang berinteraksi dengan sistem. Aktor digambarkan di luar boundary sistem.
- **Use case**: unit fungsi yang memberikan hasil bernilai bagi aktor, digambarkan sebagai elips dengan nama berbentuk kata kerja (misalnya *Lihat Jadwal Kuliah*).
- **Boundary sistem**: kotak yang membatasi use case yang menjadi cakupan sistem.
- **Asosiasi**: garis solid yang menghubungkan aktor dengan use case yang dijalankannya.

**Kaidah penting:**

1. Setiap use case harus terhubung dengan minimal satu aktor yang menjalankannya.
2. Aktor ditentukan berdasarkan peran, bukan individu tertentu.
3. Hubungan aktor dengan use case harus mencerminkan hak dan peran aktor yang disebut dalam skenario.
4. Diagram harus konsisten dengan skenario, baik dalam istilah aktor maupun fungsi.

## Hasil Review

| No. | Temuan | Perbaikan yang diperlukan | Alasan |
|---:|---|---|---|
| 1 | Aktor **Mahasiswa** terhubung dengan **Kelola Jadwal Kuliah** | Hubungkan Mahasiswa dengan **Lihat Jadwal Kuliah** | Mahasiswa hanya berperan untuk melihat jadwal kuliah |
| 2 | **Kelola Jadwal Kuliah** belum memiliki aktor | Tambahkan aktor **Admin Akademik** dan hubungkan dengan **Kelola Jadwal Kuliah** | Admin Akademik merupakan pihak yang bertugas mengelola jadwal |
| 3 | **Lihat Jadwal Kuliah** belum memiliki hubungan dengan aktor | Hubungkan **Mahasiswa → Lihat Jadwal Kuliah** | Setiap use case harus memiliki hubungan dengan aktor yang menjalankannya |
| 4 | Aktor Admin Akademik tidak terdapat pada diagram | Tambahkan aktor **Admin Akademik** di luar boundary sistem | Skenario menyebutkan adanya Admin Akademik sebagai pengelola jadwal |

## Kesimpulan

Hasil review menunjukkan bahwa diagram awal memiliki kesalahan pada hubungan aktor dan use case, bukan pada daftar fungsinya. Mahasiswa salah dihubungkan dengan *Kelola Jadwal Kuliah*, padahal perannya hanya melihat jadwal. Aktor *Admin Akademik* belum ada, sehingga *Kelola Jadwal Kuliah* tidak memiliki aktor, dan *Lihat Jadwal Kuliah* tidak terhubung dengan aktor mana pun.

Setelah perbaikan, diagram memuat dua aktor di luar boundary sistem: **Mahasiswa → Lihat Jadwal Kuliah** dan **Admin Akademik → Kelola Jadwal Kuliah**. Dengan begitu setiap use case memiliki aktor, dan pembagian peran sesuai dengan skenario. Review ini menegaskan bahwa ketepatan asosiasi dan kelengkapan aktor perlu diperiksa langsung terhadap skenario sebelum diagram dianggap benar.