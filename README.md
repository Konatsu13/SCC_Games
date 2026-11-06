# SCC Maze Challenge

**SCC Maze Challenge** adalah game maze 2D bergaya retro/pixel yang dibuat untuk **Stematel Creative Challenge**. Pemain harus menjelajahi labirin, mengumpulkan lima kunci, menjawab soal, menghindari monster dan jebakan, lalu mencapai pintu keluar secepat mungkin.

Game berjalan langsung di browser tanpa instalasi dependency atau proses build.

## Fitur

- **Maze 2D:** labirin berukuran 45 × 45 tile dengan tata letak yang dibangkitkan dari seed tetap.
- **Eksplorasi:** kumpulkan 5 kunci yang tersebar di dalam labirin untuk membuka akses ke pintu keluar.
- **Kuis edukatif:** jawab soal pilihan ganda untuk membuka pintu dan menghadapi serangan monster.
- **Bank soal:** 252 soal utama dari Matematika, IPS, Sejarah Indonesia, Bahasa Indonesia, Bahasa Inggris, dan Pengetahuan Umum, serta 40 soal Matematika Cepat untuk tantangan monster.
- **Monster:** tujuh monster berpatroli dan dapat mengejar pemain ketika berada dalam jarak tertentu.
- **Jebakan spike:** jebakan dengan fase aman, peringatan, dan aktif.
- **Sistem nyawa dan streak:** pemain memulai dengan 5 nyawa; setiap 3 jawaban benar berturut-turut memulihkan 1 nyawa (maksimal 5).
- **Skor dan rank:** skor dihitung dari jawaban, kunci, nyawa, streak, dan keberhasilan menyelesaikan maze.
- **Papan skor lokal:** simpan hingga 100 catatan hasil dan tampilkan 10 skor terbaik pada perangkat/browser yang sama.
- **Simpan progres:** progres permainan dapat dilanjutkan dari menu utama.
- **Pengaturan:** volume musik, volume efek suara, sensitivitas joystick, dan tingkat kesulitan.
- **Audio 8-bit:** musik dan efek suara dibuat menggunakan Web Audio API, tanpa file audio eksternal.
- **Kontrol desktop dan mobile:** keyboard untuk desktop serta joystick dan tombol sentuh untuk perangkat layar sentuh.
- **Minimap dan efek visual:** bantu navigasi dengan minimap, HUD, serta umpan balik visual ketika mengambil kunci atau terkena efek permainan.

## Cara Menjalankan

### Opsi 1 — Langsung dari browser

1. Unduh atau clone repository ini.
2. Buka folder project.
3. Buka file `index.html` menggunakan browser modern.

### Opsi 2 — Menggunakan local development server

Jika ingin menjalankannya melalui server lokal, gunakan salah satu opsi berikut:

**Python**
```bash
python -m http.server 8000
```

Kemudian buka `http://localhost:8000` di browser.

**Node.js (npx)**
```bash
npx serve .
```

Buka alamat lokal yang ditampilkan oleh terminal.

> Project ini berupa aplikasi web statis. Tidak terdapat `package.json` atau langkah instalasi dependency pada struktur yang digunakan saat ini.

## Cara Bermain

1. Pilih **MULAI** pada menu utama.
2. Jelajahi maze dan temukan lima kunci.
3. Dekati pintu kayu, lalu tekan tombol interaksi.
4. Jawab soal dengan benar agar pintu terbuka selama 12 detik.
5. Hindari monster. Ketika tertangkap, pemain mendapat tantangan soal dengan batas waktu.
6. Perhatikan jebakan spike dan fase aktifnya.
7. Setelah mengumpulkan lima kunci, cari pintu keluar di bagian kanan bawah maze.
8. Setelah berhasil keluar, masukkan nama (opsional) untuk menyimpan hasil ke papan skor lokal.

### Aturan penting

- Pemain memulai permainan dengan **5 nyawa**.
- Jawaban salah atau waktu habis pada soal serangan monster mengurangi 1 nyawa.
- Jawaban salah pada soal pintu tidak mengurangi nyawa.
- Tiga jawaban benar berturut-turut memulihkan 1 nyawa, hingga maksimal 5.
- Terkena spike memperlambat gerakan dan menambahkan 3 detik pada waktu permainan.
- Hanya permainan yang berhasil diselesaikan dengan mencapai pintu keluar yang dapat dicatat di papan skor.

## Kontrol

| Aksi | Desktop | Mobile |
|---|---|---|
| Bergerak | `W`, `A`, `S`, `D` atau tombol panah | Joystick virtual |
| Interaksi dengan pintu | `E` atau `Spasi` | Tombol `E` |
| Pause / lanjut | `Esc` atau tombol **PAUSE** | Tombol `II` |
| Aktif/nonaktif audio | `M` atau tombol audio | Tombol audio pada HUD |

Jawaban kuis dipilih dengan klik atau sentuhan pada opsi jawaban. Tidak ada shortcut keyboard untuk memilih jawaban kuis.

## Tingkat Kesulitan

Pengaturan menyediakan tiga pilihan:

- **Mudah**
- **Normal**
- **Sulit**

Tingkat kesulitan memengaruhi kecepatan dan jarak pandang monster.

## Penyimpanan Data

Game menggunakan **`localStorage` browser** untuk menyimpan data secara lokal, antara lain:

- Papan skor.
- Progres permainan yang belum selesai.
- Pengaturan audio, sensitivitas joystick, dan tingkat kesulitan.
- Nama pemain yang terakhir digunakan.

Data tersebut hanya tersedia pada browser dan perangkat tempat game dimainkan. Data tidak dikirim ke server dan tidak otomatis tersinkron ke perangkat lain. Menghapus data situs/browser dapat menghapus data permainan yang tersimpan.

Papan skor menampilkan maksimal 10 hasil terbaik. Jika skor sama, hasil dengan waktu penyelesaian lebih cepat ditempatkan lebih tinggi.

## Teknologi

- **HTML5** — struktur halaman dan antarmuka.
- **CSS3** — tampilan retro, layout responsif, HUD, menu, dan animasi.
- **JavaScript (Vanilla)** — logika permainan, maze, pergerakan, monster, kuis, skor, dan penyimpanan.
- **HTML Canvas 2D** — rendering maze, karakter, monster, dan minimap.
- **Web Audio API** — pembuatan musik dan efek suara 8-bit.
- **Web Storage API (`localStorage`)** — penyimpanan progres, pengaturan, dan papan skor lokal.

Tidak menggunakan framework frontend atau database/server backend.

## Struktur Repository

```text
SCC_Games/
└── index.html   # Seluruh aplikasi: HTML, CSS, dan JavaScript game
```

## Kompatibilitas

Gunakan browser modern yang mendukung HTML5 Canvas, JavaScript, Web Audio API, dan `localStorage`. Untuk pengalaman terbaik, gunakan browser versi terbaru. Pada perangkat mobile, kontrol sentuh akan ditampilkan ketika perangkat terdeteksi mendukung pointer sentuh.

## Batasan Saat Ini

- Papan skor bersifat lokal, bukan leaderboard online.
- Data permainan tidak tersinkron antarbrowser atau perangkat.
- Game belum menggunakan akun pemain atau backend.
- Tata letak maze menggunakan seed tetap sehingga pola maze dibuat secara deterministik.

## Repository

Source code: [github.com/Konatsu13/SCC_Games](https://github.com/Konatsu13/SCC_Games)

---

Dibuat untuk **Stematel Creative Challenge**.
