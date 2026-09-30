UNDANGAN PERNIKAHAN DIGITAL - EVAN & NADIA
============================================

CARA PAKAI
----------
1. Buka file index.html langsung di browser untuk melihat preview.
2. Upload index.html ke hosting gratis (Netlify, Vercel, GitHub Pages,
   atau hosting biasa) agar bisa dibagikan sebagai link ke tamu.
3. Untuk personalisasi nama tamu di cover, tambahkan parameter di URL:
   index.html?to=Budi%20Santoso

CARA GANTI DATA (semua di dalam index.html)
--------------------------------------------
1. Buka index.html dengan text editor (VS Code, Notepad++, dll).

2. Cari blok CONFIG di bagian <script> (dekat akhir file):
     var CONFIG = {
       weddingDateTimeISO: "2027-03-06T08:00:00+07:00",
       ...
     };
   -> Ganti tanggal & jam pernikahan di sini (dipakai untuk countdown
      dan tanggal akad/resepsi otomatis).

3. Nama mempelai, orang tua, tanggal, dan alamat ada di bagian HTML,
   cari teks berikut lalu ganti sesuai kebutuhan:
     - "Laurent" dan "Sofia"                -> nama mempelai
     - "Hendra Wijaya" / "Ratna Kusuma"  -> nama orang tua mempelai pria
     - "Ahmad Syarif" / "Dewi Anggraini" -> nama orang tua mempelai wanita
     - "Masjid Al-Ikhlas..."             -> lokasi akad
     - "Grand Ballroom Hotel Aryaduta..."-> lokasi resepsi
     - "https://maps.google.com/?q=..."  -> ganti dengan link Google Maps asli
     - "8760123456" / "1370099887"       -> nomor rekening
     - id="qrisSvg"                      -> ganti dengan gambar QRIS asli
       (hapus kode SVG placeholder, ganti dengan <img src="qris.png">)

4. Galeri foto: cari array "galleryData" di <script>, dan ganti bagian
   ikon SVG placeholder dengan tag <img> ke foto asli Anda jika mau
   menampilkan foto sungguhan.

CATATAN PENTING
---------------
- Ucapan & RSVP saat ini tersimpan di localStorage browser TAMU
  masing-masing (bukan terkumpul di satu tempat). Ini keterbatasan
  halaman statis tanpa server/database.
- Untuk mengumpulkan semua ucapan/RSVP ke satu tempat (misalnya
  Google Sheet), forms ini perlu disambungkan ke backend/Google Apps
  Script. Beri tahu Claude jika ingin dibantu membuat versi ini.
- Musik latar dibuat otomatis oleh browser (generative), tidak
  memerlukan file musik eksternal. Jika ingin memakai file musik
  sendiri, ada instruksi di dalam komentar kode <script> pada bagian
  paling bawah (cari kata "Alternatif: gunakan file musik asli Anda").

TEKNOLOGI
---------
- Single-file HTML + CSS + Vanilla JavaScript (tanpa framework/build
  tool), agar mudah dibuka dan di-hosting di mana saja.
