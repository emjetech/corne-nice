ZMK Corne untuk Super Mini / Promicro Wireless NRF52840.

[ZMK STUDIO](https://zmk.studio/)
Ada update baru ZMK Studio remapping tanpa perlu di flash 

[Full Dokumentasi ZMK](https://zmk.dev/docs)


Tools :
[ZMK Keymap Editor](https://nickcoutsos.github.io/keymap-editor/)
Video fork repository :
[Tutorial Mapping ZMK](https://youtu.be/cAi5pnkz48M)


Prosedur Reset Keyboard Split
Lakukan langkah-langkah berikut untuk mereset semua bagian keyboard split Anda:
- Masukkan setiap bagian keyboard split ke mode bootloader. Dengan cara tekan 2x tombol reset saat USB terhubung akan muncul drive baru, untuk flash nya cukup drag & drop di disk bootloader
- Flash salah satu bagian keyboard dengan firmware reset pengaturan setting_reset.uf2.
- Ulangi langkah 2 pada bagian lainnya dari keyboard split.
- Flash image firmware yang sebenarnya untuk setiap bagian keyboard split (misalnya my_board_left.uf2 untuk bagian kiri, my_board_right.uf2 untuk bagian kanan).
- Jika central dan peripheral tidak saling terhubung setelah menyelesaikan langkah-langkah ini, akan membantu untuk mereset central dan peripheral pada waktu yang hampir bersamaan. Biasanya dilakukan dengan menghubungkan pin reset ke ground pada setiap mikrokontroler keyboard Anda, menekan tombol reset, atau mematikan lalu menyalakan keduanya dengan sakelar daya.
- Setelah selesai, Anda harus menghapus/lupakan keyboard dari perangkat host mana pun yang sebelumnya terpasang, lalu lakukan pairing ulang, karena informasi pairing tersebut juga telah dihapus dari keyboard.
  

🔵 Penjelasan Bluetooth ZMK (Versi Sederhana)
Keyboard ZMK menggunakan sistem Bluetooth yang aktif secara otomatis. Pada layar keyboard, Anda akan melihat angka dan simbol yang menjelaskan status koneksi.

📌 1. Angka = Slot Bluetooth
Angka yang tampil di layar menunjukkan slot penyimpanan perangkat (Bluetooth Profile). <br>
Contoh: <br>
Angka 1 di layar = menggunakan BT_SEL 0 <br>
Angka 2 di layar = menggunakan BT_SEL 1 <br>
Dan seterusnya <br>
Setiap slot dapat menyimpan satu perangkat.


📌 2. Simbol “X”
Jika muncul ikon X, artinya:
Slot tersebut pernah digunakan, tetapi
Tidak sedang terhubung ke perangkat mana pun


📌 3. Pairing Ulang
Jika ingin melakukan pairing ulang untuk slot yang sedang dipakai:
Tekan tombol BT_CLR pada keymap
Layar akan berubah menjadi ikon gerigi (slot di-reset)
Lakukan pairing dari perangkat Anda
Jika berhasil, simbol akan berubah menjadi ikon centang


📌 4. Slot Tidak Bisa Ditimpa
Slot Bluetooth tidak bisa langsung ditimpa perangkat baru.
Jika slot tersebut sudah pernah terhubung ke perangkat lain, Anda harus:
Pindah ke slot lain (BT_SEL berikutnya), atau
Hapus slot dengan tombol BT_CLR

📌 5. Contoh Penggunaan Slot <br> 
Rekomendasi pembagian slot: <br>
BT_SEL 0 → PC <br>
BT_SEL 1 → Tablet <br>
BT_SEL 2 → Mac <br>
Dengan begitu, Anda hanya perlu mengganti slot saat berpindah perangkat.
