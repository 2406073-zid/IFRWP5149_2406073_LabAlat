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
| LHS-UC01 | Lihat Kalender Akademik | Use case umum yang dapat dilakukan oleh Civitas Akademika. | LHS-R01 |
| LHS-UC02 | Input Nilai Mata Kuliah | Use case utama yang dilakukan dosen untuk memasukkan nilai mata kuliah yang diampunya. | LHS-R02, LHS-R08, LHS-R09 |
| LHS-UC03 | Lihat KHS | Use case utama yang dilakukan mahasiswa untuk melihat KHS pada semester yang nilainya telah dipublikasikan. | LHS-R03, LHS-R04 |
| LHS-UC04 | Kelola Data Mahasiswa | Use case umum untuk mengelola data mahasiswa oleh Admin Akademik. | LHS-R05, LHS-R06, LHS-R07 |
| LHS-UC05 | Tambah Data Mahasiswa | Use case khusus untuk menambahkan data mahasiswa baru. | LHS-R05 |
| LHS-UC06 | Ubah Data Mahasiswa | Use case khusus untuk mengubah data mahasiswa yang telah tersimpan. | LHS-R06 |
| LHS-UC07 | Hapus Data Mahasiswa | Use case khusus untuk menghapus data mahasiswa sesuai aturan sistem. | LHS-R07 |
| LHS-UC08 | Validasi Mata Kuliah yang Diampu | Memastikan dosen hanya menginput nilai pada mata kuliah yang menjadi tanggung jawabnya. | LHS-R08 |
| LHS-UC09 | Simpan Nilai Mata Kuliah | Menyimpan nilai yang telah diinput dosen. | LHS-R09 |
| LHS-UC10 | Periksa Publikasi Nilai | Memeriksa ketersediaan publikasi nilai sebelum KHS ditampilkan kepada mahasiswa. | LHS-R04 |
| LHS-UC11 | Tampilkan KHS | Menampilkan KHS berdasarkan data nilai yang sudah dipublikasikan. | LHS-R03, LHS-R04 |

# Relasi Use case
| ID | Relasi | Use Case Sumber | Jenis Relasi | Use Case Tujuan | Keterangan |
|---|---|---|---|---|---|
| LHS-REL01 | Civitas Akademika → Lihat Kalender Akademik | Civitas Akademika | Association | Lihat Kalender Akademik (LHS-UC01) | Civitas Akademika dapat melihat kalender akademik. |
| LHS-REL02 | Mahasiswa → Civitas Akademika | Mahasiswa | Generalization | Civitas Akademika | Mahasiswa mewarisi peran dan akses umum dari Civitas Akademika. |
| LHS-REL03 | Dosen → Civitas Akademika | Dosen | Generalization | Civitas Akademika | Dosen mewarisi peran dan akses umum dari Civitas Akademika. |
| LHS-REL04 | Dosen → Input Nilai Mata Kuliah | Dosen | Association | Input Nilai Mata Kuliah (LHS-UC02) | Dosen menginput nilai mata kuliah yang diampunya. |
| LHS-REL05 | Input Nilai Mata Kuliah → Validasi Mata Kuliah yang Diampu | Input Nilai Mata Kuliah (LHS-UC02) | `<<include>>` | Validasi Mata Kuliah yang Diampu (LHS-UC08) | Penginputan nilai mencakup pemeriksaan bahwa mata kuliah diampu oleh dosen yang bersangkutan. |
| LHS-REL06 | Input Nilai Mata Kuliah → Simpan Nilai Mata Kuliah | Input Nilai Mata Kuliah (LHS-UC02) | `<<include>>` | Simpan Nilai Mata Kuliah (LHS-UC09) | Nilai yang diinput harus disimpan ke dalam sistem. |
| LHS-REL07 | Mahasiswa → Lihat KHS | Mahasiswa | Association | Lihat KHS (LHS-UC03) | Mahasiswa dapat melihat KHS miliknya. |
| LHS-REL08 | Lihat KHS → Periksa Publikasi Nilai | Lihat KHS (LHS-UC03) | `<<include>>` | Periksa Publikasi Nilai (LHS-UC10) | Sistem memeriksa status publikasi nilai sebelum menampilkan KHS. |
| LHS-REL09 | Lihat KHS → Tampilkan KHS | Lihat KHS (LHS-UC03) | `<<include>>` | Tampilkan KHS (LHS-UC11) | Sistem menampilkan KHS berdasarkan nilai yang telah dipublikasikan. |
| LHS-REL10 | Admin Akademik → Kelola Data Mahasiswa | Admin Akademik | Association | Kelola Data Mahasiswa (LHS-UC04) | Admin Akademik memiliki kewenangan mengelola data mahasiswa. |
| LHS-REL11 | Tambah Data Mahasiswa → Kelola Data Mahasiswa | Tambah Data Mahasiswa (LHS-UC05) | Generalization | Kelola Data Mahasiswa (LHS-UC04) | Tambah data merupakan bentuk khusus dari pengelolaan data mahasiswa. |
| LHS-REL12 | Ubah Data Mahasiswa → Kelola Data Mahasiswa | Ubah Data Mahasiswa (LHS-UC06) | Generalization | Kelola Data Mahasiswa (LHS-UC04) | Ubah data merupakan bentuk khusus dari pengelolaan data mahasiswa. |
| LHS-REL13 | Hapus Data Mahasiswa → Kelola Data Mahasiswa | Hapus Data Mahasiswa (LHS-UC07) | Generalization | Kelola Data Mahasiswa (LHS-UC04) | Hapus data merupakan bentuk khusus dari pengelolaan data mahasiswa. |

