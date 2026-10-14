# Use Case Description

### 1. LAB-UC01 — Lihat Ketersediaan Peralatan

| Elemen | Deskripsi |
|---|---|
| Kode Use Case | LAB-UC01 |
| Nama Use Case | Lihat Ketersediaan Peralatan |
| Tujuan | Menampilkan informasi ketersediaan peralatan laboratorium kepada mahasiswa. |
| Aktor utama | Mahasiswa |
| Sumber kebutuhan | Kebutuhan informasi ketersediaan peralatan sebelum mengajukan peminjaman. |
| Pemicu | Mahasiswa memilih menu ketersediaan peralatan. |
| Prasyarat | Mahasiswa dapat mengakses sistem informasi laboratorium. |
| Pascakondisi berhasil | Informasi peralatan beserta status ketersediaannya berhasil ditampilkan. |
| Pascakondisi gagal | Informasi ketersediaan peralatan tidak berhasil ditampilkan. |
| Include | Tidak ada. |
| Extension Point | Mahasiswa memilih peralatan yang akan dipinjam. |
| Extend | LAB-UC03 — Ajukan Peminjaman, apabila mahasiswa memilih untuk mengajukan peminjaman. |

### 2. LAB-UC03 — Ajukan Peminjaman

| Elemen | Deskripsi |
|---|---|
| Kode Use Case | LAB-UC03 |
| Nama Use Case | Ajukan Peminjaman |
| Tujuan | Menghasilkan pengajuan peminjaman yang tersimpan di dalam sistem. |
| Aktor utama | Mahasiswa |
| Sumber kebutuhan | LAB-R03 dan LAB-R04. |
| Pemicu | Mahasiswa memilih fungsi pengajuan peminjaman. |
| Prasyarat | Mahasiswa telah terautentikasi dan data peralatan tersedia. |
| Pascakondisi berhasil | Pengajuan tersimpan dengan nomor pengajuan dan status Menunggu Keputusan. |
| Pascakondisi gagal | Tidak ada pengajuan baru yang berhasil tersimpan. |
| Include | LAB-UC04 — Periksa Ketersediaan. |
| Extension Point | Bukti pengajuan tersedia setelah pengajuan berhasil disimpan. |
| Extend | LAB-UC05 — Cetak Bukti Pengajuan, jika mahasiswa memilih fungsi cetak. |

### 3. LAB-UC04 — Periksa Ketersediaan

| Elemen | Deskripsi |
|---|---|
| Kode Use Case | LAB-UC04 |
| Nama Use Case | Periksa Ketersediaan |
| Tujuan | Memastikan peralatan yang diajukan dapat dipinjam sesuai jumlah dan ketersediaan stok. |
| Aktor utama | Sistem |
| Sumber kebutuhan | Proses validasi ketersediaan peralatan sebelum pengajuan disimpan. |
| Pemicu | LAB-UC03 — Ajukan Peminjaman dijalankan. |
| Prasyarat | Data peralatan dan informasi stok tersedia di dalam sistem. |
| Pascakondisi berhasil | Status ketersediaan peralatan berhasil diperiksa dan hasilnya diteruskan ke proses pengajuan. |
| Pascakondisi gagal | Sistem menemukan bahwa stok tidak mencukupi atau data ketersediaan tidak dapat diperiksa. |
| Include | Tidak ada. |
| Extension Point | Ketersediaan peralatan tidak memenuhi permintaan mahasiswa. |
| Extend | Tidak ada. |

### 4. LAB-UC05 — Cetak Bukti Pengajuan

| Elemen | Deskripsi |
|---|---|
| Kode Use Case | LAB-UC05 |
| Nama Use Case | Cetak Bukti Pengajuan |
| Tujuan | Menghasilkan bukti pengajuan peminjaman yang dapat disimpan atau dicetak oleh mahasiswa. |
| Aktor utama | Mahasiswa |
| Sumber kebutuhan | Kebutuhan mahasiswa untuk memperoleh bukti pengajuan peminjaman. |
| Pemicu | Mahasiswa memilih fungsi cetak bukti pengajuan. |
| Prasyarat | Pengajuan peminjaman telah berhasil disimpan dan memiliki nomor pengajuan. |
| Pascakondisi berhasil | Bukti pengajuan berhasil ditampilkan atau dicetak. |
| Pascakondisi gagal | Bukti pengajuan tidak berhasil ditampilkan atau dicetak. |
| Include | Tidak ada. |
| Extension Point | Mahasiswa memilih tindakan cetak setelah pengajuan berhasil tersimpan. |
| Extend | LAB-UC03 — Ajukan Peminjaman, pada extension point bukti pengajuan tersedia. |

### 5. LAB-UC06 — Proses Keputusan Peminjaman

| Elemen | Deskripsi |
|---|---|
| Kode Use Case | LAB-UC06 |
| Nama Use Case | Proses Keputusan Peminjaman |
| Tujuan | Memproses keputusan terhadap pengajuan peminjaman peralatan laboratorium. |
| Aktor utama | Petugas Laboratorium |
| Sumber kebutuhan | Kebutuhan pemeriksaan dan penentuan status pengajuan peminjaman. |
| Pemicu | Petugas Laboratorium memilih pengajuan yang menunggu keputusan. |
| Prasyarat | Petugas telah terautentikasi dan terdapat pengajuan peminjaman yang menunggu keputusan. |
| Pascakondisi berhasil | Keputusan peminjaman tersimpan dan status pengajuan diperbarui sesuai keputusan petugas. |
| Pascakondisi gagal | Keputusan tidak berhasil disimpan dan status pengajuan tidak berubah. |
| Include | Tidak ada. |
| Extension Point | Petugas menentukan keputusan berdasarkan hasil pemeriksaan pengajuan. |
| Extend | Tidak ada. |

---

## Ringkasan Relasi Use Case

| No. | Use Case Utama | Relasi | Use Case Terkait | Keterangan |
|---:|---|---|---|---|
| 1 | LAB-UC03 — Ajukan Peminjaman | `<<include>>` | LAB-UC04 — Periksa Ketersediaan | Pemeriksaan ketersediaan wajib dilakukan dalam proses pengajuan. |
| 2 | LAB-UC05 — Cetak Bukti Pengajuan | `<<extend>>` | LAB-UC03 — Ajukan Peminjaman | Pencetakan bukti dilakukan secara opsional setelah pengajuan berhasil. |
