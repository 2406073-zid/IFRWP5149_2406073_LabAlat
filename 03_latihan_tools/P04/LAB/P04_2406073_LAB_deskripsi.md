# Deskripsi Use Case LAB

Dokumen ini merangkum aktor, tujuan, alur, relasi, dan kondisi akhir use case pada model P04. Uraian mengikuti skenario P04 dan diagram use case terkait.

## Daftar Use Case

### LAB-UC01 ? Lihat Ketersediaan Peralatan

| Elemen | Deskripsi |
|---|---|
| ID Use Case | LAB-UC01 |
| Nama Use Case | Lihat Ketersediaan Peralatan |
| Aktor | Peminjam (Mahasiswa atau Dosen) |
| Tujuan | Peminjam mengetahui status ketersediaan alat. |
| Prasyarat | Pengguna telah terautentikasi dan memiliki hak akses sesuai peran. |
| Pemicu | Peminjam membuka menu ketersediaan. |
| Deskripsi Proses | Sistem menampilkan daftar peralatan dan status ketersediaannya. |
| Relasi Use Case | Tidak ada relasi khusus. |
| Pascakondisi | Peminjam dapat melihat daftar peralatan. |

### LAB-UC02 ? Kelola Data Peralatan

| Elemen | Deskripsi |
|---|---|
| ID Use Case | LAB-UC02 |
| Nama Use Case | Kelola Data Peralatan |
| Aktor | Petugas Laboratorium |
| Tujuan | Petugas mengakses fungsi tambah, ubah, dan hapus data peralatan. |
| Prasyarat | Pengguna telah terautentikasi dan memiliki hak akses sesuai peran. |
| Pemicu | Petugas membuka menu Kelola Data Peralatan. |
| Deskripsi Proses | Sistem menampilkan data alat dan menyediakan pilihan tambah, ubah, atau hapus. |
| Relasi Use Case | Tidak ada relasi khusus. |
| Pascakondisi | Petugas memilih proses pengelolaan; detail ada pada LAB-UC08 s.d. LAB-UC10. |

### LAB-UC03 ? Ajukan Peminjaman

| Elemen | Deskripsi |
|---|---|
| ID Use Case | LAB-UC03 |
| Nama Use Case | Ajukan Peminjaman |
| Aktor | Peminjam (Mahasiswa atau Dosen) |
| Tujuan | Peminjam mengajukan peralatan untuk kegiatan praktikum atau penelitian. |
| Prasyarat | Pengguna telah terautentikasi dan memiliki hak akses sesuai peran. |
| Pemicu | Peminjam memilih alat dan mengirim pengajuan. |
| Deskripsi Proses | Sistem menyertakan LAB-UC04 untuk memeriksa ketersediaan, lalu menyimpan pengajuan jika tersedia. |
| Relasi Use Case | `<<include>>` LAB-UC04 Periksa Ketersediaan; direalisasikan oleh collaboration pengajuan. |
| Pascakondisi | Pengajuan tersimpan dengan status Menunggu Keputusan jika pemeriksaan berhasil. |

### LAB-UC04 ? Periksa Ketersediaan

| Elemen | Deskripsi |
|---|---|
| ID Use Case | LAB-UC04 |
| Nama Use Case | Periksa Ketersediaan |
| Aktor | Sistem; dipanggil oleh LAB-UC03 |
| Tujuan | Memastikan peralatan tersedia sebelum pengajuan disimpan. |
| Prasyarat | Pengguna telah terautentikasi dan memiliki hak akses sesuai peran. |
| Pemicu | Sistem menerima pilihan alat dari alur pengajuan. |
| Deskripsi Proses | Sistem memeriksa jumlah dan status alat lalu mengembalikan hasil pemeriksaan. |
| Relasi Use Case | `<<include>>` dari LAB-UC03 Ajukan Peminjaman. |
| Pascakondisi | Hasil pemeriksaan tersedia bagi LAB-UC03. |

### LAB-UC05 ? Cetak Bukti Pengajuan

| Elemen | Deskripsi |
|---|---|
| ID Use Case | LAB-UC05 |
| Nama Use Case | Cetak Bukti Pengajuan |
| Aktor | Mahasiswa |
| Tujuan | Mahasiswa memperoleh bukti pengajuan peminjaman. |
| Prasyarat | Pengguna telah terautentikasi dan memiliki hak akses sesuai peran. |
| Pemicu | Mahasiswa memilih opsi cetak setelah pengajuan. |
| Deskripsi Proses | Sistem menyiapkan dan mencetak bukti pengajuan. |
| Relasi Use Case | `<<extend>>` LAB-UC03 Ajukan Peminjaman, jika mahasiswa memilih cetak. |
| Pascakondisi | Bukti tercetak sebagai perilaku opsional `<<extend>>` LAB-UC03. |

### LAB-UC06 ? Proses Keputusan Peminjaman

| Elemen | Deskripsi |
|---|---|
| ID Use Case | LAB-UC06 |
| Nama Use Case | Proses Keputusan Peminjaman |
| Aktor | Petugas Laboratorium |
| Tujuan | Petugas menentukan persetujuan atau penolakan pengajuan. |
| Prasyarat | Pengguna telah terautentikasi dan memiliki hak akses sesuai peran. |
| Pemicu | Petugas membuka daftar pengajuan Menunggu Keputusan. |
| Deskripsi Proses | Sistem menampilkan pengajuan; petugas memilih keputusan dan sistem memperbarui status. |
| Relasi Use Case | Tidak ada relasi khusus. |
| Pascakondisi | Status pengajuan menjadi Disetujui atau Ditolak. |

