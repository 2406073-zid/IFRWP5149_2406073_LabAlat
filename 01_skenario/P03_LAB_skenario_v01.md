 # Skenario   
    Mahasiswa mengajukan peminjaman peralatan dengan memilih alat, 
    jumlah, dan rentang waktu. Sistem memeriksa ketersediaan. Jika 
    tersedia dan data lengkap, sistem menyimpan pengajuan berstatus 
    menunggu keputusan. Pada tampilan konfirmasi, mahasiswa dapat 
    memilih mencetak bukti pengajuan. Petugas mengelola data peralatan 
    serta menyetujui atau menolak pengajuan. Kepala laboratorium melihat 
    laporan peminjaman. 

# Kebutuhan Sistem
    |Kebutuhan|                                             Sistem                                              |
    |---------|-------------------------------------------------------------------------------------------------|
    |   ID    |                                            Kebutuhan                                            |
    | LAB-R01 |                         Mahasiswa dapat melihat ketersediaan peralatan                          |
    | LAB-R02 |                             Petugas dapat mengelola data peralatan                              |
    | LAB-R03 |Mahasiswa dapat mengajukan peminjaman; sistem memeriksa ketersediaan sebelum menyimpan pengajuan |
    | LAB-R04 |            Mahasiswa dapat mencetak bukti pada konfirmasi pengajuan jika memilihnya             |
    | LAB-R05 |                  Petugas dapat menetapkan persetujuan atau penolakan pengajuan                  |
    | LAB-R06 |                      Kepala laboratorium dapat melihat laporan peminjaman                       |

# Batas dan Aturan Sistem
    Batas sistem dan aturan: 
    • Sistem mencatat dan menyediakan informasi; perpindahan fisik alat tidak 
    terjadi di dalam perangkat lunak. 
    • Pengguna telah terautentikasi dan memiliki hak akses sesuai peran. 
    • Pengajuan yang diterima sistem berstatus Menunggu keputusan, bukan 
    otomatis Disetujui. 
    • Pengajuan dengan peralatan tidak tersedia tidak disimpan sebagai 
    pengajuan berhasil. 
    • Pencetakan bukti tidak menjadi syarat keberhasilan pengajuan. 
    • Persetujuan petugas belum dimodelkan sebagai reservasi teknis stok. 
    • Pengambilan, pengembalian, kondisi alat, dan denda belum dianalisis 
    pada potongan model ini.

# Identifikasi Aktor 
## Tabel Aktor Sistem Pengajuan KRS

| Aktor | Tujuan terhadap Sistem |
|---|---|
| Mahasiswa | Memilih mata kuliah, mengajukan KRS, melihat status pengajuan, dan mengunduh bukti pengajuan. |
| Dosen Wali | Memeriksa pengajuan KRS, memberikan persetujuan atau penolakan, serta mencatat keputusan dan alasannya. |

# Identifikasi Use Case
## Katalog Use Case Sistem Pengajuan KRS

| ID | Nama Use Case | Keterangan |
|---|---|---|
| UC-01 | Ajukan KRS | Fungsi utama Mahasiswa untuk memilih mata kuliah dan mengirim pengajuan KRS. |
| UC-02 | Validasi KRS | Proses sistem untuk memeriksa kelengkapan pengajuan, prasyarat mata kuliah, dan benturan jadwal. |
| UC-03 | Unduh Bukti Pengajuan KRS | Perilaku tambahan yang dapat dilakukan Mahasiswa setelah pengajuan KRS berhasil disimpan. |
| UC-04 | Proses Keputusan KRS | Fungsi utama Dosen Wali untuk memeriksa pengajuan dan memberikan persetujuan atau penolakan. |
| UC-05 | Catat Keputusan KRS | Proses pencatatan hasil keputusan dan catatan Dosen Wali pada pengajuan KRS. |

# Relasi Use Case
| No. | Use Case Utama | Relasi | Use Case Terkait | Keterangan |
|---:|---|---|---|---|
| 1 | LAB-UC03 — Ajukan Peminjaman | `<<include>>` | LAB-UC04 — Periksa Ketersediaan | Pemeriksaan ketersediaan wajib dilakukan dalam proses pengajuan. |
| 2 | LAB-UC05 — Cetak Bukti Pengajuan | `<<extend>>` | LAB-UC03 — Ajukan Peminjaman | Pencetakan bukti dilakukan secara opsional setelah pengajuan berhasil. |
