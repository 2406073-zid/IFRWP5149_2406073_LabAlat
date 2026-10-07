| No. | Temuan | Perbaikan yang diperlukan | Alasan |
|---:|---|---|---|
| 1 |  | Hubungkan Mahasiswa dengan **Lihat Jadwal Kuliah** | Mahasiswa hanya berperan untuk melihat jadwal kuliah |
| 2 | **Kelola Jadwal Kuliah** belum memiliki aktor | Tambahkan aktor **Admin Akademik** dan hubungkan dengan **Kelola Jadwal Kuliah** | Admin Akademik merupakan pihak yang bertugas mengelola jadwal |
| 3 | **Lihat Jadwal Kuliah** belum memiliki hubungan dengan aktor | Hubungkan **Mahasiswa → Lihat Jadwal Kuliah** | Setiap use case harus memiliki hubungan dengan aktor yang menjalankannya |
| 4 | Aktor Admin Akademik tidak terdapat pada diagram | Tambahkan aktor **Admin Akademik** di luar boundary sistem | Skenario menyebutkan adanya Admin Akademik sebagai pengelola jadwal |