FIXZY — QR NOTA & CEK STATUS SERVIS

File dalam paket:
- servisan.html: halaman input servis asli dengan QR dan satu penulisan ringkasan aman ke cek_servis_public.
- scan-barcode.html: pemindai QR dan input nomor nota manual.
- cek-servis.html: halaman publik yang membaca satu dokumen cek_servis_public berdasarkan ID nota.

Pemasangan:
1. Cadangkan file lama. Ganti servisan.html dengan file dari paket ini.
2. Letakkan scan-barcode.html dan cek-servis.html pada folder hosting yang sama dengan servisan.html.
3. Pastikan halaman diakses melalui HTTPS agar kamera berfungsi.
4. Firebase Rules tidak diubah oleh paket ini. Rules aktif harus mengizinkan authenticated create/update pada cek_servis_public sesuai isAuth, hasIzin('servis'), isMyData(request.resource.data), field wajib, dan nomorNota == notaId.
5. QR baru dapat menampilkan status jika penulisan cek_servis_public berhasil. Jika ditolak, data servis utama tetap tersimpan dan halaman memberi peringatan terpisah. Jangan tekan simpan ulang hanya karena peringatan publik; periksa log permission-denied.

Keamanan:
Dokumen publik hanya berisi nomor nota, tanggal, nama konter, tipe perangkat, keluhan, teknisi, status, estimasi, DP, sisa, dan field kepemilikan untuk Rules. Nomor WA, alamat, IMEI, sandi, dan pola tidak disalin. Halaman cek publik tidak membaca koleksi servis.

Catatan:
Pengujian koneksi langsung ke Firebase harus dilakukan di akun proyek A Yudi. Saya tidak mengubah Firebase Rules dan tidak bisa menjamin Rules aktif mengizinkan penulisan tanpa uji langsung.
