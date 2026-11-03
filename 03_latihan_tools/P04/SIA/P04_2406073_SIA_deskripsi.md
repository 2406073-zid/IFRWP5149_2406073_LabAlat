# Deskripsi Use Case SIA

Dokumen ini merangkum aktor, tujuan, alur, relasi, dan kondisi akhir use case pada model P04. Uraian mengikuti skenario P04 dan diagram use case terkait.

## Daftar Use Case

### LHS-UC01 ? Lihat Kalender Akademik

| Elemen | Deskripsi |
|---|---|
| ID Use Case | LHS-UC01 |
| Nama Use Case | Lihat Kalender Akademik |
| Aktor | Civitas Akademika (Mahasiswa dan Dosen) |
| Tujuan | Melihat agenda resmi institusi, seperti awal semester, batas KRS, dan masa ujian. |
| Prasyarat | Pengguna telah terautentikasi dan memiliki hak akses sesuai peran. |
| Pemicu | Pengguna membuka menu kalender akademik. |
| Deskripsi Proses | Sistem menampilkan agenda resmi institusi dan rincian agenda yang dipilih. |
| Relasi Use Case | Tidak ada relasi khusus. |
| Pascakondisi | Kalender akademik ditampilkan. |

### LHS-UC02 ? Input Nilai Mata Kuliah

| Elemen | Deskripsi |
|---|---|
| ID Use Case | LHS-UC02 |
| Nama Use Case | Input Nilai Mata Kuliah |
| Aktor | Dosen |
| Tujuan | Dosen menginput nilai mata kuliah yang diampunya setelah masa perkuliahan berakhir. |
| Prasyarat | Pengguna telah terautentikasi dan memiliki hak akses sesuai peran. |
| Pemicu | Dosen membuka fungsi input nilai dan memilih mata kuliah. |
| Deskripsi Proses | Sistem memvalidasi mata kuliah melalui LHS-UC08, menerima nilai, lalu menyimpan melalui LHS-UC09. |
| Relasi Use Case | `<<include>>` LHS-UC08 Validasi Mata Kuliah yang Diampu dan LHS-UC09 Simpan Nilai Mata Kuliah; direalisasikan melalui collaboration yang sesuai. |
| Pascakondisi | Nilai tersimpan dan belum ditampilkan di KHS sebelum dipublikasikan. |

### LHS-UC03 ? Lihat KHS

| Elemen | Deskripsi |
|---|---|
| ID Use Case | LHS-UC03 |
| Nama Use Case | Lihat KHS |
| Aktor | Mahasiswa |
| Tujuan | Melihat KHS untuk semester yang nilainya sudah dipublikasikan. |
| Prasyarat | Pengguna telah terautentikasi dan memiliki hak akses sesuai peran. |
| Pemicu | Mahasiswa memilih menu Lihat KHS dan semester. |
| Deskripsi Proses | Sistem memeriksa publikasi melalui LHS-UC10 dan menampilkan KHS melalui LHS-UC11 jika sudah dipublikasikan. |
| Relasi Use Case | `<<include>>` LHS-UC10 Periksa Publikasi Nilai dan LHS-UC11 Tampilkan KHS; direalisasikan melalui collaboration yang sesuai. |
| Pascakondisi | KHS hanya ditampilkan untuk semester yang nilainya telah dipublikasikan. |

### LHS-UC04 ? Kelola Data Mahasiswa

| Elemen | Deskripsi |
|---|---|
| ID Use Case | LHS-UC04 |
| Nama Use Case | Kelola Data Mahasiswa |
| Aktor | Admin Akademik |
| Tujuan | Mengakses fungsi tambah, ubah, dan hapus data mahasiswa. |
| Prasyarat | Pengguna telah terautentikasi dan memiliki hak akses sesuai peran. |
| Pemicu | Admin membuka menu Kelola Data Mahasiswa. |
| Deskripsi Proses | Sistem menampilkan data dan menyediakan pilihan proses khusus LHS-UC05 sampai LHS-UC07. |
| Relasi Use Case | Tidak ada relasi khusus. |
| Pascakondisi | Admin memilih tindakan; use case umum bagi LHS-UC05 s.d. LHS-UC07. |

### LHS-UC05 ? Tambah Data Mahasiswa

| Elemen | Deskripsi |
|---|---|
| ID Use Case | LHS-UC05 |
| Nama Use Case | Tambah Data Mahasiswa |
| Aktor | Admin Akademik |
| Tujuan | Menambahkan data mahasiswa baru. |
| Prasyarat | Pengguna telah terautentikasi dan memiliki hak akses sesuai peran. |
| Pemicu | Admin memilih Tambah Data Mahasiswa dan mengisi formulir. |
| Deskripsi Proses | Sistem memvalidasi kelengkapan data, menyimpan data baru, dan menampilkan konfirmasi. |
| Relasi Use Case | Generalization dari LHS-UC04 Kelola Data Mahasiswa. |
| Pascakondisi | Data mahasiswa baru tersimpan; generalization dari LHS-UC04. |

### LHS-UC06 ? Ubah Data Mahasiswa

