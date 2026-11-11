# Jobsheet Review Use Case Sistem Informasi Akademik (Pengajuan KRS)

## Tujuan

1. Memahami relasi `<<include>>` dan `<<extend>>` pada use case diagram.
2. Menyusun use case beserta deskripsinya untuk proses pengajuan dan pengambilan keputusan KRS.
3. Membedakan perilaku wajib (include) dan perilaku opsional (extend) berdasarkan skenario.
4. Meninjau kelengkapan dan konsistensi rancangan use case Sistem Informasi Akademik.

## Dasar Teori

**Use case diagram** menggambarkan interaksi aktor dengan fungsi sistem. Selain asosiasi aktor dan use case, UML menyediakan relasi antar use case.

**Relasi `<<include>>`**

- Digunakan ketika sebuah use case *selalu* membutuhkan perilaku dari use case lain.
- Use case yang disertakan wajib dijalankan sebagai bagian dari use case dasar.
- Arah panah putus-putus dari use case dasar menuju use case yang disertakan.
- Contoh: *Ajukan KRS* menyertakan *Validasi KRS*.

**Relasi `<<extend>>`**

- Digunakan untuk perilaku tambahan yang *opsional* dan hanya berjalan pada kondisi tertentu.
- Arah panah putus-putus dari use case yang memperluas menuju use case dasar.
- Contoh: *Unduh Bukti Pengajuan KRS* memperluas *Ajukan KRS*.

**Deskripsi use case** melengkapi diagram dengan keterangan tekstual, umumnya berisi identitas (ID dan nama), aktor, tujuan, prasyarat, pemicu, deskripsi proses (alur normal dan alternatif), relasi, dan pascakondisi. Struktur ini membuat perilaku sistem dapat ditelusuri ke skenario.

**Alur alternatif** perlu dimodelkan agar sistem menangani kondisi gagal, misalnya validasi tidak terpenuhi, tidak hanya kondisi berhasil.

## Hasil Review

| No. | Aspek yang Ditinjau | Hasil Review | Alasan |
|---:|---|---|---|
| 1 | Identifikasi aktor | Terdapat dua aktor, yaitu **Mahasiswa** dan **Dosen Wali**. | Kedua aktor memiliki peran yang jelas dalam proses pengajuan dan pengambilan keputusan KRS. |
| 2 | Use case pengajuan KRS | **UC-01 Ajukan KRS** telah menggambarkan proses pemilihan mata kuliah dan pengiriman pengajuan oleh Mahasiswa. | Sesuai dengan skenario yang diberikan. |
| 3 | Relasi validasi KRS | **UC-01 Ajukan KRS** terhubung dengan **UC-02 Validasi KRS** menggunakan `<<include>>`. | Validasi wajib dilakukan untuk memeriksa kelengkapan, prasyarat mata kuliah, dan benturan jadwal. |
| 4 | Use case unduh bukti | **UC-03 Unduh Bukti Pengajuan KRS** terhubung dengan aktor Mahasiswa dan memperluas UC-01 menggunakan `<<extend>>`. | Pengunduhan bukti dilakukan secara opsional setelah pengajuan berhasil disimpan. |
| 5 | Use case keputusan KRS | **UC-04 Proses Keputusan KRS** terhubung dengan aktor Dosen Wali. | Dosen Wali bertanggung jawab memeriksa pengajuan dan menentukan persetujuan atau penolakan. |
| 6 | Relasi pencatatan keputusan | **UC-04 Proses Keputusan KRS** terhubung dengan **UC-05 Catat Keputusan KRS** menggunakan `<<include>>`. | Setiap keputusan perlu dicatat agar hasilnya tersimpan dalam sistem. |
| 7 | Hasil validasi | Sistem menangani validasi berhasil maupun gagal dan memberikan informasi kesalahan jika pengajuan tidak memenuhi persyaratan. | Mahasiswa dapat mengetahui hasil pemeriksaan dan memperbaiki pengajuan jika diperlukan. |
| 8 | Hasil keputusan | Sistem menyimpan status **Disetujui** atau **Ditolak** beserta catatan keputusan Dosen Wali. | Hasil keputusan dapat diketahui oleh Mahasiswa dan tersimpan sebagai bagian dari data pengajuan. |
| 9 | Konsistensi rancangan | Kelima use case telah memiliki identitas, aktor, tujuan, prasyarat, pemicu, deskripsi proses, relasi, dan pascakondisi. | Struktur deskripsi membantu menjelaskan fungsi setiap use case secara sistematis. |

## Kesimpulan

Rancangan use case pengajuan KRS telah sesuai dengan skenario. Aktor **Mahasiswa** dan **Dosen Wali** teridentifikasi dengan peran yang jelas. Relasi antar use case dipakai dengan tepat: `<<include>>` untuk *Validasi KRS* dan *Catat Keputusan KRS* karena keduanya wajib dijalankan, serta `<<extend>>` untuk *Unduh Bukti Pengajuan KRS* karena bersifat opsional setelah pengajuan berhasil.

Sistem juga menangani hasil validasi berhasil maupun gagal, dan menyimpan status keputusan (**Disetujui** atau **Ditolak**) beserta catatannya. Kelima use case telah dilengkapi deskripsi yang konsisten. Dari review ini dapat disimpulkan bahwa pemisahan perilaku wajib dan opsional serta kelengkapan deskripsi use case membuat rancangan mudah ditelusuri ke kebutuhan pada skenario.