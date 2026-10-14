## UC-01 — Ajukan KRS

| Elemen | Deskripsi |
|---|---|
| ID Use Case | UC-01 |
| Nama Use Case | Ajukan KRS |
| Aktor | Mahasiswa |
| Tujuan | Mahasiswa dapat memilih mata kuliah dan mengajukan KRS. |
| Prasyarat | Mahasiswa dapat mengakses sistem KRS dan periode pengisian KRS tersedia. |
| Pemicu | Mahasiswa memilih menu pengajuan KRS. |
| Deskripsi Proses | Mahasiswa memilih mata kuliah dan mengirim pengajuan. Sistem menjalankan UC-02 Validasi KRS melalui relasi `<<include>>`. Jika validasi berhasil, sistem menyimpan pengajuan dengan status menunggu persetujuan dosen wali. Jika gagal, sistem menampilkan alasan kegagalan agar mahasiswa dapat memperbaiki pengajuan. |
| Relasi Use Case | `<<include>>` UC-02 Validasi KRS. UC-03 Unduh Bukti Pengajuan KRS memperluas UC-01 melalui `<<extend>>` jika pengajuan berhasil disimpan dan mahasiswa memilih mengunduh bukti. |
| Pascakondisi | Pengajuan tersimpan jika validasi berhasil dan berstatus menunggu persetujuan dosen wali. |

## UC-02 — Validasi KRS

| Elemen | Deskripsi |
|---|---|
| ID Use Case | UC-02 |
| Nama Use Case | Validasi KRS |
| Aktor | Sistem, dipicu oleh Mahasiswa |
| Tujuan | Memeriksa kelengkapan pengajuan, prasyarat mata kuliah, dan benturan jadwal. |
| Prasyarat | Mahasiswa telah mengirim pengajuan KRS melalui UC-01. |
| Pemicu | Sistem menerima pengajuan KRS dari mahasiswa. |
| Deskripsi Proses | Sistem memeriksa kelengkapan data, prasyarat mata kuliah, dan benturan jadwal. Jika seluruh pemeriksaan terpenuhi, validasi berhasil. Jika terdapat kesalahan, sistem menampilkan alasan kegagalan dan meminta mahasiswa memperbaiki pengajuan. |
| Relasi Use Case | Menjadi use case yang disertakan melalui `<<include>>` oleh UC-01 Ajukan KRS. |
| Pascakondisi | Hasil validasi berhasil atau gagal tersedia untuk proses pengajuan KRS. |

## UC-03 — Unduh Bukti Pengajuan KRS

| Elemen | Deskripsi |
|---|---|
| ID Use Case | UC-03 |
| Nama Use Case | Unduh Bukti Pengajuan KRS |
| Aktor | Mahasiswa |
| Tujuan | Memberikan bukti bahwa pengajuan KRS telah berhasil disimpan. |
| Prasyarat | Pengajuan KRS telah berhasil divalidasi dan disimpan. |
| Pemicu | Mahasiswa memilih tombol unduh bukti pengajuan. |
| Deskripsi Proses | Mahasiswa membuka detail pengajuan dan memilih tombol unduh. Sistem memeriksa data pengajuan, menyiapkan bukti, dan menyediakan dokumen untuk diunduh. Jika proses gagal, sistem menampilkan pesan kesalahan agar mahasiswa dapat mencoba kembali. |
| Relasi Use Case | `<<extend>>` UC-01 Ajukan KRS karena pengunduhan bukti merupakan proses opsional setelah pengajuan berhasil disimpan. |
| Pascakondisi | Bukti pengajuan berhasil diunduh dan status pengajuan tetap menunggu persetujuan dosen wali. |

## UC-04 — Proses Keputusan KRS

| Elemen | Deskripsi |
|---|---|
| ID Use Case | UC-04 |
| Nama Use Case | Proses Keputusan KRS |
| Aktor | Dosen Wali |
| Tujuan | Menentukan apakah pengajuan KRS mahasiswa disetujui atau ditolak. |
| Prasyarat | Pengajuan KRS telah tersimpan dengan status menunggu persetujuan dosen wali. |
| Pemicu | Dosen wali membuka daftar pengajuan KRS mahasiswa. |
| Deskripsi Proses | Dosen wali memeriksa detail pengajuan, kemudian memilih persetujuan atau penolakan. Sistem menjalankan UC-05 Catat Keputusan KRS melalui relasi `<<include>>` untuk menyimpan hasil keputusan dan catatannya. Jika disetujui, status menjadi Disetujui. Jika ditolak, status menjadi Ditolak dan catatan alasan penolakan disimpan. |
| Relasi Use Case | `<<include>>` UC-05 Catat Keputusan KRS. |
| Pascakondisi | Keputusan dosen wali tersimpan dan status pengajuan diperbarui sesuai hasil keputusan. |

## UC-05 — Catat Keputusan KRS

| Elemen | Deskripsi |
|---|---|
| ID Use Case | UC-05 |
| Nama Use Case | Catat Keputusan KRS |
| Aktor | Dosen Wali |
| Tujuan | Menyimpan keputusan persetujuan atau penolakan beserta catatan dosen wali. |
| Prasyarat | Dosen wali telah memeriksa pengajuan dan memilih keputusan melalui UC-04. |
| Pemicu | Dosen wali mengirim keputusan KRS. |
| Deskripsi Proses | Dosen wali memberikan catatan keputusan. Sistem memeriksa kelengkapan data, menyimpan hasil keputusan, dan memperbarui status menjadi Disetujui atau Ditolak. Jika catatan wajib belum diisi atau penyimpanan gagal, sistem menampilkan pesan agar dosen wali melengkapi atau mengulangi proses. |
| Relasi Use Case | Menjadi use case yang disertakan melalui `<<include>>` oleh UC-04 Proses Keputusan KRS. |
| Pascakondisi | Keputusan dan catatan tersimpan serta status pengajuan diperbarui. |
