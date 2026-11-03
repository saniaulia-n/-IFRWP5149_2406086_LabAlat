Mahasiswa dan dosen sama-sama merupakan Civitas Akademika yang 
dapat melihat kalender akademik. Dosen menginput nilai mata kuliah yang 
diampunya setelah masa perkuliahan berakhir. Mahasiswa melihat Kartu 
Hasil Studi (KHS) untuk semester yang nilainya sudah dipublikasikan. Admin 
Akademik mengelola data mahasiswa: menambah data mahasiswa baru, 
mengubah data mahasiswa, dan menghapus data mahasiswa. Dua use case 
utama, Input Nilai Mata Kuliah dan Lihat KHS, ditunjukkan realisasinya oleh 
collaboration yang bersesuaian.

Batas dan asumsi 
• Kode kebutuhan dimulai dari SIA-R07 agar SIA-R01 dan SIA-R02 
(Pertemuan 2) serta SIA-R03 sampai SIA-R06 (Pertemuan 3) tetap 
mempunyai identitas berbeda. 
• Pengguna telah terautentikasi dan memiliki hak akses sesuai peran. 
• Kalender akademik pada tugas ini adalah agenda resmi institusi (awal 
semester, batas KRS, masa ujian, dan sejenisnya); jangan 
menyamakannya dengan jadwal kuliah pada Pertemuan 2. 
• Nilai hanya dapat diinput oleh dosen pengampu mata kuliah tersebut. Nilai 
yang diinput belum terpublikasi sebelum dinyatakan resmi oleh ketentuan 
tugas ini: KHS hanya menampilkan nilai yang sudah dipublikasikan. 
• Hapus Data Mahasiswa hanya untuk mahasiswa yang tidak memiliki data 
akademik aktif. Ketentuan ini fiktif untuk latihan. 
• Pengajuan KRS tetap digambar sebagai bagian diagram kumulatif dari 
Pertemuan 3. Pembayaran dan perancangan basis data berada di luar 
tugas ini.

Identifikasi Aktor dan Use Case

Katalog Use Case

| ID       | Nama Use Case             | Aktor Terkait                                   | Sumber  Kebutuhan | Status      |
| SIA-UC01 | Lihat Jadwal Kuliah       | Mahasiswa                                       | SIA-R01          | Tetap (P02) |
| SIA-UC02 | Kelola Jadwal Kuliah      | Admin Akademik                                  | SIA-R02          | Tetap (P02) |
| SIA-UC03 | Ajukan KRS                | Mahasiswa                                       | SIA-R03          | Tetap (P03) |
| SIA-UC04 | Validasi KRS              | Sistem (proses yang di-*include* oleh SIA-UC03) | SIA-R04          | Tetap (P03) |
| SIA-UC05 | Unduh Bukti Pengajuan KRS | Mahasiswa                                       | SIA-R05          | Tetap (P03) |
| SIA-UC06 | Proses Keputusan KRS      | Dosen Wali                                      | SIA-R06          | Tetap (P03) |
| SIA-UC07 | Lihat Kalender Akademik   | Civitas Akademika                               | SIA-R07          | Baru (P04)  |
| SIA-UC08 | Input Nilai Mata Kuliah   | Dosen                                           | SIA-R08          | Baru (P04)  |
| SIA-UC09 | Lihat KHS                 | Mahasiswa                                       | SIA-R09          | Baru (P04)  |
| SIA-UC10 | Kelola Data Mahasiswa     | Admin Akademik                                  | SIA-R10          | Baru (P04)  |
| SIA-UC11 | Tambah Data Mahasiswa     | Admin Akademik                                  | SIA-R11          | Baru (P04)  |
| SIA-UC12 | Ubah Data Mahasiswa       | Admin Akademik                                  | SIA-R11          | Baru (P04)  |
| SIA-UC13 | Hapus Data Mahasiswa      | Admin Akademik                                  | SIA-R11          | Baru (P04)  |

 Identifikasi Aktor
| Nama Aktor        | Kedudukan                           | Peran dalam Sistem                                                                                  |
|-------------------|-------------------------------------|-----------------------------------------------------------------------------------------------------|
| Civitas Akademika | Aktor umum, baru pada Pertemuan 4   | Melihat kalender akademik.                                                                          |
| Mahasiswa         | Aktor khusus dari Civitas Akademika | Melihat kalender akademik, melihat KHS, dan menjalankan fungsi mahasiswa dari pertemuan sebelumnya. |
| Dosen             | Aktor khusus dari Civitas Akademika | Melihat kalender akademik dan menginput nilai mata kuliah yang diampunya.                           |
| Admin Akademik    | Tetap dari pertemuan sebelumnya     | Mengelola jadwal kuliah dan data mahasiswa.                                                         |
| Dosen Wali        | Tetap dari pertemuan sebelumnya     | Menjalankan fungsi validasi dan proses keputusan KRS sesuai diagram sebelumnya.                     |

 Catatan Identifikasi

