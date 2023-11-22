# Role-Playing-Games Inventory System Mobile

Muhammad Najmi Briliant (2206082820)
PBP C

## Tautan Aplikasi

[Link to Role-Playing-Games Inventory System]()

## Tugas 9: Integrasi Layanan Web Django dengan Aplikasi Flutter

> 1. Apakah bisa kita melakukan pengambilan data JSON tanpa membuat model terlebih dahulu? Jika iya, apakah hal tersebut lebih baik daripada membuat model sebelum melakukan pengambilan data JSON?

Ya, data JSON di Flutter dapat diambil tanpa perlu membuat model khusus terlebih dahulu. Ini bisa dilakukan dengan menggunakan struktur data bawaan Dart seperti Map dan List untuk menampung dan mengelola data JSON yang diambil.

- Tanpa Model:

Kelebihan: Lebih cepat dan mudah untuk implementasi sederhana; tidak perlu mendefinisikan struktur data terlebih dahulu.
Kekurangan: Kurang efisien untuk data yang kompleks; meningkatkan risiko kesalahan saat mengakses atau memanipulasi data karena tidak ada validasi atau autocompletion.

- Dengan Model:

Kelebihan: Lebih mudah dalam menangani data yang kompleks; memberikan validasi, autocompletion, dan keamanan tipe data yang lebih baik.
Kekurangan: Memerlukan waktu lebih untuk setup awal; kode menjadi lebih banyak dan rumit.

> 2. Jelaskan fungsi dari CookieRequest dan jelaskan mengapa instance CookieRequest perlu untuk dibagikan ke semua komponen di aplikasi Flutter.

- Fungsi CookieRequest:

CookieRequest bukanlah bagian standar dari Flutter atau Dart. Namun, dalam konteks umum pengembangan web dan aplikasi, konsep "CookieRequest" mungkin merujuk pada request HTTP yang mengirimkan atau menerima cookie.Fungsi utamanya biasanya untuk mengelola session dan autentikasi, memungkinkan server mengenali pengguna yang sama di berbagai request.

- Pentingnya Berbagi Instance CookieRequest:

Jika aplikasi Flutter Anda berinteraksi dengan server yang menggunakan cookie untuk autentikasi atau manajemen sesi, sangat penting untuk memastikan bahwa cookie tersebut konsisten di semua komponen aplikasi.Ini memastikan bahwa pengguna tetap terotentikasi atau sesi tetap valid di seluruh aplikasi.

> 3. Jelaskan mekanisme pengambilan data dari JSON hingga dapat ditampilkan pada Flutter.

1. Request Data: 
Gunakan HTTP client (seperti http package di Dart) untuk mengirimkan request ke server.

2. Terima Respons: 
Server mengirimkan respons dalam format JSON.

3. Parsa Respons: 
Gunakan json.decode() untuk mengkonversi string JSON menjadi Map atau List di Dart.

4. Gunakan Data: 
Data yang telah diparsa kemudian dapat digunakan untuk membangun UI atau logika bisnis.

> 4. Jelaskan mekanisme autentikasi dari input data akun pada Flutter ke Django hingga selesainya proses autentikasi oleh Django dan tampilnya menu pada Flutter.

1. Input Data: 
Di Flutter, pengguna memasukkan data akun (biasanya username dan password).

2. Kirim ke Server Django: 
Data dikirim ke server Django menggunakan HTTP request.

3. Proses di Django: 
Django memproses data, melakukan autentikasi (misalnya, memeriksa database untuk username dan password).

4. Respons Autentikasi:
Django mengirimkan respons (sukses/gagal) kembali ke Flutter.

5. Tampilan Menu: 
Jika autentikasi berhasil, aplikasi Flutter menampilkan menu atau melakukan navigasi ke halaman berikutnya.

> 5. Sebutkan seluruh widget yang kamu pakai pada tugas ini dan jelaskan fungsinya masing-masing.

1. Scaffold: Membuat struktur dasar layout visual untuk halaman Flutter.

2. Form: Menggunakan formulir yang memungkinkan validasi data input.

3. TextEditingController: Mengontrol teks yang sedang diedit.

4. AlertDialog: Menampilkan dialog dengan pesan dan beberapa aksi.

5. GlobalKey<FormState>: Memungkinkan validasi form dari tempat lain dalam widget tree.

> 6. Jelaskan bagaimana cara kamu mengimplementasikan checklist di atas secara step-by-step! (bukan hanya sekadar mengikuti tutorial).

- [x] Memastikan deployment proyek tugas Django kamu telah berjalan dengan baik.

