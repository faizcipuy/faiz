# === Data Produk & Stok ===
produk = {
    "Indomie": {"harga": 3500, "stok": 10},
    "Telur": {"harga": 2500, "stok": 20},
    "Beras": {"harga": 12000, "stok": 15},
    "Minyak Goreng": {"harga": 15000, "stok": 8},
    "Gula": {"harga": 10000, "stok": 12}
}

def tampilkan_daftar_produk():
    """Menampilkan daftar produk, harga, dan stok"""
    print("\n===== SELAMAT DATANG DI TOKO =====")
    print("Daftar Produk:")
    for nama, info in produk.items():
        print(f"- {nama}: Rp{info['harga']} | Stok: {info['stok']}")

def input_pembelian():
    """
    Input barang dan jumlah yang dibeli user.
    Mengembalikan keranjang belanja (dictionary).
    """
    keranjang = {}
    while True:
        barang = input("\nMasukkan nama barang (ketik 'selesai' untuk mengakhiri): ").title()
        if barang.lower() == "selesai":
            break
        if barang in produk:
            if produk[barang]["stok"] <= 0:
                print("Stok habis.")
                continue
            try:
                jumlah = int(input(f"Masukkan jumlah {barang}: "))
                if jumlah <= 0:
                    print("Jumlah harus lebih dari 0.")
                elif jumlah > produk[barang]["stok"]:
                    print(f"Stok tidak mencukupi. Stok tersedia: {produk[barang]['stok']}")
                else:
                    keranjang[barang] = keranjang.get(barang, 0) + jumlah
                    produk[barang]["stok"] -= jumlah
            except ValueError:
                print("Masukkan angka yang valid.")
        else:
            print("Barang tidak tersedia.")
    return keranjang

def cetak_struk(keranjang):
    """
    Mencetak struk belanja dan menghitung total.
    Mengembalikan total belanja.
    """
    print("\n===== STRUK PEMBELIAN =====")
    total = 0
    for barang, jumlah in keranjang.items():
        harga = produk[barang]["harga"]
        subtotal = harga * jumlah
        print(f"{barang} x {jumlah} = Rp{subtotal}")
        total += subtotal
    print(f"\nTotal Belanja: Rp{total}")
    return total

def proses_pembayaran(total):
    """
    Memproses pembayaran dari user.
    Menangani jika uang kurang.
    """
    while True:
        try:
            bayar = int(input("Masukkan jumlah uang: Rp"))
            if bayar < total:
                print("Uang tidak cukup. Masukkan lagi.")
            else:
                kembalian = bayar - total
                print(f"Kembalian: Rp{kembalian}")
                print("=== Terima kasih telah berbelanja! ===")
                break
        except ValueError:
            print("Masukkan angka yang valid.")

def cek_stok_inventori():
    """
    Menampilkan dan mengatur stok inventori.
    """
    while True:
        print("\n=== Menu Inventori ===")
        print("1. Lihat stok")
        print("2. Tambah stok")
        print("3. Kurangi stok")
        print("4. Kembali ke menu utama")
        pilihan = input("Pilih menu (1/2/3/4): ")

        if pilihan == "1":
            print("\nStok saat ini:")
            for nama, info in produk.items():
                print(f"- {nama}: {info['stok']}")
        elif pilihan == "2":
            barang = input("Nama barang yang akan ditambah stok: ").title()
            if barang in produk:
                try:
                    tambah = int(input("Jumlah yang akan ditambah: "))
                    if tambah > 0:
                        produk[barang]["stok"] += tambah
                        print(f"Stok {barang} sekarang: {produk[barang]['stok']}")
                    else:
                        print("Jumlah harus lebih dari 0.")
                except ValueError:
                    print("Masukkan angka yang valid.")
            else:
                print("Barang tidak ditemukan.")
        elif pilihan == "3":
            barang = input("Nama barang yang akan dikurangi stok: ").title()
            if barang in produk:
                try:
                    kurang = int(input("Jumlah yang akan dikurangi: "))
                    if 0 < kurang <= produk[barang]["stok"]:
                        produk[barang]["stok"] -= kurang
                        print(f"Stok {barang} sekarang: {produk[barang]['stok']}")
                    else:
                        print("Jumlah tidak valid atau melebihi stok.")
                except ValueError:
                    print("Masukkan angka yang valid.")
            else:
                print("Barang tidak ditemukan.")
        elif pilihan == "4":
            break
        else:
            print("Pilihan tidak valid.")

# === Program Utama ===
def main():
    while True:
        print("\n=== MENU UTAMA ===")
        print("1. Transaksi Belanja")
        print("2. Cek & Atur Stok Inventori")
        print("3. Keluar")
        menu = input("Pilih menu (1/2/3): ")

        if menu == "1":
            tampilkan_daftar_produk()
            keranjang = input_pembelian()
            if keranjang:
                total = cetak_struk(keranjang)
                proses_pembayaran(total)
            else:
                print("Tidak ada barang yang dibeli.")
        elif menu == "2":
            cek_stok_inventori()
        elif menu == "3":
            print("Keluar dari program. Terima kasih!")
            break
        else:
            print("Pilihan tidak valid.")

if _name_ == "_main_":
    main()
