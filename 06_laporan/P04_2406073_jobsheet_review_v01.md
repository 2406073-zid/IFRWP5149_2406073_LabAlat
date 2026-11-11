# Hasil Review (P04)

## Tujuan

1. Memahami relasi generalization pada aktor dan use case, serta relasi include dan extend pada diagram use case.
2. Menyusun use case diagram untuk sistem laboratorium (LAB) dan Sistem Informasi Akademik (SIA).
3. Memahami fungsi collaboration sebagai realisasi use case.
4. Meninjau diagram dan dokumen deskripsi terhadap skenario dan notasi UML.

## Dasar Teori

**Generalization** menggambarkan hubungan induk-turunan. Turunan mewarisi hubungan dan perilaku induknya. Notasinya garis *solid* dengan kepala panah segitiga kosong yang mengarah ke induk. Pada aktor, contohnya *Mahasiswa* dan *Dosen* sebagai turunan *Peminjam* atau *Civitas Akademika*. Pada use case, contohnya *Tambah*, *Ubah*, dan *Hapus Data Peralatan* sebagai turunan *Kelola Data Peralatan*.

**Include** menunjukkan perilaku wajib yang selalu dijalankan oleh use case dasar (panah putus-putus dari use case dasar ke use case yang disertakan). **Extend** menunjukkan perilaku opsional yang menambah use case dasar pada kondisi tertentu (panah putus-putus dari use case yang memperluas ke use case dasar).

**Collaboration** (use case realization) menjelaskan bagaimana sebuah use case diwujudkan oleh sekumpulan objek yang berkolaborasi. Collaboration dimodelkan pada diagram tersendiri, terpisah dari use case diagram, agar batas antara kebutuhan fungsional (use case) dan realisasinya tidak tercampur.

**Konsistensi penamaan**: nama aktor dan use case pada diagram harus sama dengan istilah pada skenario sehingga mudah dicocokkan dan ditelusuri.

**Dokumen deskripsi use case** memuat ID, aktor, tujuan, prasyarat, pemicu, proses, relasi, dan pascakondisi untuk setiap use case.

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

## Kesimpulan

Secara umum, diagram LAB dan SIA telah merepresentasikan aktor, fungsi utama, serta relasi include, extend, dan generalization sesuai skenario, dan dokumen deskripsi sudah lengkap. Namun ada beberapa hal yang perlu diperbaiki:

1. **Notasi generalization** pada LAB tidak jelas (tanpa panah segitiga kosong) dan pada SIA digambar putus-putus; keduanya harus garis solid dengan segitiga kosong menuju induk.
2. **Duplikasi use case** *Catat Pengembalian Peralatan* perlu dihapus; gunakan satu use case saja.
3. **Penamaan aktor** LAB (*Petugas Laboran*, *Kepala Laboran*) perlu disamakan dengan skenario (*Petugas Laboratorium*, *Kepala Laboratorium*).
4. **Diagram collaboration** untuk *Input Nilai Mata Kuliah*, *Lihat KHS*, *Ajukan Peminjaman*, dan *Catat Pengembalian* belum ada dan harus dibuat sebagai artefak terpisah.

Setelah perbaikan tersebut, rancangan akan sesuai dengan skenario dan kaidah UML.