1 Katalog terdiri atas 13 *use case*, yaitu enam fungsi lama dan tujuh fungsi baru.
2 ID SIA-UC01 sampai SIA-UC06 dipertahankan sesuai katalog pertemuan sebelumnya.
3 Fungsi baru menggunakan ID SIA-UC07 sampai SIA-UC13.
4 SIA-UC04 — Validasi KRS merupakan perilaku yang disertakan dalam SIA-UC03 — Ajukan KRS melalui relasi `<<include>>`.
5 SIA-UC05 — Unduh Bukti Pengajuan KRS merupakan perilaku tambahan bersyarat pada SIA-UC03 — Ajukan KRS melalui relasi `<<extend>>`.
6 SIA-UC10 — Kelola Data Mahasiswa merupakan *use case* umum bagi SIA-UC11, SIA-UC12, dan SIA-UC13.
7 Generalization aktor dan *use case* ditetapkan lebih lanjut pada Langkah 3 dan Langkah 4

Hierarki Aktor

| Aktor Umum        | Aktor Khusus |
|-------------------|--------------|
| Civitas Akademika | Mahasiswa    |
| Civitas Akademika | Dosen        |

Mahasiswa dan Dosen merupakan aktor khusus dari Civitas Akademika. Keduanya mewarisi fungsi yang dimiliki aktor umum sesuai dengan kebutuhan tugas.

Fungsi yang Diwarisi

| Aktor Umum        | Aktor Khusus | Use Case yang Diwarisi             |
|-------------------|--------------|------------------------------------|
| Civitas Akademika | Mahasiswa    | SIA-UC07 — Lihat Kalender Akademik |
| Civitas Akademika | Dosen        | SIA-UC07 — Lihat Kalender Akademik |


Alasan Pemodelan
Generalization aktor digunakan karena Mahasiswa dan Dosen memiliki fungsi bersama, yaitu melihat kalender akademik. Civitas Akademika menjadi aktor umum yang mewakili fungsi tersebut, sedangkan Mahasiswa dan Dosen menjadi aktor khusus yang mewarisi fungsi dari aktor umum.
Asosiasi antara Civitas Akademika dan SIA-UC07 — Lihat Kalender Akademik digambarkan satu kali dari aktor umum. Asosiasi tersebut tidak digambar ulang dari Mahasiswa dan Dosen karena fungsi tersebut diwarisi melalui generalization aktor.

Tetapkan Generalization Use Case
Hierarki Use Case
| Use Case Umum                    | Use Case Khusus                  |
|----------------------------------|----------------------------------|
| SIA-UC10 — Kelola Data Mahasiswa | SIA-UC11 — Tambah Data Mahasiswa |
| SIA-UC10 — Kelola Data Mahasiswa | SIA-UC12 — Ubah Data Mahasiswa   |
| SIA-UC10 — Kelola Data Mahasiswa | SIA-UC13 — Hapus Data Mahasiswa  |

Perilaku Pembeda Setiap Use Case Khusus
1 SIA-UC11 — Tambah Data Mahasiswa:Admin Akademik menambahkan data mahasiswa baru ke dalam sistem.
2 SIA-UC12 — Ubah Data Mahasiswa:Admin Akademik mengubah data mahasiswa yang telah tersimpan di dalam sistem.
3 SIA-UC13 — Hapus Data Mahasiswa:Admin Akademik menghapus data mahasiswa yang tidak memiliki data akademik aktif, sesuai batasan dan asumsi tugas

Tetapkan Collaboration
Daftar Collaboration

| ID Collaboration | Nama Collaboration      | Use Case yang Direalisasikan       |
|------------------|-------------------------|------------------------------------|
| SIA-CO01         | Input Nilai Mata Kuliah | SIA-UC08 — Input Nilai Mata Kuliah |
| SIA-CO02         | Lihat KHS               | SIA-UC09 — Lihat KHS               |

Keterangan

1 SIA-CO01 — Input Nilai Mata Kuliah merealisasikan SIA-UC08 — Input Nilai Mata Kuliah.
2 SIA-CO02 — Lihat KHS merealisasikan SIA-UC09 — Lihat KHS.

 Susun use case description 

1 SIA-UC08: Input Nilai Mata Kuliah


