## Hasil Review

| No. | Aspek yang Ditinjau | Hasil Review | Alasan |
|---:|---|---|---|
| 1 | Aktor LAB | Diagram memuat Peminjam, Petugas Laboran, dan Kepala Laboran; Mahasiswa dan Dosen menjadi turunan Peminjam. | Aktor sesuai dengan fungsi peminjaman, pengelolaan alat, keputusan, pengembalian, dan laporan. |
| 2 | Use case LAB | Diagram mencakup melihat ketersediaan, mengajukan peminjaman, mengelola data alat, memproses keputusan, melihat laporan, dan mencatat pengembalian. | Fungsi utama pada skenario P04 telah direpresentasikan. |
| 3 | Relasi include dan extend LAB | Ajukan Peminjaman menyertakan Periksa Ketersediaan; Cetak Bukti Pengajuan memperluas Ajukan Peminjaman; Catat Pengembalian menyertakan Periksa Kondisi. | Arah relasi sesuai dengan perilaku wajib dan perilaku opsional pada skenario. |
| 4 | Generalization LAB | Generalization Peminjam ke Mahasiswa/Dosen dan Kelola Data Peralatan ke Tambah/Ubah/Hapus tampak sebagai garis tanpa kepala panah segitiga yang jelas. | Generalization UML perlu garis solid dengan panah segitiga kosong yang mengarah ke induk. |
| 5 | Catat Pengembalian LAB | Terdapat dua label use case Catat Pengembalian Peralatan, satu memakai kapitalisasi berbeda, yang dihubungkan garis putus-putus. | Duplikasi membuat batas antara use case dan realisasi/collaboration tidak jelas. Gunakan satu use case dan tampilkan collaboration pada model terpisah atau dengan notasi yang diterangkan. |
| 6 | Istilah aktor LAB | Diagram memakai nama Petugas Laboran dan Kepala Laboran, sedangkan skenario memakai Petugas Laboratorium dan Kepala Laboratorium. | Samakan istilah dengan skenario agar aktor mudah dicocokkan. |
| 7 | Aktor dan fungsi SIA | Civitas Akademika menjadi aktor umum bagi Mahasiswa dan Dosen; Admin Akademik mengelola data mahasiswa. | Pembagian aktor konsisten dengan skenario. |
| 8 | Use case dan relasi SIA | Diagram mencakup kalender akademik, input nilai, KHS, kelola data mahasiswa, serta use case validasi, penyimpanan nilai, pemeriksaan publikasi, dan penampilan KHS. | Relasi include untuk input nilai dan KHS serta generalization untuk tambah/ubah/hapus sesuai katalog. |
| 9 | Notasi generalization SIA | Garis generalization Mahasiswa dan Dosen ke Civitas Akademika ditampilkan putus-putus. | Generalization UML menggunakan garis solid dan segitiga kosong; arah menuju aktor umum sudah benar. |
| 10 | Collaboration P04 | Skenario P04 menyebut realisasi Input Nilai Mata Kuliah, Lihat KHS, Ajukan Peminjaman, dan Catat Pengembalian melalui collaboration, tetapi berkas diagram P04 yang ditinjau hanya berisi diagram use case. | Tambahkan diagram collaboration yang diminta pada artefak terpisah dan pastikan use case yang direalisasikan cocok dengan skenario. |
| 11 | Dokumen deskripsi | Dokumen deskripsi LAB dan SIA telah memuat ID, aktor, tujuan, prasyarat, pemicu, proses, relasi, dan pascakondisi setiap use case. | Struktur deskripsi membuat perilaku dan hubungan use case dapat ditelusuri ke skenario. |

