# skenario
Tugas ini berbeda dari tugas pertemuan sebelumnya. Tugas Pertemuan 2 
adalah jadwal kuliah dan tugas Pertemuan 3 adalah pengajuan KRS. Tugas 
Pertemuan 4 adalah layanan hasil studi, dengan teknik generalization dan 
collaboration yang sama seperti studi kasus, tetapi diterapkan pada skenario 
baru tanpa contoh jawaban. 
Skenario tugas berikut fiktif untuk praktikum dan berbeda dari tugas 
Pertemuan 2 (jadwal kuliah) dan Pertemuan 3 (pengajuan KRS). 
Mahasiswa dan dosen sama-sama merupakan Civitas Akademika yang 
dapat melihat kalender akademik. Dosen menginput nilai mata kuliah yang 
diampunya setelah masa perkuliahan berakhir. Mahasiswa melihat Kartu 
Hasil Studi (KHS) untuk semester yang nilainya sudah dipublikasikan. Admin 
Akademik mengelola data mahasiswa: menambah data mahasiswa baru, 
mengubah data mahasiswa, dan menghapus data mahasiswa. Dua use case 
utama, Input Nilai Mata Kuliah dan Lihat KHS, ditunjukkan realisasinya oleh 
collaboration yang bersesuaian.

# Kebutuhan Sistem
| ID | Kebutuhan |
|---|---|
| SIA-R01 | Sistem menyediakan fitur untuk melihat kalender akademik bagi mahasiswa dan dosen. |
| SIA-R02 | Sistem menyediakan fitur bagi dosen untuk menginput nilai mata kuliah yang diampunya setelah masa perkuliahan berakhir. |
| SIA-R03 | Sistem menyediakan fitur bagi mahasiswa untuk melihat Kartu Hasil Studi (KHS) berdasarkan semester yang nilainya sudah dipublikasikan. |
| SIA-R04 | Sistem menampilkan KHS mahasiswa hanya untuk semester yang nilainya sudah dipublikasikan. |
| SIA-R05 | Sistem menyediakan fitur bagi Admin Akademik untuk menambahkan data mahasiswa baru. |
| SIA-R06 | Sistem menyediakan fitur bagi Admin Akademik untuk mengubah data mahasiswa. |
| SIA-R07 | Sistem menyediakan fitur bagi Admin Akademik untuk menghapus data mahasiswa. |
| SIA-R08 | Sistem memvalidasi bahwa dosen hanya dapat menginput nilai mata kuliah yang diampunya. |
| SIA-R09 | Sistem menyimpan nilai mata kuliah yang telah diinput dosen. |
| SIA-R10 | Sistem menunjukkan realisasi use case Input Nilai Mata Kuliah dan Lihat KHS melalui collaboration yang sesuai. |

# Batas dan Aturan Sistem
• Kode kebutuhan dimulai dari SIA-R07 agar SIA-R01 dan SIA-R02 
(Pertemuan 2) serta SIA-R03 sampai SIA-R06 (Pertemuan 3) tetap 
mempunyai identitas berbeda. 
• Pengguna telah terautentikasi dan memiliki hak akses sesuai peran. 
• Kalender akademik pada tugas ini adalah agenda resmi institusi (awal 
semester, batas KRS, masa ujian, dan sejenisnya); jangan 
menyamakannya dengan jadwal kuliah pada Pertemuan 2. 
• Nilai hanya dapat diinput oleh dosen pengampu mata kuliah tersebut. Nilai 
yang diinput belum terpublikasi sebelum dinyatakan resmi oleh ketentuan 
tugas ini: KHS hanya menampilkan nilai yang sudah dipublikasikan. 
• Hapus Data Mahasiswa hanya untuk mahasiswa yang tidak memiliki data 
akademik aktif. Ketentuan ini fiktif untuk latihan. 
• Pengajuan KRS tetap digambar sebagai bagian diagram kumulatif dari 
Pertemuan 3. Pembayaran dan perancangan basis data berada di luar 
tugas ini.

# Tentukan Aktor
| Aktor | Kedudukan | Tujuan terhadap Sistem |
|---|---|---|
| Civitas Akademika | Aktor umum (*generalization*) | Berperan sebagai aktor umum yang memiliki akses untuk melihat kalender akademik. |
| Mahasiswa | Turunan dari Civitas Akademika | Melihat kalender akademik dan Kartu Hasil Studi (KHS) untuk semester yang nilainya sudah dipublikasikan. |
| Dosen | Turunan dari Civitas Akademika | Melihat kalender akademik dan menginput nilai mata kuliah yang diampunya setelah masa perkuliahan berakhir. |
| Admin Akademik | Aktor mandiri | Mengelola data mahasiswa, meliputi menambah, mengubah, dan menghapus data mahasiswa. |

