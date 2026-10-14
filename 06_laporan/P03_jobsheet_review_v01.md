# Jobsheet Review Use Case Sistem Informasi Akademik (Pengajuan KRS)

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