### LAB-UC07 ? Lihat Laporan Peminjaman

| Elemen | Deskripsi |
|---|---|
| ID Use Case | LAB-UC07 |
| Nama Use Case | Lihat Laporan Peminjaman |
| Aktor | Kepala Laboratorium |
| Tujuan | Kepala laboratorium melihat laporan peminjaman. |
| Prasyarat | Pengguna telah terautentikasi dan memiliki hak akses sesuai peran. |
| Pemicu | Kepala laboratorium membuka menu laporan dan memilih periode. |
| Deskripsi Proses | Sistem menampilkan laporan untuk periode yang dipilih. |
| Relasi Use Case | Tidak ada relasi khusus. |
| Pascakondisi | Laporan peminjaman periode terpilih ditampilkan. |

### LAB-UC08 ? Tambah Data Peralatan

| Elemen | Deskripsi |
|---|---|
| ID Use Case | LAB-UC08 |
| Nama Use Case | Tambah Data Peralatan |
| Aktor | Petugas Laboratorium |
| Tujuan | Petugas menambahkan data alat baru. |
| Prasyarat | Pengguna telah terautentikasi dan memiliki hak akses sesuai peran. |
| Pemicu | Petugas memilih Tambah Data Peralatan. |
| Deskripsi Proses | Sistem menampilkan formulir, memvalidasi data, menyimpan data baru, dan menampilkan konfirmasi. |
| Relasi Use Case | Generalization dari LAB-UC02 Kelola Data Peralatan. |
| Pascakondisi | Data peralatan baru tersimpan; generalization dari LAB-UC02. |

### LAB-UC09 ? Ubah Data Peralatan

| Elemen | Deskripsi |
|---|---|
| ID Use Case | LAB-UC09 |
| Nama Use Case | Ubah Data Peralatan |
| Aktor | Petugas Laboratorium |
| Tujuan | Petugas memperbarui data alat. |
| Prasyarat | Pengguna telah terautentikasi dan memiliki hak akses sesuai peran. |
| Pemicu | Petugas memilih Ubah Data Peralatan dan memilih alat. |
| Deskripsi Proses | Sistem menampilkan data saat ini; petugas mengubahnya; sistem memvalidasi dan menyimpan perubahan. |
| Relasi Use Case | Generalization dari LAB-UC02 Kelola Data Peralatan. |
| Pascakondisi | Data peralatan diperbarui; generalization dari LAB-UC02. |

### LAB-UC10 ? Hapus Data Peralatan

| Elemen | Deskripsi |
|---|---|
| ID Use Case | LAB-UC10 |
| Nama Use Case | Hapus Data Peralatan |
| Aktor | Petugas Laboratorium |
| Tujuan | Petugas menghapus data alat yang sudah tidak digunakan. |
| Prasyarat | Pengguna telah terautentikasi dan memiliki hak akses sesuai peran. |
| Pemicu | Petugas memilih Hapus Data Peralatan dan memilih alat. |
| Deskripsi Proses | Sistem memastikan alat tidak sedang dipinjam dan tidak memiliki pengajuan aktif, lalu meminta konfirmasi sebelum menghapus. |
| Relasi Use Case | Generalization dari LAB-UC02 Kelola Data Peralatan. |
| Pascakondisi | Data dihapus hanya jika aturan penghapusan terpenuhi; generalization dari LAB-UC02. |

### LAB-UC11 ? Catat Pengembalian Peralatan

| Elemen | Deskripsi |
|---|---|
| ID Use Case | LAB-UC11 |
| Nama Use Case | Catat Pengembalian Peralatan |
| Aktor | Petugas Laboratorium |
| Tujuan | Petugas mencatat kembalinya alat dan memperbarui statusnya. |
| Prasyarat | Pengguna telah terautentikasi dan memiliki hak akses sesuai peran. |
| Pemicu | Petugas memilih peminjaman berstatus Dipinjam. |
| Deskripsi Proses | Sistem menampilkan data peminjaman; petugas mengonfirmasi alat kembali dan mencatat kondisi melalui LAB-UC12. |
| Relasi Use Case | `<<include>>` LAB-UC12 Periksa Kondisi Peralatan; direalisasikan oleh collaboration pengembalian. |
| Pascakondisi | Pengembalian tercatat dan status peminjaman diperbarui. |

### LAB-UC12 ? Periksa Kondisi Peralatan

| Elemen | Deskripsi |
|---|---|
| ID Use Case | LAB-UC12 |
| Nama Use Case | Periksa Kondisi Peralatan |
| Aktor | Sistem; dipanggil oleh LAB-UC11 |
| Tujuan | Mencatat kondisi alat saat pengembalian. |
| Prasyarat | Pengguna telah terautentikasi dan memiliki hak akses sesuai peran. |
| Pemicu | Alur LAB-UC11 meminta pencatatan kondisi. |
| Deskripsi Proses | Petugas memilih kondisi Baik, Rusak Ringan, atau Rusak Berat; sistem menyimpan kondisi. |
| Relasi Use Case | `<<include>>` oleh LAB-UC11 Catat Pengembalian Peralatan. |
| Pascakondisi | Kondisi alat tercatat; `<<include>>` oleh LAB-UC11. |

## Catatan Model

Sistem hanya mencatat dan menyediakan informasi. Perpindahan alat dilakukan di luar sistem. Pengembalian hanya berlaku untuk peminjaman berstatus Dipinjam; kondisi yang dicatat adalah Baik, Rusak Ringan, atau Rusak Berat. Penghapusan data alat tidak berlaku jika alat sedang dipinjam atau memiliki pengajuan aktif.
