# Petualangan TKA Matematika – SD Negeri 3 Muara Rupit

Aplikasi kuis interaktif TKA Matematika untuk siswa kelas VI A dan VI B SD Negeri 3 Muara Rupit. Aplikasi dibuat menggunakan HTML, CSS, dan JavaScript, serta dapat dipublikasikan melalui GitHub Pages.

## Fitur

- 50 soal Matematika untuk latihan kelas VI.
- Bentuk soal:
  - Pilihan ganda
  - Benar/Salah
  - Pilihan kompleks (lebih dari satu jawaban)
  - Soal dengan ilustrasi/visual sederhana
- Materi meliputi pecahan, desimal dan persen, perkalian dan pembagian, soal cerita dan logika, bangun datar, bangun ruang, data dan penalaran.
- Siswa mengisi nama, kelas, dan tanggal pengerjaan sebelum memulai.
- Penyesuaian level kesulitan berdasarkan ketepatan jawaban selama pengerjaan.
- Pembacaan soal dengan fitur suara browser dan efek bunyi yang dapat diaktifkan atau dinonaktifkan.
- Sertifikat hasil yang dapat dicetak atau disimpan sebagai PDF melalui fitur cetak browser.
- Dasbor guru untuk melihat rekap hasil siswa.
- Ekspor rekap ke Excel, Word, dan PDF.
- Integrasi Firebase Authentication dan Cloud Firestore untuk penyimpanan hasil secara daring.

## Berkas

- `index.html` — berkas utama aplikasi. Unggah berkas ini ke repositori GitHub.
- `README.md` — petunjuk penggunaan dan pemasangan aplikasi.

## Cara menjalankan di komputer

1. Unduh berkas aplikasi HTML.
2. Jika nama berkas belum `index.html`, ubah namanya menjadi `index.html`.
3. Buka berkas `index.html` menggunakan browser seperti Google Chrome atau Microsoft Edge.
4. Untuk menggunakan penyimpanan Firebase dan dasbor guru, lakukan konfigurasi Firebase terlebih dahulu sebagaimana dijelaskan di bawah.

> Catatan: beberapa fitur memerlukan koneksi internet karena Firebase dan pustaka ekspor dokumen dimuat dari layanan daring.

## Konfigurasi Firebase

Aplikasi ini menggunakan Firebase JavaScript SDK versi compat `10.12.2`, Firebase Authentication, dan Cloud Firestore.

### 1. Siapkan Firebase Project