| Elemen | Deskripsi |
|---|---|
| ID Use Case | LHS-UC06 |
| Nama Use Case | Ubah Data Mahasiswa |
| Aktor | Admin Akademik |
| Tujuan | Memperbarui data mahasiswa yang telah tersimpan. |
| Prasyarat | Pengguna telah terautentikasi dan memiliki hak akses sesuai peran. |
| Pemicu | Admin memilih data mahasiswa dan mengirim perubahan. |
| Deskripsi Proses | Sistem memvalidasi perubahan, menyimpan data, dan menampilkan konfirmasi. |
| Relasi Use Case | Generalization dari LHS-UC04 Kelola Data Mahasiswa. |
| Pascakondisi | Data mahasiswa diperbarui; generalization dari LHS-UC04. |

### LHS-UC07 ? Hapus Data Mahasiswa

| Elemen | Deskripsi |
|---|---|
| ID Use Case | LHS-UC07 |
| Nama Use Case | Hapus Data Mahasiswa |
| Aktor | Admin Akademik |
| Tujuan | Menghapus data mahasiswa yang tidak memiliki data akademik aktif. |
| Prasyarat | Pengguna telah terautentikasi dan memiliki hak akses sesuai peran. |
| Pemicu | Admin memilih data mahasiswa untuk dihapus. |
| Deskripsi Proses | Sistem memeriksa data akademik aktif dan meminta konfirmasi sebelum menghapus. |
| Relasi Use Case | Generalization dari LHS-UC04 Kelola Data Mahasiswa. |
| Pascakondisi | Data dihapus jika tidak ada data akademik aktif; generalization dari LHS-UC04. |

### LHS-UC08 ? Validasi Mata Kuliah yang Diampu

| Elemen | Deskripsi |
|---|---|
| ID Use Case | LHS-UC08 |
| Nama Use Case | Validasi Mata Kuliah yang Diampu |
| Aktor | Sistem; dipanggil oleh LHS-UC02 |
| Tujuan | Memastikan dosen hanya menginput nilai mata kuliah yang diampunya. |
| Prasyarat | Pengguna telah terautentikasi dan memiliki hak akses sesuai peran. |
| Pemicu | LHS-UC02 meminta validasi dosen dan mata kuliah. |
| Deskripsi Proses | Sistem memeriksa penugasan mengajar dosen dan mengembalikan hasil validasi. |
| Relasi Use Case | `<<include>>` oleh LHS-UC02 Input Nilai Mata Kuliah. |
| Pascakondisi | Hasil validasi dikembalikan ke LHS-UC02. |

### LHS-UC09 ? Simpan Nilai Mata Kuliah

| Elemen | Deskripsi |
|---|---|
| ID Use Case | LHS-UC09 |
| Nama Use Case | Simpan Nilai Mata Kuliah |
| Aktor | Sistem; dipanggil oleh LHS-UC02 |
| Tujuan | Menyimpan nilai yang sudah diinput dosen. |
| Prasyarat | Pengguna telah terautentikasi dan memiliki hak akses sesuai peran. |
| Pemicu | LHS-UC02 mengirim nilai setelah validasi berhasil. |
| Deskripsi Proses | Sistem menyimpan nilai mata kuliah dan mahasiswa terkait. |
| Relasi Use Case | `<<include>>` oleh LHS-UC02 Input Nilai Mata Kuliah. |
| Pascakondisi | Nilai tersimpan dan menunggu publikasi resmi. |

### LHS-UC10 ? Periksa Publikasi Nilai

| Elemen | Deskripsi |
|---|---|
| ID Use Case | LHS-UC10 |
| Nama Use Case | Periksa Publikasi Nilai |
| Aktor | Sistem; dipanggil oleh LHS-UC03 |
| Tujuan | Memastikan nilai semester telah dipublikasikan sebelum KHS ditampilkan. |
| Prasyarat | Pengguna telah terautentikasi dan memiliki hak akses sesuai peran. |
| Pemicu | LHS-UC03 meminta status publikasi untuk semester pilihan. |
| Deskripsi Proses | Sistem memeriksa status publikasi dan mengembalikan hasilnya. |
| Relasi Use Case | `<<include>>` oleh LHS-UC03 Lihat KHS. |
| Pascakondisi | Status publikasi tersedia bagi LHS-UC03. |

### LHS-UC11 ? Tampilkan KHS

| Elemen | Deskripsi |
|---|---|
| ID Use Case | LHS-UC11 |
| Nama Use Case | Tampilkan KHS |
| Aktor | Sistem; dipanggil oleh LHS-UC03 |
| Tujuan | Menampilkan KHS berdasarkan nilai yang sudah dipublikasikan. |
| Prasyarat | Pengguna telah terautentikasi dan memiliki hak akses sesuai peran. |
| Pemicu | LHS-UC03 meminta KHS setelah pemeriksaan publikasi berhasil. |
| Deskripsi Proses | Sistem mengambil nilai mahasiswa, menyusun KHS, dan menampilkannya. |
| Relasi Use Case | `<<include>>` oleh LHS-UC03 Lihat KHS. |
| Pascakondisi | KHS semester terpilih ditampilkan. |

## Catatan Model

Nilai hanya dapat diinput oleh dosen pengampu. Nilai yang diinput belum tampil di KHS sampai dipublikasikan. KHS hanya menampilkan nilai yang sudah dipublikasikan. Penghapusan data mahasiswa hanya berlaku jika tidak memiliki data akademik aktif.
