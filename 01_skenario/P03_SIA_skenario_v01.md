# skenario
Skenario tugas:
Mahasiswa mengajukan KRS dengan memilih mata kuliah. Setiap
pengajuan menjalankan validasi KRS yang memeriksa kelengkapan,
prasyarat mata kuliah, dan benturan jadwal. Jika validasi berhasil,
sistem menyimpan pengajuan berstatus menunggu persetujuan dosen
wali. Pada konfirmasi penyimpanan, mahasiswa dapat memilih
mengunduh bukti pengajuan. Dosen wali menyetujui atau menolak KRS
dan memberikan catatan keputusan

# Kebututhan Tugas

| ID Kebutuhan | Tugas |
|---|---|
| SIA-R01 | Mahasiswa dapat melihat jadwal kuliah. |
| SIA-R02 | Admin akademik dapat mengelola jadwal kuliah. |
| SIA-R03 | Mahasiswa dapat mengajukan KRS. |
| SIA-R04 | Sistem memvalidasi KRS sebagai bagian dari proses pengajuan. |
| SIA-R05 | Mahasiswa dapat mengunduh bukti pengajuan jika memilihnya pada konfirmasi penyimpanan. |
| SIA-R06 | Dosen Wali dapat memproses persetujuan atau penolakan KRS. |

# Batas dan aturan
Batas dan asumsi sistem:
• Pengguna telah terautentikasi.
• Data mata kuliah, prasyarat, dan jadwal tersedia.
• Validasi gagal menyebabkan pengajuan belum berhasil tersimpan.
• Unduh bukti tidak menjadi syarat keberhasilan pengajuan.
• KRS tersimpan belum berarti disetujui.
• Pembayaran, pengisian nilai, dan implementasi basis data berada di luar
tugas.

# Tabel Identifikasi Aktor dan Use Case

| No. | Nama Aktor | Jenis Aktor | Peran dan Tanggung Jawab |
|---|---|---|---|
| 1 | Mahasiswa | Aktor utama | Memilih mata kuliah, mengajukan KRS, menjalani proses validasi, dan mengunduh bukti pengajuan setelah penyimpanan berhasil. |
| 2 | Dosen Wali | Aktor utama | Memeriksa pengajuan KRS, memberikan persetujuan atau penolakan, serta menambahkan catatan keputusan. |


| No. | Nama Use Case | Aktor Terkait | Tujuan | Hasil yang Diharapkan |
|---|---|---|---|---|
| 1 | Memilih Mata Kuliah | Mahasiswa | Memilih mata kuliah yang akan diambil pada semester berjalan. | Daftar mata kuliah yang dipilih tercatat sebagai pengajuan KRS. |
| 2 | Mengajukan KRS | Mahasiswa | Mengirimkan pengajuan KRS yang telah disusun. | Sistem memulai proses validasi KRS. |
| 3 | Memvalidasi KRS | Mahasiswa (pemicu proses) | Memeriksa kelengkapan pengajuan, prasyarat mata kuliah, dan benturan jadwal. | Jika validasi berhasil, pengajuan disimpan dengan status menunggu persetujuan dosen wali. Jika gagal, pengajuan perlu diperbaiki. |
| 4 | Mengunduh Bukti Pengajuan | Mahasiswa | Mendapatkan bukti pengajuan KRS setelah penyimpanan berhasil. | Bukti pengajuan KRS dapat diunduh oleh mahasiswa. |
| 5 | Memberikan Keputusan KRS | Dosen Wali | Meninjau pengajuan KRS, memberikan persetujuan atau penolakan, dan menambahkan catatan keputusan. | Status pengajuan diperbarui sesuai keputusan dosen wali dan catatan keputusan tersimpan. |

# 2. Katalog Use Case

| No. | Nama Use Case | Aktor Terkait | Tujuan | Hasil yang Diharapkan |
|---|---|---|---|---|
| 1 | Memilih Mata Kuliah | Mahasiswa | Memilih mata kuliah yang akan diambil pada semester berjalan. | Daftar mata kuliah yang dipilih tercatat sebagai pengajuan KRS. |
| 2 | Mengajukan KRS | Mahasiswa | Mengirimkan pengajuan KRS yang telah disusun. | Sistem memulai proses validasi KRS. |
| 3 | Memvalidasi KRS | Mahasiswa (pemicu proses) | Memeriksa kelengkapan pengajuan, prasyarat mata kuliah, dan benturan jadwal. | Jika validasi berhasil, pengajuan disimpan dengan status menunggu persetujuan dosen wali. Jika gagal, pengajuan perlu diperbaiki. |
| 4 | Mengunduh Bukti Pengajuan | Mahasiswa | Mendapatkan bukti pengajuan KRS setelah penyimpanan berhasil. | Bukti pengajuan KRS dapat diunduh oleh mahasiswa. |
| 5 | Memberikan Keputusan KRS | Dosen Wali | Meninjau pengajuan KRS, memberikan persetujuan atau penolakan, dan menambahkan catatan keputusan. | Status pengajuan diperbarui sesuai keputusan dosen wali dan catatan keputusan tersimpan. |

# 2. Relasi Use Case

| Jenis Relasi | Hubungan | Alasan |
|---|---|---|
| `<<include>>` | UC-01 → UC-02 | Validasi wajib dilakukan dalam setiap pengajuan KRS. |
| `<<extend>>` | UC-03 → UC-01 | Pengunduhan bukti bersifat opsional setelah pengajuan berhasil disimpan. |
| `<<include>>` | UC-04 → UC-05 | Pencatatan keputusan menjadi bagian wajib dari proses keputusan KRS sesuai skenario. |
