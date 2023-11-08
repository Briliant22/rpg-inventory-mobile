# Role-Playing-Games Inventory System Mobile

Muhammad Najmi Briliant (2206082820)
PBP C

## Tautan Aplikasi

[Link to Role-Playing-Games Inventory System]()

## Tugas 7: Elemen Dasar Flutter

> 1. Apa perbedaan utama antara stateless dan stateful widget dalam konteks pengembangan aplikasi Flutter?

Dalam Flutter, widget adalah blok dasar pembangun antarmuka pengguna. Ada dua jenis widget utama:

StatelessWidget: Ini adalah widget yang tidak memerlukan keadaan mutabel atau state. Dengan kata lain, StatelessWidget tidak dapat mengubah apa yang mereka tampilkan setelah mereka dibuat. Hal ini membuatnya cocok untuk UI yang sederhana dan tetap tidak berubah sepanjang waktu penggunaannya. Contohnya adalah widget yang menampilkan judul atau ikon yang tidak pernah berubah, tidak peduli bagaimana interaksi pengguna dengan aplikasi.

StatefulWidget: Sebaliknya, StatefulWidget dapat mempertahankan keadaan yang mungkin berubah selama umur widget. Ketika data yang berhubungan dengan tampilan berubah, widget dapat menggunakan setState() untuk memperbarui UI. Ini penting untuk widget yang interaktif, seperti form, atau informasi yang harus diperbarui secara real-time, seperti countdown timer.

> 2. Sebutkan seluruh widget yang kamu gunakan untuk menyelesaikan tugas ini dan jelaskan fungsinya masing-masing.

1. MaterialApp: Ini adalah widget di tingkat atas yang membungkus sejumlah widget yang membentuk aplikasi material design. Ia mengatur tema, navigasi, dan judul di seluruh aplikasi.

2. Scaffold: Ini menyediakan kerangka dasar untuk implementasi tata letak material di Flutter. Ini memberikan struktur untuk app bar, body, floating action buttons, drawers, dan bottom sheets.

3. AppBar: Sebuah app bar yang biasanya ditampilkan di bagian atas Scaffold. Ia menyediakan space untuk judul, leading, dan actions.

4. SingleChildScrollView: Widget ini menyediakan scrollable area pada layar yang memungkinkan user untuk scroll melalui konten yang tidak muat di layar secara vertikal.

5. Padding: Ini memberikan padding pada widget anaknya, yang berarti memberikan ruang tambahan di sekitar anak widget.

6. Column: Widget ini menata anak-anaknya secara vertikal. Sangat berguna untuk menampilkan widgets dalam bentuk vertikal, satu di atas yang lain.

7. Text: Widget ini menampilkan string teks dengan berbagai styling opsi.

8. GridView: Ini menyediakan grid yang terdiri dari multiple boxes - cells, yang masing-masing bisa menampung widget. Sangat berguna untuk membuat layout yang terstruktur seperti grid view.

9. Icon: Ini menampilkan ikon dari set data ikon material, dengan opsi untuk menyesuaikan ukuran dan warna.

10. InkWell: Sebuah widget yang merespons ketukan dan menunjukkan splash efek ketika di-interaksi oleh pengguna. Ini sering digunakan untuk menambahkan efek visual untuk taps pada container atau card.

11. SnackBar: Ini adalah pesan singkat yang ditampilkan di bagian bawah layar dan digunakan untuk memberikan feedback kepada pengguna.

> 3. Jelaskan bagaimana cara kamu mengimplementasikan checklist di atas secara step-by-step (bukan hanya sekadar mengikuti tutorial)

- [x] Membuat tiga tombol sederhana dengan ikon dan teks untuk:

    - Melihat daftar item (Lihat Item)
    - Menambah item (Tambah Item)
    - Logout (Logout)

    Developer telah mendesain tiga tombol interaktif untuk memenuhi kebutuhan aplikasi dengan membuat sebuah array List<ShopItem> di dalam kelas MyHomePage. Masing-masing ShopItem memiliki label dan ikon yang berhubungan dengan aksi tertentu—yaitu, untuk melihat item, menambahkan item baru, dan proses logout.

    Setiap ShopItem ini selanjutnya ditransformasi menjadi widget ShopCard, yang merupakan komponen visual tombol tersebut di layar pengguna.

- [x] Memunculkan Snackbar dengan tulisan:

    - "Kamu telah menekan tombol Lihat Item" ketika tombol Lihat Item ditekan.
    - "Kamu telah menekan tombol Tambah Item" ketika tombol Tambah Item ditekan.
    - "Kamu telah menekan tombol Logout" ketika tombol Logout ditekan.

    Dalam desain ShopCard, saya menggunakan InkWell untuk menanggapi ketukan pengguna. Di sini, saya menentukan tindakan yang terjadi setelah pengguna mengetuk tombol menggunakan properti onTap.

    Setiap kali pengguna mengetuk salah satu tombol, aplikasi akan memberikan umpan balik langsung dengan menampilkan SnackBar yang berisi pesan yang menginformasikan aksi yang telah dilakukan, contohnya "Kamu telah menekan tombol Lihat Item" untuk tombol dengan label "Lihat Item"

- [x] Melakukan add-commit-push ke GitHub.