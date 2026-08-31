BARRA INVOICE MOBILE V7 - VERSI PWA (bisa di-install ke HP Android)

Tambahan di versi ini:
- manifest.json + icons/ -> supaya bisa "Add to Home Screen" dan
  membuka seperti aplikasi asli (tanpa address bar browser).
- service-worker.js -> meng-cache semua file app supaya bisa dibuka
  100% offline setelah pertama kali diinstall.
- Tombol Export Backup (.json) & Import Backup (.json) di halaman
  Riwayat -> jaga-jaga kalau HP di-reset / app-nya kehapus, data
  bisa dipulihkan dari file backup.

CARA PASANG (lihat instruksi lengkap dari asisten yang membuatkan ini):
1. Upload seluruh folder ini ke hosting statis gratis (GitHub Pages/
   Netlify/Vercel) -- WAJIB, karena fitur offline (service worker)
   hanya aktif di alamat https:// atau localhost, TIDAK aktif kalau
   index.html dibuka langsung dari file manager HP.
2. Buka link hasil hosting itu di Chrome Android.
3. Menu titik tiga -> "Add to Home screen" / "Install app".
4. Selesai, ikon "Barra Invoice" muncul di HP seperti app biasa.

BARRA INVOICE MOBILE V6

Perubahan utama:
- Beranda tanpa "Invoice Terbaru"
- Dashboard mobile-first dengan tile square yang lebih profesional
- Tipografi, spacing, icon SVG, tombol, dan kartu dirapikan
- Tombol Kembali ke Beranda di Buat Invoice dan Riwayat
- Riwayat dibuat ringkas dan rapi di HP
- Logo Barra Apparel terbaru dari pengguna otomatis tertanam DI INVOICE
- Logo tidak ditampilkan pada header web
- Logo menggunakan data embedded agar ikut saat export PDF/JPEG/PNG offline
- Status invoice: merah BELUM BAYAR, kuning DP, hijau LUNAS
- Data tetap offline via localStorage

—— CATATAN RAPIIN KODE ——
- CSS yang tadinya 3 lapis revisi (V4/V5/V6) saling menimpa sekarang
  digabung jadi satu set aturan bersih (22.4KB -> 14.8KB), tampilan
  tidak berubah.
- Logo yang sebelumnya di-embed base64 dua kali (dobel ±340KB) kini
  cuma disimpan sekali lalu dipakai ulang -> ukuran file total turun
  dari ±712KB jadi ±372KB.
- Class CSS yang tidak pernah dipakai di HTML (dashboard/leftcol/
  rightcol/pagination/textbtn/dll) dihapus.
- BUG DIPERBAIKI: preview invoice di halaman "Buat Invoice" sekarang
  otomatis menyesuaikan skala ke lebar kontainer, jadi kolom Total/
  Sisa Pembayaran/Status tidak lagi terpotong di layar sempit
  (mobile) maupun desktop. Saat export PDF/JPEG/PNG, ukuran invoice
  tetap 794x1123px penuh seperti sebelumnya (tidak ikut mengecil).
