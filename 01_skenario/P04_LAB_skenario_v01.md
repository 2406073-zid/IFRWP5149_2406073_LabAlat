# skenario
Skenario berikut merupakan bahan latihan yang ditetapkan untuk jobsheet, bukan hasil pengumpulan kebutuhan laboratorium nyata. Skenario ini melanjutkan potongan model Pertemuan 3.

Selain mahasiswa, dosen juga dapat meminjam peralatan laboratorium untuk kegiatan praktikum dan penelitian. Mahasiswa dan dosen sama-sama dapat melihat ketersediaan peralatan serta mengajukan peminjaman.

Petugas laboratorium bertanggung jawab mengelola data peralatan, yang meliputi penambahan peralatan baru, perubahan data peralatan, dan penghapusan data peralatan yang tidak lagi digunakan.

Setelah peminjaman disetujui dan peralatan diambil, petugas laboratorium mencatat pengembalian peralatan. Pada saat mencatat pengembalian, petugas juga memeriksa dan mencatat kondisi peralatan.

Dua *use case* utama pada potongan model ini adalah **Ajukan Peminjaman** dan **Catat Pengembalian Peralatan**. Realisasi kedua *use case* tersebut ditunjukkan melalui *collaboration* yang sesuai.

Seluruh fungsi Pertemuan 3 tetap berlaku dan harus tetap digambarkan dalam model, meliputi pemeriksaan ketersediaan peralatan saat pengajuan, pencetakan bukti pengajuan oleh mahasiswa, proses keputusan peminjaman oleh petugas, serta pembuatan laporan peminjaman untuk kepala laboratorium.

Diagram Pertemuan 4 merupakan pengembangan dari diagram Pertemuan 3 dengan menambahkan kebutuhan baru sesuai skenario. Dengan demikian, diagram Pertemuan 4 tidak menggantikan diagram Pertemuan 3, melainkan melanjutkan dan memperluas model yang sudah ada.

# kebutuhan sistem
| ID | Kebutuhan |
|---|---|
| LAB-R01 s.d. LAB-R06 | Kebutuhan Pertemuan 3 tetap berlaku dan tidak berubah arti (lihat Jobsheet Pertemuan 3). |
| LAB-R07 | Mahasiswa dan Dosen, sebagai Peminjam, dapat melihat ketersediaan peralatan dan mengajukan peminjaman. |
| LAB-R08 | Petugas laboratorium mengelola data peralatan dalam tiga bentuk khusus: tambah, ubah, dan hapus data peralatan. |
| LAB-R09 | Petugas laboratorium dapat mencatat pengembalian peralatan untuk peminjaman yang berstatus Dipinjam. |
| LAB-R10 | Sistem memeriksa dan mencatat kondisi peralatan sebagai bagian dari pencatatan pengembalian. |
| LAB-R11 | Model menunjukkan *collaboration* yang merealisasikan Ajukan Peminjaman dan Catat Pengembalian Peralatan. |

# Batas dan Aturan Sistem
    • Sistem mencatat dan menyediakan informasi; perpindahan fisik alat tidak
    terjadi di dalam perangkat lunak (tetap dari Pertemuan 3).
    • Pengguna telah terautentikasi dan memiliki hak akses sesuai peran (tetap
    dari Pertemuan 3).
    • Pengembalian hanya dapat dicatat untuk peminjaman berstatus Dipinjam.
    Peminjaman yang masih Menunggu Keputusan atau Ditolak tidak dapat
    dicatat pengembaliannya.
    • Kondisi peralatan pada pengembalian dicatat dengan salah satu nilai: Baik,
    Rusak Ringan, atau Rusak Berat.
    • Hapus Data Peralatan hanya untuk peralatan yang tidak sedang dipinjam
    dan tidak memiliki pengajuan aktif.
    • Keterlambatan dan denda belum dimodelkan pada pertemuan ini. Tuliskan
    sebagai pertanyaan terbuka pada berkas kebutuhan, jangan mengarang
    aturan denda.
    • Kriteria penerimaan model: semua kebutuhan LAB-R01 sampai LAB-R11
    mempunyai representasi pada diagram kumulatif, arah generalization dan
    realization benar, dan diagram konsisten dengan deskripsinya.

