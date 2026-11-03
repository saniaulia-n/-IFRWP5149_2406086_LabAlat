| No. | Sumber | Hubungan | Tujuan |
|---:|---|---|---|
| 1 | Mahasiswa | Association | SIA-UC01 Lihat Jadwal Kuliah |
| 2 | Admin Akademik | Association | SIA-UC02 Kelola Jadwal Kuliah |
| 3 | Mahasiswa | Association | SIA-UC03 Ajukan KRS |
| 4 | Mahasiswa | Association | SIA-UC05 Unduh Bukti Pengajuan KRS |
| 5 | Dosen Wali | Association | SIA-UC06 Proses Keputusan KRS |
| 6 | Mahasiswa | Generalization → | Civitas Akademika |
| 7 | Dosen | Generalization → | Civitas Akademika |
| 8 | Civitas Akademika | Association | SIA-UC07 Lihat Kalender Akademik |
| 9 | Dosen | Association | SIA-UC08 Input Nilai Mata Kuliah |
| 10 | Mahasiswa | Association | SIA-UC09 Lihat KHS |
| 11 | Admin Akademik | Association | SIA-UC10 Kelola Data Mahasiswa |
| 12 | SIA-UC03 Ajukan KRS | `<<include>>` | SIA-UC04 Validasi KRS |
| 13 | SIA-UC05 Unduh Bukti Pengajuan KRS | `<<extend>>` | SIA-UC03 Ajukan KRS |
| 14 | SIA-UC11 Tambah Data Mahasiswa | Generalization → | SIA-UC10 Kelola Data Mahasiswa |
| 15 | SIA-UC12 Ubah Data Mahasiswa | Generalization → | SIA-UC10 Kelola Data Mahasiswa |
| 16 | SIA-UC13 Hapus Data Mahasiswa | Generalization → | SIA-UC10 Kelola Data Mahasiswa |
| 17 | SIA-CO01 (collaboration) | Realization → | SIA-UC08 Input Nilai Mata Kuliah |
| 18 | SIA-CO02 (collaboration) | Realization → | SIA-UC09 Lihat KHS | 
 