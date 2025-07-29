🧾 Judul: Aplikasi Kasir Sederhana Berbasis CLI (Command Line Interface)
👤 Identitas Mahasiswa
Nama: Muhammad Alfarizi
NIM: 24110310058
Prodi: Bisnis Digital
Mata Kuliah: Algoritma Pemrograman
Dosen: H. Caesar Rismanto, S.T., M.M, & Ahmad Roihan, S.Kom., MTI
Link GitHub: faizcipuy/faiz - GitHub 
💡 Deskripsi Singkat
Aplikasi ini dibuat untuk membantu toko kecil dalam melakukan pencatatan belanja pelanggan, pengelolaan stok barang, pencetakan struk, serta perhitungan pembayaran dan kembalian. Berjalan di terminal/CLI tanpa memerlukan database atau tampilan GUI, sehingga ringan dan mudah dipahami.

🧱 Struktur Utama Program
1. Data Produk & Stok

Disimpan dalam struktur data seperti dictionary.
Masing-masing produk memiliki:
Nama Barang
Harga
Jumlah Stok

2. Menu Utama

Menu yang ditampilkan ke pengguna terdiri dari tiga pilihan:
1. Transaksi Belanja
2. Cek & Atur Stok Inventori
3. Keluar
Tujuan: Memudahkan navigasi, memberikan fleksibilitas kepada pengguna, dan membuat program terlihat profesional dan terstruktur.
3. Transaksi Belanja

Menampilkan produk, harga, dan stok saat ini.

Pengguna memasukkan barang dan jumlah yang ingin dibeli.

Program memvalidasi apakah stok mencukupi.

Jika valid, stok akan otomatis berkurang.

Mencetak struk belanja.

Menghitung total belanja dan kembalian setelah input pembayaran.

4. Cek & Atur Stok Inventori

Admin bisa:

Melihat semua stok barang.

Menambahkan stok baru (restock).

Mengurangi stok (barang rusak atau hilang).

Fungsi ini membantu menjaga data stok tetap akurat.

5. Fungsi Penting dalam Kode

Fungsi	Deskripsi

tampilkan_daftar_produk()	Menampilkan semua barang dengan harga dan stok
input_pembelian()	Memasukkan barang yang dibeli dan validasi stok
cetak_struk()	Mencetak detail belanja
proses_pembayaran()	Memproses pembayaran dan menghitung kembalian
cek_stok_inventori()	Menampilkan dan mengatur stok
main()	Fungsi utama untuk menavigasi menu

🧮 Contoh Potongan Kode (Menu Utama)

def main():
    while True:
        print("\n=== MENU UTAMA ===")
        print("1. Transaksi Belanja")
        print("2. Cek & Atur Stok Inventori")
        print("3. Keluar")
        menu = input("Pilih menu (1/2/3): ")

Alasan:
Struktur menu dibuat agar user bisa memilih fungsi dengan mudah dan tidak langsung dipaksa belanja.

🛒 Contoh Potongan Kode (Input Pembelian)

def input_pembelian():
    keranjang = {}
    while True:
        barang = input("Masukkan nama barang (ketik 'selesai' jika selesai): ").title()
        if barang.lower() == "selesai":
            break
        if barang in produk:
            if produk[barang]["stok"] <= 0:
                print("Stok habis.")
                continue
            # lanjut ke input jumlah

Penjelasan:

title() menjaga konsistensi input (misalnya "indomie" atau "INDOMIE").

Validasi stok mencegah pembelian melebihi stok.


✅ Kelebihan Aplikasi

Mudah digunakan dan dipahami.
Stok langsung otomatis berkurang setelah transaksi.
Admin bisa mengatur stok kapan saja.
Potensial dikembangkan ke sistem yang lebih kompleks (misal: file JSON, GUI, atau database).

❌ Kekurangan Aplikasi

1. Validasi input masih sederhana.
Belum ada koreksi kesalahan pengetikan nama barang.

2. Tampilan hanya berupa teks (CLI).
Kurang ramah bagi pengguna awam yang terbiasa dengan tampilan grafis.