# Katalog Use case
| ID | Nama Use Case | Peran dalam Model | Sumber Kebutuhan |
|---|---|---|---|
| SIA-UC01 | Lihat Kalender Akademik | Use case yang dapat dilakukan oleh Civitas Akademika, yaitu mahasiswa dan dosen. | SIA-R01 |
| SIA-UC02 | Input Nilai Mata Kuliah | Use case utama yang dilakukan dosen untuk memasukkan nilai mata kuliah yang diampunya setelah masa perkuliahan berakhir. | SIA-R02, SIA-R08, SIA-R09 |
| SIA-UC03 | Lihat KHS | Use case utama yang dilakukan mahasiswa untuk melihat Kartu Hasil Studi pada semester yang nilainya sudah dipublikasikan. | SIA-R03, SIA-R04 |
| SIA-UC04 | Kelola Data Mahasiswa | Use case yang dilakukan Admin Akademik untuk mengelola data mahasiswa. | SIA-R05, SIA-R06, SIA-R07 |
| SIA-UC05 | Tambah Data Mahasiswa | Use case khusus untuk menambahkan data mahasiswa baru. | SIA-R05 |
| SIA-UC06 | Ubah Data Mahasiswa | Use case khusus untuk mengubah data mahasiswa yang telah tersimpan. | SIA-R06 |
| SIA-UC07 | Hapus Data Mahasiswa | Use case khusus untuk menghapus data mahasiswa. | SIA-R07 |
| SIA-UC08 | Validasi Mata Kuliah yang Diampu | Use case untuk memastikan dosen hanya menginput nilai pada mata kuliah yang diampunya. | SIA-R08 |
| SIA-UC09 | Simpan Nilai Mata Kuliah | Use case untuk menyimpan nilai yang telah diinput dosen. | SIA-R09 |
| SIA-UC10 | Periksa Publikasi Nilai | Use case untuk memeriksa apakah nilai mahasiswa sudah dipublikasikan sebelum KHS ditampilkan. | SIA-R04 |
| SIA-UC11 | Tampilkan KHS | Use case untuk menampilkan Kartu Hasil Studi berdasarkan data nilai yang sudah dipublikasikan. | SIA-R03, SIA-R04 |
| SIA-UC12 | Tampilkan Peringatan Nilai Belum Dipublikasikan | Use case ekstensi yang menampilkan pemberitahuan jika nilai pada semester yang dipilih belum dipublikasikan. | SIA-R04 |
| SIA-UC13 | Tampilkan Pesan Kesalahan Input Nilai | Use case ekstensi yang menampilkan pesan kesalahan jika nilai yang dimasukkan tidak valid. | SIA-R08 |

# Relasi Use case
| ID | Use Case Sumber | Jenis Relasi | Use Case Tujuan | Keterangan |
|---|---|---|---|---|
| SIA-REL01 | Civitas Akademika | Association | Lihat Kalender Akademik | Civitas Akademika dapat melihat kalender akademik. |
| SIA-REL02 | Mahasiswa | Generalization | Civitas Akademika | Mahasiswa mewarisi peran umum Civitas Akademika. |
| SIA-REL03 | Dosen | Generalization | Civitas Akademika | Dosen mewarisi peran umum Civitas Akademika. |
| SIA-REL04 | Input Nilai Mata Kuliah | `<<include>>` | Validasi Mata Kuliah yang Diampu | Sistem memvalidasi mata kuliah yang diampu dosen. |
| SIA-REL05 | Lihat KHS | `<<include>>` | Periksa Publikasi Nilai | Sistem memeriksa status publikasi nilai. |
| SIA-REL06 | Tampilkan Peringatan Nilai Belum Dipublikasikan | `<<extend>>` | Lihat KHS | Peringatan ditampilkan apabila nilai belum dipublikasikan. |
| SIA-REL07 | Tampilkan Pesan Kesalahan Input Nilai | `<<extend>>` | Input Nilai Mata Kuliah | Pesan kesalahan ditampilkan apabila nilai yang dimasukkan tidak valid. |