# Tentukan Aktor
| Aktor | Kedudukan | Tujuan terhadap Sistem |
|---|---|---|
| Peminjam | Umum (*general*), baru pada Pertemuan 4 | Berperan sebagai aktor umum bagi peminjam peralatan. Mewariskan fungsinya kepada Mahasiswa dan Dosen. |
| Mahasiswa | Khusus dari Peminjam, tetap dari Pertemuan 3 | Melihat ketersediaan dan mengajukan peminjaman (diwarisi dari Peminjam), serta mencetak bukti pengajuan sebagai asosiasi khususnya sendiri. |
| Dosen | Khusus dari Peminjam, baru pada Pertemuan 4 | Melihat ketersediaan dan mengajukan peminjaman (diwarisi dari Peminjam). |
| Petugas Laboratorium | Tetap dari Pertemuan 3 | Mengelola data peralatan, memproses keputusan peminjaman, dan mencatat pengembalian peralatan. |
| Kepala Laboratorium | Tetap dari Pertemuan 3 | Melihat laporan peminjaman. |

# Katalog Use case 
| ID | Nama Use Case | Peran dalam Model | Sumber Kebutuhan |
|---|---|---|---|
| LAB-UC01 | Lihat Ketersediaan Peralatan | Tetap dari Pertemuan 3; fungsi aktor umum Peminjam. | LAB-R01, LAB-R07 |
| LAB-UC02 | Kelola Data Peralatan | Tetap dari Pertemuan 3; use case umum bagi LAB-UC08, LAB-UC09, dan LAB-UC10. | LAB-R02, LAB-R08 |
| LAB-UC03 | Ajukan Peminjaman | Tetap dari Pertemuan 3; fungsi aktor umum Peminjam; menyertakan LAB-UC04; direalisasikan melalui LAB-CO01. | LAB-R03, LAB-R07 |
| LAB-UC04 | Periksa Ketersediaan | Tetap dari Pertemuan 3; perilaku yang disertakan (*include*) oleh LAB-UC03. | LAB-R03 |
| LAB-UC05 | Cetak Bukti Pengajuan | Tetap dari Pertemuan 3; tambahan bersyarat pada LAB-UC03 melalui relasi `«extend»`. | LAB-R04 |
| LAB-UC06 | Proses Keputusan Peminjaman | Tetap dari Pertemuan 3; fungsi utama petugas laboratorium. | LAB-R05 |
| LAB-UC07 | Lihat Laporan Peminjaman | Tetap dari Pertemuan 3; fungsi utama kepala laboratorium. | LAB-R06 |
| LAB-UC08 | Tambah Data Peralatan | Baru pada Pertemuan 4; use case khusus dari LAB-UC02. | LAB-R08 |
| LAB-UC09 | Ubah Data Peralatan | Baru pada Pertemuan 4; use case khusus dari LAB-UC02. | LAB-R08 |
| LAB-UC10 | Hapus Data Peralatan | Baru pada Pertemuan 4; use case khusus dari LAB-UC02. | LAB-R08 |
| LAB-UC11 | Catat Pengembalian Peralatan | Baru pada Pertemuan 4; fungsi utama petugas laboratorium; direalisasikan melalui LAB-CO02. | LAB-R09 |
| LAB-UC12 | Periksa Kondisi Peralatan | Baru pada Pertemuan 4; perilaku yang disertakan (*include*) oleh LAB-UC11. | LAB-R10 |

# Relasi Use case
| ID Relasi | Use Case Sumber | Jenis Relasi | Use Case Tujuan | Keterangan |
|---|---|---|---|---|
| REL-UC01 | Ajukan Peminjaman (LAB-UC03) | `<<include>>` | Periksa Ketersediaan (LAB-UC04) | Proses pengajuan peminjaman selalu menyertakan pemeriksaan ketersediaan peralatan. |
| REL-UC02 | Cetak Bukti Pengajuan (LAB-UC05) | `<<extend>>` | Ajukan Peminjaman (LAB-UC03) | Pencetakan bukti pengajuan merupakan perilaku tambahan yang bersyarat pada proses pengajuan peminjaman. |
| REL-UC03 | Tambah Data Peralatan (LAB-UC08) | Generalization | Kelola Data Peralatan (LAB-UC02) | Tambah data peralatan merupakan fungsi khusus dari pengelolaan data peralatan. |
| REL-UC04 | Ubah Data Peralatan (LAB-UC09) | Generalization | Kelola Data Peralatan (LAB-UC02) | Ubah data peralatan merupakan fungsi khusus dari pengelolaan data peralatan. |
| REL-UC05 | Hapus Data Peralatan (LAB-UC10) | Generalization | Kelola Data Peralatan (LAB-UC02) | Hapus data peralatan merupakan fungsi khusus dari pengelolaan data peralatan. |
| REL-UC06 | Catat Pengembalian Peralatan (LAB-UC11) | `<<include>>` | Periksa Kondisi Peralatan (LAB-UC12) | Proses pengembalian peralatan menyertakan pemeriksaan dan pencatatan kondisi peralatan. |