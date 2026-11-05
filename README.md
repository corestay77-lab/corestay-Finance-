# CoreStay Finance

**Versi 1.2.0** (build 2026-11-03)

Aplikasi web statis (HTML, CSS, JavaScript tanpa build): Dashboard, Invoice dan piutang, Utang dan pembayaran, Kas dan bank, Laporan, Pengaturan.

## Isi
- `index.html`: aplikasi Finance
- `config.js`: isi `executiveUrl` dengan alamat aplikasi Executive bila ingin muncul tautan di menu (boleh dikosongkan)
- `assets/logo.png`: logo CoreStay Advisory

## Menayangkan di GitHub Pages
1. Buat repositori baru, misalnya `corestay-finance`.
2. Unggah semua isi folder ini (termasuk folder `assets`) ke cabang `main`.
3. Settings, Pages, Deploy from a branch, cabang `main`, folder root, Save.
4. Alamat: `https://NAMA-ANDA.github.io/corestay-finance/`.

## Catatan
- Data tersimpan di browser (localStorage) per perangkat. Belum ada login atau database bersama.
- Aplikasi Executive hanya bisa membaca data Finance bila kedua aplikasi berada di akun GitHub yang sama (alamat `NAMA-ANDA.github.io`).
- Isi awal adalah data contoh. Jangan memasukkan data keuangan atau pribadi yang nyata di versi ini.

## Mengubah dan menghapus data
- Invoice, tagihan, dan transaksi kas punya tombol **Ubah** dan **Hapus** di setiap baris.
- Mengubah invoice atau tagihan yang sudah lunas ikut memperbarui transaksi kas terkait (jumlah, hotel, keterangan).
- Menghapus invoice atau tagihan lunas ikut menghapus transaksi kasnya. Menghapus transaksi pelunasan mengembalikan status invoice menjadi Terkirim (tagihan menjadi Disetujui).
- Menu **Pengaturan**: tambah, ubah, hapus rekening bank (rekening yang masih punya transaksi tidak bisa dihapus), unduh dan pulihkan cadangan data (.json), kosongkan data, kembalikan data contoh.

## Akuntansi perhotelan (mulai 1.2.0)
- **Klasifikasi akun** mengacu pada struktur USALI: pendapatan (Kamar, F&B, departemen operasional lain), beban departemen, beban tak terdistribusi (A&G, Penjualan dan pemasaran, TI, Pemeliharaan properti, Energi), biaya manajemen, non-operasional dan beban tetap. Setoran pajak, belanja modal, dan transfer antar rekening berada di luar laba rugi. Gaji dicatat pada departemen tempat biaya timbul.
- **Laporan** menampilkan laba departemen, GOP, margin GOP, dan laba bersih per hotel, dengan pilihan basis akrual atau kas.
- **Pajak dan service charge** pada invoice: PBJT jasa perhotelan, PPN, atau tanpa pajak. Pajak dihitung atas jumlah termasuk service charge dan tidak dihitung sebagai pendapatan. Tarif dapat diubah karena PBJT mengikuti peraturan daerah (paling tinggi 10%).
- **Kontrol:** invoice dan tagihan punya tanggal dokumen. Draf bisa dihapus; dokumen yang sudah berjalan dibatalkan dengan alasan; dokumen lunas harus membatalkan pembayarannya lebih dulu. Menu Pengaturan memuat penutupan buku per tanggal dan jejak perubahan.
- **Data lama tidak dimigrasi.** Aplikasi masih tahap pengembangan: data dari versi sebelum 1.2.0 (di browser maupun berkas cadangan) diabaikan dan aplikasi memakai data contoh.

### Batasan
Aplikasi ini pembukuan satu sisi untuk pelaporan manajemen, bukan buku besar berpasangan (debit-kredit). Belum ada jurnal, penyusutan, PPh 21/23/4(2), PPN masukan, anggaran, serta statistik kamar (okupansi, ADR, RevPAR). Laporan pajak resmi tetap disusun dari sistem pajak dan akuntan Anda.

## Versi
Nomor versi ada di `index.html` pada konstanta `VER` dan `BUILD` (awal blok `<script>`). Naikkan keduanya setiap rilis, lalu tambahkan baris di daftar riwayat pada fungsi `pengaturan()` dan di bawah ini. Versi tampil di footer dan di menu Pengaturan.

### Riwayat
- 1.2.0 (2026-11-03): Klasifikasi akun USALI, laporan GOP basis akrual dan kas, PBJT/PPN dan service charge, pajak bukan pendapatan, tanggal dokumen, pembatalan dengan alasan, penutupan buku, jejak perubahan.
- 1.1.0 (2026-11-03): Ubah dan hapus data, menu Pengaturan (rekening, cadangan), footer dan versi.
- 1.0.0: Rilis awal.