Project Django Developer masih belum bisa di deploy oleh PaaS PBP, sehingga pada tugas ini, Developer menggunakan link ke localhost (http://127.0.0.1:8000/). 

- [x] Membuat halaman login pada proyek tugas Flutter.

  1.  Impor Paket yang Diperlukan
  2.  Pengaturan Aplikasi Login
  3.  Membuat file screen Halaman Login
  4.  Mengatur proses Login
  5.  Mengatur Navigasi dan Feedback setelah proses Login

- [x] Mengintegrasikan sistem autentikasi Django dengan proyek tugas Flutter.

- [x] Membuat model kustom sesuai dengan proyek aplikasi Django.

Developer membuat model Item untuk menampung data dari Item yang dibuat pengguna.

      Fields({
        required this.user,
        required this.name,
        required this.power,
        required this.price,
        required this.amount,
        required this.category,
        required this.description,
      });

- [x] Membuat halaman yang berisi daftar semua item yang terdapat pada endpoint JSON di Django yang telah kamu deploy.

    - Tampilkan name, amount, dan description dari masing-masing item pada halaman ini.

      return ListView.builder(
        itemCount: snapshot.data!.length,
        itemBuilder: (_, index) => Container(
            margin: const EdgeInsets.symmetric (
                horizontal: 16, vertical: 12
            ),
            padding: const EdgeInsets.all(20.0),
            child: Column(
              mainAxisAlignment: MainAxisAlignment.start,
              crossAxisAlignment: CrossAxisAlignment.start,
              children: [
                Text(
                  "${snapshot.data![index].fields.name}",
                  style: const TextStyle(
                      fontSize: 18.0,
                      fontWeight: FontWeight.bold,
                  ),
                ),
                const SizedBox(height: 10),
                Text("${snapshot.data![index].fields.power}"),
                const SizedBox(height: 10),
                Text("${snapshot.data![index].fields.price}"),
                const SizedBox(height: 10),
                Text("${snapshot.data![index].fields.amount}"),
                const SizedBox(height: 10),
                Text(
                    "${snapshot.data![index].fields.category}"
                ),
                const SizedBox(height: 10),
                Text(
                    "${snapshot.data![index].fields.description}"
                )
              ],
            ),
        )
      );

- [x] Membuat halaman detail untuk setiap item yang terdapat pada halaman daftar Item.

    - Halaman ini dapat diakses dengan menekan salah satu item pada halaman daftar Item.

    - Tampilkan seluruh atribut pada model item kamu pada halaman ini.

    - Tambahkan tombol untuk kembali ke halaman daftar item.

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

        Membuat sebuah kelas yang merupakan StatefulWidget, karena formulir ini akan mengalami perubahan status ketika pengguna melakukan input. Kelas ShopFormPage ini akan berfungsi sebagai kerangka untuk halaman formulir.

        Di dalam State dari ShopFormPage, Developer menentukan beberapa variabel yang akan menyimpan nilai dari setiap TextFormField, sesuai dengan atribut model pada aplikasi Django yang telah dibuat sebelumnya.

        Developer menggunakan GlobalKey untuk FormState agar dapat mengontrol form dari luar widget form itu sendiri, contohnya untuk melakukan validasi formulir.

    - Memiliki sebuah tombol Save.
        
        Setelah semua input telah diisi dan melewati proses validasi, pengguna dapat menekan tombol 'Save', yang kemudian akan memunculkan dialog yang menampilkan informasi yang telah diinput. Informasi tersebut akan disimpan ke dalam list item.

    - Setiap elemen input di formulir juga harus divalidasi dengan ketentuan sebagai berikut:
        - Setiap elemen input tidak boleh kosong.
        - Setiap elemen input harus berisi data dengan tipe data atribut modelnya.

        Setiap TextFormField memiliki validator untuk memastikan bahwa field tersebut tidak kosong dan harus sesuai tipe datanya. Sebagai contoh, untuk amount yang harus berupa integer, validator akan menolak nilai yang merupakan character selain angka.

- [x] Mengarahkan pengguna ke halaman form tambah item baru ketika menekan tombol Tambah Item pada halaman utama.

    Untuk me-routing pengguna ke ShopFormpage untuk menambah item baru saat tombol "Tambah Item" ditekan pada halaman utama, developer telah membuat sebuah ShopCard widget yang merupakan StatelessWidget. Di dalam widget ini, InkWell digunakan untuk menangani ketukan, dan menggunakan Navigator.push untuk berpindah halaman.

    Saat InkWell di-tap, kondisi dicek untuk nama item. Jika nama item adalah "Tambah Item", maka aplikasi akan me-routing ke ShopFormPage yang merupakan formulir untuk menambah item baru. Jika nama item adalah "Lihat Item", maka akan navigasi ke ItemListPage yang merupakan halaman untuk menampilkan daftar item. Pada tombol lainnya, sebuah SnackBar akan ditampilkan memberitahukan pengguna bahwa mereka telah menekan tombol dengan nama item tersebut.

- [x] Memunculkan data sesuai isi dari formulir yang diisi dalam sebuah pop-up setelah menekan tombol Save pada halaman formulir tambah item baru.

    Setelah seluruh input sudah diisi dan divalidasi, tombol 'Save' akan memicu dialog yang menampilkan informasi yang telah diinput dan menyimpannya ke dalam list item.

              Align(
                alignment: Alignment.bottomCenter,
                child: Padding(
                  padding: const EdgeInsets.all(8.0),
                  child: ElevatedButton(
                    style: ButtonStyle(
                      backgroundColor: MaterialStateProperty.all(Colors.indigo),
                    ),
                    onPressed: () {
                      if (_formKey.currentState!.validate()) {
                        listItem.add(Item(_name, _amount, _description));
                        showDialog(
                            context: context,
                            builder: (context) {
                              return AlertDialog(
                                title: const Text('Item berhasil tersimpan'),
                                content: SingleChildScrollView(
                                  child: Column(
                                    crossAxisAlignment:
                                        CrossAxisAlignment.start,
                                    children: [
                                      Text('Nama: $_name'),
                                      Text('Price: $_amount'),
                                      Text('Description: $_description'),
                                    ],
                                  ),
                                ),
                                actions: [
                                  TextButton(
                                      onPressed: () {
                                        Navigator.pop(context);
                                      },
                                      child: const Text('OK'))
                                ],
                              );
                            });
                        _formKey.currentState!.reset();
                      }
                    },
                    child: const Text(
                      "Save",
                      style: TextStyle(color: Colors.white),
                    ),
                  ),
                ),
              ),

- [x] Membuat sebuah drawer pada aplikasi dengan ketentuan sebagai berikut:

    - Drawer minimal memiliki dua buah opsi, yaitu Halaman Utama dan Tambah Item.
    - Ketika memiih opsi Halaman Utama, maka aplikasi akan mengarahkan pengguna ke halaman utama.
    - Ketika memiih opsi (Tambah Item), maka aplikasi akan mengarahkan pengguna ke halaman form tambah item baru.

    Berikut kode untuk membuat drawer:

    class LeftDrawer extends StatelessWidget {
        const LeftDrawer({super.key});

        @override
        Widget build(BuildContext context) {
            return Drawer(
            child: ListView(
                children: [
                const DrawerHeader(
                    // TODO: Bagian drawer header
                    decoration: BoxDecoration(
                      color: Colors.indigo,
                    ),
                    child: Column(
                      children: [
                        Text(
                          'Shopping List',
                          textAlign: TextAlign.center,
                          style: TextStyle(
                            fontSize: 30,
                            fontWeight: FontWeight.bold,
                            color: Colors.white,
                          ),
                        ),
                        Padding(padding: EdgeInsets.all(10)),
                        Text(
                          "Catat seluruh keperluan belanjamu di sini!",
                          // TODO: Tambahkan gaya teks dengan center alignment, font ukuran 15, warna putih, dan weight biasa
                        ),
                      ],
                  ),
                ),
                // TODO: Bagian routing
                ListTile(
                    leading: const Icon(Icons.home_outlined),
                    title: const Text('Halaman Utama'),
                    // Bagian redirection ke MyHomePage
                    onTap: () {
                    Navigator.pushReplacement(
                        context,
                        MaterialPageRoute(
                            builder: (context) => MyHomePage(),
                        ));
                    },
                ),
                ListTile(
                    leading: const Icon(Icons.add_shopping_cart),
                    title: const Text('Tambah Item'),
                    // Bagian redirection ke ShopFormPage
                    onTap: () {
                    /*
                    TODO: Buatlah routing ke ShopFormPage di sini,
                    setelah halaman ShopFormPage sudah dibuat.
                    */
                    Navigator.push(
                        context,
                        MaterialPageRoute(
                        builder: (context) => const ShopFormPage(),
                        ),
                    );
                  },
                ),
                ListTile(
                    leading: const Icon(Icons.app_registration_rounded),
                    title: const Text('Lihat Item'),
                    // Bagian redirection ke ShopFormPage
                    onTap: () {
                    Navigator.push(
                        context,
                        MaterialPageRoute(
                        builder: (context) => const ItemListPage(),
                        ),
                    );

                  },
                ),
              ],
            ),
          );
        }
      }

## Tugas 7: Elemen Dasar Flutter

> 1. Apa perbedaan utama antara stateless dan stateful widget dalam konteks Developeran aplikasi Flutter?

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