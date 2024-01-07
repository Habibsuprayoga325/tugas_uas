program ini menjelaskan sebuah program yang digunakan oleh kasir di sebuah kantin untuk memesan makanan atau minuman,menghitung total pembelian,dan menampilkan struk pembelian. Berikut adalah penjelasan rinci dari setiap bagian program:

1. Menu dan Harga:
```python
menu = {
    "Soto ayam": 20000,
    "Nasi Goreng": 15000,
    "Mie Goreng": 12000,
    "Ayam Goreng": 18000,
    "Es Teh": 5000,
    "Es Jeruk": 6000
}
```
-Dictionary `menu` berisi opsi makanan dan harga masing-masing.

2. fungsi `tampilkan_menu`:
   ```python
   def tampilkan_menu():
     print("menu makanan/minuman:")
     for item, harga in menu.items():
         print(f"{item}: Rp {harga}")
   ```
   -fungsi ini menampilkan menu makanan/minuman beserta harganya.


   3. fungsi `hitung_total`:
      ```python
      def hitung_total(harga, jumlah):
          return harga * jumlah
      ```
      -fungsi ini menghitung total harga satuan dan jumlah yang dipesan.

   4. fungsi `main`:
      ```python
      def main():
        pesanan = {}

       while true:
        tampilkan_menu()
      pilihan = input("masukan nama makanan/minuman yang ingin dipesan (ketik 'sudah' untuk menampilkan struk):")

      if pilihan.lower() == 'sudah':
        break

      if pilihan in menu:
        jumlah = int(input(f"masukan jumlah {pilihan}: "))
        harga_total = hitung_total(menu[pilihan], jumlah)
        pesanan[pilihan] = {'jumlah': jumlah, 'harga_total': harga_total}
      else:
          print("menu tidak ada. silahkan pilih menu yang tersedia.")

      total_pembelian = 0
      for item, detail in pesanan.items():
          tabel_struk.add_row([item, f"x{detail['jumlah']}", f"Rp {detail['harga_total']}"])
          total_pembelian += detail['harga_total']

  print("\nStruk pembelian:")
  print(tabel_struk)
  print(f"\nTotal pembelian: Rp {total_pembelian}")

if __name__ == "__main__":
    main()
```
-Fungsi `main` merupakan inti dari program.
-Selama pengguna belum memilih 'sudah', program akan menampilkan menu dan meminta pengguna untuk memasukkan pesanan.
- Jika pesanan valid, program akan menyimpan pesanan beserta jumlah dan total harga dalam dictionary `pesanan`.
- Setelah pengguna selesai memesan, program akan menampilkan struk pembelian, mencetak menu, jumlah, dan harga total setiap pesanan, serta total pembelian keseluruhan.

5. Eksekusi Program:
```python
if __name__ == "__main__":
    main()
```
- Ini adalah blok yang akan dijalankan jika skrip dijalankan langsung (bukan diimpor sebagai modul).
-  Memanggil fungsi `main` untuk memulai eksekusi program.