| Elemen | SIA-UC08: Input Nilai Mata Kuliah |
| ID dan nama | SIA-UC08: Input Nilai Mata Kuliah |
| Sumber kebutuhan | SIA-R08 |
| Tujuan | Nilai mahasiswa untuk mata kuliah yang diampu dosen berhasil dicatat dalam sistem. |
| Aktor utama | Dosen |
| Pemicu | Dosen memilih fungsi input nilai dan menentukan mata kuliah yang akan diinput nilainya. |
| Prasyarat | Dosen telah terautentikasi dan merupakan dosen pengampu mata kuliah yang dipilih. Data mata kuliah dan mahasiswa terkait tersedia di sistem. |
| Pascakondisi berhasil | Nilai mahasiswa berhasil disimpan dan tercatat pada mata kuliah yang sesuai. Nilai belum dianggap dipublikasikan sampai proses publikasi resmi dilakukan. |
| Pascakondisi gagal | Nilai baru tidak tersimpan atau tidak mengubah nilai yang telah tersimpan. Data nilai sebelumnya tetap terjaga. |
| Include | Tidak ada. |
| Collaboration | SIA-CO01: Input Nilai Mata Kuliah |

### Alur Utama

| Langkah | Tindakan Dosen | Respons Sistem |
| 1 | Memilih fungsi input nilai mata kuliah. | Menampilkan daftar mata kuliah yang diampu dosen. |
| 2 | Memilih mata kuliah yang akan diinput nilainya. | Menampilkan daftar mahasiswa yang terdaftar pada mata kuliah tersebut beserta kolom input nilai. |
| 3 | Mengisi nilai mahasiswa sesuai ketentuan yang berlaku. | Menampung nilai yang dimasukkan dosen. |
| 4 | Mengonfirmasi penyimpanan nilai. | Memeriksa hak akses dosen dan memastikan nilai berada dalam rentang yang sah. |
| 5 | Menyimpan nilai. | Menyimpan nilai mahasiswa pada mata kuliah yang sesuai tanpa memublikasikannya secara otomatis. |
| 6 | Melihat hasil penyimpanan. | Menampilkan konfirmasi bahwa nilai berhasil disimpan. |

### Alur Alternatif atau Pengecualian

- **A1: Dosen bukan pengampu mata kuliah yang dipilih (pada langkah 4).** Sistem menolak penyimpanan nilai dan menampilkan pemberitahuan bahwa dosen tidak memiliki hak untuk menginput nilai pada mata kuliah tersebut. Pascakondisi gagal berlaku.

- **A2: Nilai berada di luar rentang yang sah (pada langkah 4).** Sistem menolak nilai yang tidak valid dan menampilkan pemberitahuan agar dosen memperbaiki isian. Nilai yang ditolak tidak disimpan; dosen dapat memperbaiki nilai dan mencoba menyimpan kembali.

- **A3: Penyimpanan gagal (pada langkah 5).** Sistem menampilkan pemberitahuan bahwa penyimpanan gagal. Nilai baru tidak dianggap berhasil tersimpan dan pascakondisi gagal berlaku.


## 2. SIA-UC09: Lihat KHS

### Informasi *Use Case*

| Elemen                | SIA-UC09: Lihat KHS                                                                        |
|-----------------------|--------------------------------------------------------------------------------------------|
| ID dan nama           | SIA-UC09: Lihat KHS                                                                        |
| Sumber kebutuhan      | SIA-R09                                                                                    |
| Tujuan                | Mahasiswa dapat melihat Kartu Hasil Studi (KHS) untuk semester yang dipilih.               |
| Aktor utama           | Mahasiswa                                                                                  |
| Pemicu                | Mahasiswa memilih fungsi lihat KHS dan menentukan semester yang ingin dilihat.             |
| Prasyarat             | Mahasiswa telah terautentikasi dan data akademiknya tersedia di sistem.                    |
| Pascakondisi berhasil | KHS semester yang dipilih ditampilkan dengan hanya memuat nilai yang sudah dipublikasikan. |
| Pascakondisi gagal    | KHS tidak ditampilkan apabila data tidak tersedia atau terjadi kegagalan pemrosesan.       |
| Include               | Tidak ada.                                                                                 |
| Collaboration         | SIA-CO02: Lihat KHS                                                                        |

### Alur Utama

| Langkah | Tindakan Mahasiswa                   | Respons Sistem                                                     |
|--------:|--------------------------------------|--------------------------------------------------------------------|
|       1 | Memilih fungsi lihat KHS.            | Menampilkan pilihan semester yang tersedia.                        |
|       2 | Memilih semester yang ingin dilihat. | Mengambil data KHS untuk semester yang dipilih.                    |
|       3 | Melihat KHS.                         | Menampilkan KHS yang hanya berisi nilai yang sudah dipublikasikan. |

### Alur Alternatif atau Pengecualian

- **A1: Belum ada nilai yang dipublikasikan.** Sistem tidak menampilkan nilai yang belum dipublikasikan dan memberikan informasi bahwa KHS belum tersedia atau belum lengkap untuk semester tersebut.

- **A2: Data KHS tidak tersedia atau gagal diproses.** Sistem menampilkan informasi bahwa KHS tidak dapat ditampilkan. Pascakondisi gagal berlaku.