1. Buka [Firebase Console](https://console.firebase.google.com/).
2. Pilih proyek Firebase sekolah yang akan digunakan.
3. Buka **Project settings** (ikon roda gigi) → **General**.
4. Pada bagian **Your apps**, pilih aplikasi Web. Jika belum ada, tambahkan aplikasi Web.
5. Salin konfigurasi Firebase Web App.

### 2. Masukkan konfigurasi ke `index.html`

Cari bagian berikut di dalam `index.html`:

```javascript
const firebaseConfig = {
  apiKey: "ISI_API_KEY",
  authDomain: "ISI_PROJECT_ID.firebaseapp.com",
  projectId: "ISI_PROJECT_ID",
  storageBucket: "ISI_PROJECT_ID.appspot.com",
  messagingSenderId: "ISI_MESSAGING_SENDER_ID",
  appId: "ISI_APP_ID"
};
```

Ganti setiap nilai contoh dengan nilai asli dari konfigurasi Firebase Web App. Jangan mengubah nama properti seperti `apiKey`, `authDomain`, `projectId`, `storageBucket`, `messagingSenderId`, dan `appId`.

### 3. Aktifkan metode login

Di Firebase Console:

1. Buka **Build → Authentication → Get started**.
2. Pada **Sign-in method**, aktifkan **Anonymous** untuk sesi siswa.
3. Aktifkan **Email/Password** untuk akun guru.
4. Tambahkan akun guru melalui bagian **Users** jika belum tersedia.

Aplikasi memakai login anonim untuk siswa dan login email/kata sandi untuk guru. Jangan membagikan kata sandi akun guru kepada siswa.

### 4. Atur email guru

Cari baris berikut di `index.html`:

```javascript
const TEACHER_EMAIL = "ISI_EMAIL_GURU";
```

Ganti `ISI_EMAIL_GURU` dengan alamat email guru yang didaftarkan di Firebase Authentication. Penulisan email harus sama dengan akun guru yang digunakan untuk masuk ke dasbor.

### 5. Buat Cloud Firestore

1. Buka **Build → Firestore Database**.
2. Buat database jika belum tersedia.
3. Pilih lokasi database sesuai kebutuhan sekolah.
4. Pastikan aturan keamanan Firestore membatasi pembacaan data hanya untuk akun guru yang berwenang.

Aplikasi menyimpan hasil pada koleksi:

```text
Hasil_TKA_Matematika
```

Setiap dokumen hasil memuat data siswa, kelas, tanggal pengerjaan, jumlah jawaban benar, nilai, level akhir, waktu penyimpanan, dan ringkasan jawaban.

**Penting:** jangan menggunakan aturan Firestore yang mengizinkan semua orang membaca, mengubah, atau menghapus seluruh data. Aturan harus disesuaikan dengan autentikasi siswa anonim dan akun guru. Uji aturan menggunakan akun siswa dan akun guru sebelum aplikasi dipakai secara resmi. Jangan pernah memasukkan private key atau service-account key ke dalam file HTML.

## Publikasi melalui GitHub Pages

1. Masuk ke GitHub dan buka repositori yang akan digunakan.
2. Unggah `index.html` ke folder utama repositori (root).
3. Pastikan nama file tepat `index.html`.
4. Buka **Settings → Pages**.
5. Pada bagian **Build and deployment**, pilih **Deploy from a branch**.
6. Pilih branch `main` dan folder `/ (root)`, lalu klik **Save**.
7. Tunggu proses publikasi selesai. Buka alamat GitHub Pages yang ditampilkan pada halaman Pages.

Jika melakukan perubahan pada aplikasi, unggah kembali `index.html` yang sudah diperbarui ke repositori. Muat ulang halaman aplikasi setelah proses publikasi selesai. Jika perubahan belum terlihat, coba muat ulang paksa browser.

## Cara menggunakan sebagai siswa

1. Buka alamat aplikasi.
2. Isi nama lengkap.
3. Pilih kelas VI A atau VI B.
4. Isi tanggal pengerjaan.
5. Tekan **Mulai Petualangan**.
6. Pilih jawaban. Pada soal pilihan kompleks, pilih semua jawaban yang dianggap benar.
7. Tekan **Periksa Jawaban** untuk melihat umpan balik.
8. Tekan **Soal Berikutnya** sampai seluruh 50 soal selesai.
9. Lihat nilai dan sertifikat. Gunakan **Cetak / Simpan PDF** untuk mencetak atau menyimpan sertifikat.

Siswa harus mengisi nama, kelas, dan tanggal sebelum memulai. Hasil akan dikirim ke Firestore apabila konfigurasi Firebase sudah benar dan perangkat terhubung ke internet.

## Cara menggunakan dasbor guru

1. Tekan **Dasbor Guru**.
2. Masukkan email dan kata sandi akun guru yang sudah didaftarkan di Firebase Authentication.
3. Setelah berhasil masuk, lihat rekap percobaan siswa.
4. Tekan **Perbarui** untuk mengambil data terbaru.
5. Gunakan tombol **Unduh Excel**, **Unduh Word**, atau **Unduh PDF** untuk mengekspor rekap.

Jika dasbor tidak dapat menampilkan data, periksa konfigurasi Firebase, status login, email guru, koneksi internet, dan aturan keamanan Firestore.

## Penilaian dan level

- Terdapat 50 soal.
- Setiap jawaban benar menambah 2 poin pada skor berjalan.
- Nilai akhir dihitung dari jumlah jawaban benar dibandingkan 50 soal, lalu dikalikan 100.
- Level disesuaikan berdasarkan akurasi jawaban yang telah diperiksa:
  - Akurasi 80% atau lebih: Level 3.
  - Akurasi 55% sampai kurang dari 80%: Level 2.
  - Akurasi kurang dari 55%: Level 1.

Level ditampilkan sebagai penyesuaian tingkat tantangan selama sesi. Urutan soal pada versi ini mengikuti susunan bank soal di dalam kode.

## Teknologi yang digunakan

- HTML5
- CSS3
- JavaScript
- Firebase App, Authentication, dan Cloud Firestore (compat SDK 10.12.2)
- SheetJS (`xlsx`) untuk ekspor Excel
- jsPDF untuk ekspor PDF
- docx untuk ekspor Word
- Web Speech API untuk pembacaan soal
- Web Audio API untuk efek bunyi

## Pemecahan masalah

| Masalah | Hal yang perlu diperiksa |
|---|---|
| Hasil tidak tersimpan | Pastikan konfigurasi Firebase sudah diganti, Anonymous Authentication aktif, Firestore tersedia, dan internet tersambung. |
| Dasbor guru gagal masuk | Pastikan akun Email/Password sudah dibuat, email pada kode sama dengan email akun, dan kata sandi benar. |
| Dasbor tidak menampilkan data | Periksa aturan Firestore dan pastikan guru memiliki izin membaca koleksi `Hasil_TKA_Matematika`. |
| Tombol ekspor tidak bekerja | Pastikan internet tersambung karena pustaka ekspor dimuat dari CDN. |
| Suara tidak terdengar | Pastikan tombol suara dalam keadaan ON, volume perangkat aktif, dan browser mendukung Web Speech API. |
| Perubahan GitHub belum terlihat | Pastikan file diunggah ke branch dan folder yang dipakai GitHub Pages, lalu muat ulang halaman. |

## Catatan keamanan dan penggunaan

- Konfigurasi Firebase Web App yang berada di HTML merupakan konfigurasi klien, bukan tempat menyimpan kata sandi atau private key.
- Keamanan data ditentukan terutama oleh aturan Firestore. Tinjau dan uji aturan sebelum aplikasi digunakan untuk data siswa.
- Dasbor guru memerlukan akun guru yang terdaftar. Jangan membagikan kredensialnya.
- Nilai pada aplikasi merupakan hasil latihan/asesmen melalui aplikasi. Untuk penilaian resmi, guru tetap perlu melakukan verifikasi sesuai kebutuhan pembelajaran.
- Pastikan penggunaan data siswa mengikuti kebijakan perlindungan data dan ketentuan sekolah.

## Identitas aplikasi

**Nama aplikasi:** Petualangan TKA Matematika  
**Satuan pendidikan:** SD Negeri 3 Muara Rupit  
**Kelas:** VI A dan VI B  
**Guru:** Rasmila Br Ginting, S.Pd  
**Kepala sekolah:** Candra Melati Putra, S.Pd, M.Pd
