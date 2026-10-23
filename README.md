<div align="center">

# Tugas Pendahuluan Modul 6

**Pemrograman Web · JavaScript & jQuery**

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)
![jQuery](https://img.shields.io/badge/jQuery-0769AD?style=flat&logo=jquery&logoColor=white)

</div>

<br>

|           |               |
| :-------- | :------------ |
| **Nama**  | Ilham Fadilah |
| **NIM**   | 103092400051  |
| **Kelas** | WEBPRO-IT0701 |

<br>

## Daftar Isi

- [Struktur File](#struktur-file)
- [Soal 1 – Apa itu JavaScript?](#1-apa-itu-javascript-dan-apa-kegunaannya)
- [Soal 2 – Apa itu jQuery?](#2-apa-itu-jquery-dan-apa-kegunaannya)
- [Soal 3 – Perbedaan JavaScript dan jQuery](#3-perbedaan-javascript-dan-jquery)
- [Soal 4 – Prompt Nama dan NIM](#soal-4--soal1html)
- [Soal 5 – Bermain dengan Warna](#soal-5--soal2html)
- [Cara Menjalankan](#cara-menjalankan)

<br>

## Struktur File

```text
WEBPRO_TP_MOD_06_IlhamFadilah/
├── soal1.html     → Soal 4 (JavaScript)
├── style1.css     → tampilan soal1.html
├── soal2.html     → Soal 5 (jQuery)
├── style2.css     → tampilan soal2.html
└── README.md      → jawaban soal 1–3 dan penjelasan program
```

---

## Jawaban Soal

### 1. Apa itu JavaScript dan apa kegunaannya?

**JavaScript** adalah bahasa pemrograman yang dijalankan langsung oleh browser. Kalau HTML berfungsi sebagai kerangka halaman dan CSS sebagai tampilannya, maka JavaScript membuat halaman tersebut bisa **bergerak dan merespons pengguna**. JavaScript juga bisa dipakai di sisi server lewat Node.js.

**Kegunaan utamanya:**

| Kegunaan                   | Penjelasan singkat                                                       |
| :------------------------- | :----------------------------------------------------------------------- |
| Mengubah isi halaman       | Mengganti teks, gambar, atau gaya elemen tanpa memuat ulang halaman      |
| Merespons aksi pengguna    | Menjalankan kode saat tombol diklik, form dikirim, atau keyboard ditekan |
| Validasi form              | Memeriksa isian pengguna sebelum dikirim ke server                       |
| Mengambil data dari server | Memuat data baru di latar belakang (AJAX / Fetch)                        |
| Animasi dan efek           | Membuat tampilan lebih hidup                                             |
| Membuat aplikasi           | Aplikasi web, server (Node.js), hingga mobile                            |

> [!NOTE]
> Contoh di tugas ini: `prompt()` dipakai untuk meminta nama dan NIM, lalu `document.getElementById()` dipakai untuk menampilkannya ke form.

### 2. Apa itu jQuery dan apa kegunaannya?

**jQuery** adalah _library_ JavaScript, yaitu kumpulan kode siap pakai yang dibuat untuk **mempersingkat penulisan JavaScript**. Semboyannya _"write less, do more"_ (tulis lebih sedikit, hasilkan lebih banyak). Agar bisa dipakai, file jQuery harus dimuat lebih dulu, misalnya lewat CDN.

**Kegunaan utamanya:**

| Kegunaan                          | Contoh                                          |
| :-------------------------------- | :---------------------------------------------- |
| Memilih elemen HTML dengan mudah  | `$("#kotakWarna")`                              |
| Mengubah tampilan atau isi elemen | `.css()`, `.text()`, `.html()`, `.addClass()`   |
| Menangani event                   | `.click()`, `.on()`                             |
| Efek dan animasi bawaan           | `.hide()`, `.show()`, `.fadeIn()`, `.slideUp()` |
| Memudahkan AJAX                   | `$.ajax()`, `$.get()`, `$.post()`               |
| Berjalan sama di berbagai browser | Perbedaan antar browser sudah ditangani jQuery  |

> [!NOTE]
> Contoh di tugas ini: tombol warna memakai `.css()`, sedangkan tombol sembunyikan dan tampilkan memakai `.hide()` dan `.show()`.

### 3. Perbedaan JavaScript dan jQuery

Singkatnya: **JavaScript adalah bahasanya, jQuery adalah alat bantunya.** jQuery ditulis menggunakan JavaScript, jadi jQuery tidak bisa berjalan tanpa JavaScript.

| Aspek             | JavaScript                                     | jQuery                                           |
| :---------------- | :--------------------------------------------- | :----------------------------------------------- |
| Jenis             | Bahasa pemrograman                             | Library (kumpulan kode siap pakai)               |
| Berdiri sendiri?  | Ya, langsung jalan di browser                  | Tidak, harus memuat file jQuery lebih dulu       |
| Penulisan kode    | Lebih panjang                                  | Lebih singkat, memakai `$()`                     |
| Cakupan           | Luas: logika program, DOM, server, dan lainnya | Terbatas: DOM, event, efek, dan AJAX             |
| Efek dan animasi  | Dibuat sendiri                                 | Sudah tersedia (`hide()`, `show()`, dan lainnya) |
| Perbedaan browser | Perlu disesuaikan sendiri                      | Sudah ditangani jQuery                           |
| File tambahan     | Tidak perlu                                    | Perlu (CDN atau file lokal)                      |
| Cara belajar      | Dipelajari lebih dulu sebagai dasar            | Lebih mudah, tetapi tetap butuh dasar JavaScript |

**Perbandingan kode** untuk tugas yang sama (mengubah warna kotak, lalu menyembunyikannya):

```javascript
// JavaScript
document.getElementById("kotakWarna").style.backgroundColor = "#7c3aed";
document.getElementById("kotakWarna").style.display = "none";

// jQuery
$("#kotakWarna").css("background-color", "#7c3aed");
$("#kotakWarna").hide();
```

---

## Penjelasan Program

### Soal 4 – `soal1.html`

Program meminta nama dan NIM lewat kotak prompt saat halaman dibuka, lalu menampilkannya di form.

1. Halaman dibuka, lalu `onload="tampilkanData()"` menjalankan fungsi `tampilkanData()`.
2. `prompt("Masukkan nama kamu:")` meminta nama, kemudian `prompt("Masukkan nim kamu:")` meminta NIM.
3. Jika pengguna menekan **Cancel**, hasilnya `null`. Nilai ini diganti teks kosong agar tulisan "null" tidak muncul di form.
4. Nilai dimasukkan ke kolom Nama dan NIM lewat `.value`. Kolom bersifat `readonly`, jadi hanya menampilkan data.

### Soal 5 – `soal2.html`

Program mengubah warna dan menyembunyikan kotak memakai jQuery. jQuery dimuat dari CDN `https://code.jquery.com/jquery-3.7.1.min.js`, dan semua kode berada di dalam `$(document).ready()` supaya baru berjalan setelah halaman selesai dimuat.

| Tombol            | Kode jQuery                                           | Hasil                |
| :---------------- | :---------------------------------------------------- | :------------------- |
| Ungu              | `$("#kotakWarna").css("background-color", "#7c3aed")` | Kotak berwarna ungu  |
| Biru              | `$("#kotakWarna").css("background-color", "#2563eb")` | Kotak berwarna biru  |
| Hijau             | `$("#kotakWarna").css("background-color", "#15803d")` | Kotak berwarna hijau |
| Sembunyikan Kotak | `$("#kotakWarna").hide()`                             | Kotak disembunyikan  |
| Tampilkan Kotak   | `$("#kotakWarna").show()`                             | Kotak muncul kembali |

Saat ditampilkan lagi, kotak tetap memakai warna terakhir yang dipilih.

---

## Cara Menjalankan

1. Unduh atau clone repository ini.
2. Buka `soal1.html` dan `soal2.html` di browser, atau gunakan **Live Server** di VS Code.
3. `soal2.html` membutuhkan koneksi internet karena jQuery dimuat dari CDN.
