# Role-Playing-Games Inventory System Mobile

Muhammad Najmi Briliant (2206082820)
PBP C

## Tautan Aplikasi

[Link to Role-Playing-Games Inventory System]()

## Tugas 8: Flutter Navigation, Layouts, Forms, and Input Elements

> 1. Jelaskan perbedaan antara Navigator.push() dan Navigator.pushReplacement(), disertai dengan contoh mengenai penggunaan kedua metode tersebut yang tepat!

Navigator.push(): Metode ini digunakan untuk menambahkan rute baru ke tumpukan navigasi. Rute baru ditumpuk di atas rute saat ini, sehingga pengguna dapat kembali ke rute sebelumnya.

Contoh penggunaan Navigator.push():

    onPressed: () {
    Navigator.push(
        context,
        MaterialPageRoute(builder: (context) => SecondScreen()),
    );
    }


Navigator.pushReplacement(): Metode ini digunakan untuk mengganti rute saat ini dengan rute baru. Ini berguna ketika Anda ingin mengganti rute saat pengguna menyelesaikan tindakan tertentu dan tidak ingin pengguna kembali ke rute sebelumnya.

Contoh penggunaan Navigator.pushReplacement():

    onPressed: () {
    Navigator.pushReplacement(
        context,
        MaterialPageRoute(builder: (context) => NewScreen()),
    );
    }

> 2. Jelaskan masing-masing layout widget pada Flutter dan konteks penggunaannya masing-masing!

- Container: Digunakan untuk mengelola tata letak dan dekorasi dasar.

- Row dan Column: Digunakan untuk menempatkan widget secara horizontal (Row) atau vertikal (Column).

- Stack: Menempatkan widget di atas satu sama lain.

- ListView dan GridView: Digunakan untuk menampilkan daftar item secara vertikal (ListView) atau sebagai grid (GridView).

- Expanded: Mengalokasikan ruang tambahan untuk widget anak dalam Row, Column, atau Flex.

> 3. Sebutkan apa saja elemen input pada form yang kamu pakai pada tugas kali ini dan jelaskan mengapa kamu menggunakan elemen input tersebut!

Kode ini menggunakan TextFormField untuk Nama Item, Amount, dan Description. Penggunaan elemen input ini sesuai dengan kebutuhan formulir untuk mengumpulkan informasi yang diperlukan tentang item, seperti nama, jumlah, dan deskripsi. Setiap elemen input juga dilengkapi dengan validasi untuk memastikan data yang dimasukkan sesuai dengan kebutuhan aplikasi.

> 4. Bagaimana penerapan clean architecture pada aplikasi Flutter?

- Domain Layer: Berisi aturan bisnis dan logika aplikasi independen dari infrastruktur atau kerangka kerja.

- Data Layer: Menyediakan implementasi konkrit untuk penyimpanan dan pengambilan data.

- Presentation Layer: Menangani tampilan dan interaksi pengguna.

- Dependency Rule: Lapisan lebih dalam tidak boleh memiliki ketergantungan pada lapisan lebih luar.

Contoh penerapan di Flutter bisa mencakup:

- Use Case Classes: Mewakili fungsionalitas aplikasi yang spesifik.

- Repositories: Menyediakan abstraksi untuk mengakses data.

- Interfaces: Digunakan untuk berkomunikasi antara lapisan.
- Models: Representasi objek dalam aplikasi.

Dengan clean architecture, perubahan pada satu lapisan tidak akan secara langsung memengaruhi lapisan lain, memudahkan pengujian dan pemeliharaan.

> 5. Jelaskan bagaimana cara kamu mengimplementasikan checklist di atas secara step-by-step! (bukan hanya sekadar mengikuti tutorial)

- [x] Membuat minimal satu halaman baru pada aplikasi, yaitu halaman formulir tambah item baru dengan ketentuan sebagai berikut:

    - Memakai minimal tiga elemen input, yaitu name, amount, description. Tambahkan elemen input sesuai dengan model pada aplikasi tugas Django yang telah kamu buat.

    - Memiliki sebuah tombol Save.
    - Setiap elemen input di formulir juga harus divalidasi dengan ketentuan sebagai berikut:
        - Setiap elemen input tidak boleh kosong.
        - Setiap elemen input harus berisi data dengan tipe data atribut modelnya.

- [x] Mengarahkan pengguna ke halaman form tambah item baru ketika menekan tombol Tambah Item pada halaman utama.

- [x] Memunculkan data sesuai isi dari formulir yang diisi dalam sebuah pop-up setelah menekan tombol Save pada halaman formulir tambah item baru.

- [x] Membuat sebuah drawer pada aplikasi dengan ketentuan sebagai berikut:

    - Drawer minimal memiliki dua buah opsi, yaitu Halaman Utama dan Tambah Item.
    - Ketika memiih opsi Halaman Utama, maka aplikasi akan mengarahkan pengguna ke halaman utama.
    - Ketika memiih opsi (Tambah Item), maka aplikasi akan mengarahkan pengguna ke halaman form tambah item baru.

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