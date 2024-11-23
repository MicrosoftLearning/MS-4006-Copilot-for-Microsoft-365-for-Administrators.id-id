## Penyewa WWL - Ketentuan penggunaan

Jika Anda diberikan penyewa sebagai bagian dari penyajian pelatihan yang dipimpin instruktur, harap diperhatikan bahwa penyewa tersedia untuk mendukung lab praktik dalam pelatihan yang dipimpin instruktur. 

Penyewa tidak boleh dibagikan atau digunakan untuk tujuan di luar lab praktik. Penyewa yang digunakan dalam kursus ini adalah penyewa uji coba dan tidak dapat digunakan atau diakses setelah kelas berakhir dan tidak memenuhi syarat perpanjangan. 

Penyewa tidak boleh dikonversi ke langganan berbayar. Penyewa yang diperoleh sebagai bagian dari kursus ini tetap menjadi milik Microsoft Corporation dan kami berhak mendapatkan akses dan repositorinya kapan saja. 

# Jalur Pembelajaran 1 - Lab 1 - Latihan 1 - Inisialisasi Penyewa Microsoft 365 Anda 

Adatum Corporation adalah anak perusahaan dari Contoso Electronics. Adatum menjalankan aplikasi lamanya (seperti Microsoft Server Exchange 2019) dalam penyebaran secara lokal. Namun, baru-baru ini berlangganan Microsoft 365, sehingga membuat penyebaran hibrid di mana ia harus menyinkronkan penyebaran lokal dan cloudnya. 

Sebagai administrator Microsoft 365 Adatum, Anda telah ditugaskan untuk menyebarkan Microsoft 365 dalam penyebaran hibrid Adatum menggunakan lingkungan lab virtual. Dalam latihan ini, Anda akan mengatur penyewa uji coba Microsoft 365 Adatum, dan instruktur Anda akan memandu Anda tentang cara mendapatkan kredensial Microsoft 365 di lingkungan yang dihosting di lab Anda. Anda akan menggunakan kredensial ini di seluruh lab yang tersisa dalam kursus ini. 

Di lingkungan lab Anda, penyedia hosting lab Anda telah mendapatkan penyewa uji coba Microsoft 365 untuk Anda. Penyedia lab Anda juga telah membuat dua akun admin yang akan Anda gunakan di lingkungan lab VM Anda: 

- Akun administrator lokal untuk lingkungan lokal Adatum (Adatum\Administrator).
- Akun admin penyewa default di Microsoft 365 (nama tampilan untuk akun pengguna ini adalah Administrator MOD). 

Anda akan masuk ke PC Klien 1 (LON-CL1) menggunakan akun Adatum\Administrator lokal. Saat mengakses Microsoft 365 untuk pertama kalinya, Anda awalnya akan masuk menggunakan akun admin penyewa Microsoft 365 (Administrator MOD). Anda kemudian akan menyiapkan penyewa Microsoft 365 Adatum untuk Microsoft Entra ID dan untuk lab selanjutnya menggunakan pemberitahuan audit dan Microsoft Graph PowerShell.


### Tugas 1- Menyiapkan Profil Organisasi Adatum

Di seluruh lab dalam kursus ini, Anda akan bermain peran dengan mengambil peran sebagai Holly Dickson, Admin Microsoft 365 istrator Adatum. Dalam peran Anda sebagai Holly, Anda ditugaskan untuk menyiapkan profil perusahaan untuk penyewa uji coba Microsoft 365-nya. Dalam tugas ini, Anda akan mengonfigurasi opsi yang diperlukan untuk penyewa Adatum. Karena Holly belum membuat akun pengguna Microsoft 365 pribadi untuk dirinya sendiri (Anda akan melakukan ini di latihan lab berikutnya), Holly awalnya akan masuk ke Microsoft 365 menggunakan akun admin penyewa microsoft 365 default dan kata sandi yang dibuat oleh penyedia hosting lab Anda. Akun ini adalah akun Administrator MOD, yang aliasnya adalah "admin". Nama pengguna untuk akun ini adalah admin@xxxxxZZZZZZ.onmicrosoft.com (di mana xxxxxZZZZZZ adalah awalan penyewa yang ditetapkan oleh penyedia hosting lab Anda); nama tampilan untuk akun ini akan menjadi Administrator MOD.

1. Penyedia hosting lab Anda akan menyediakan dua kata sandi yang digunakan dengan akun pengguna fiktif di penyewa uji coba Microsoft 365 Anda. Akun Administrator MOD, yang merupakan administrator penyewa default, telah diberi **Kata Sandi Administratif**. Semua pengguna lain - bahkan mereka yang diberi peran admin - telah diberi **Kata Sandi Pengguna**. <br>

    Untuk tujuan keamanan, Microsoft telah mengonfigurasi penyewa uji coba Anda sehingga semua pengguna yang telah ditentukan harus mengubah kata sandi mereka saat masuk berikutnya. Beberapa penyedia hosting lab dapat menyediakan dua bidang kata sandi baru, satu untuk administrator (sebenarnya, admin MOD dan Holly Dickson) dan satu untuk semua pengguna lain. Jika kedua bidang kata sandi baru ini muncul di VM Anda, masukkan kata sandi baru untuk masing-masing bidang. Nilai kata sandi baru ini akan disimpan di VM dan ditampilkan dalam instruksi lab. <br>
 
    Penyedia hosting lab lainnya mungkin tidak menyediakan bidang kata sandi baru ini. Untuk lingkungan tersebut, Anda harus menuliskan kata sandi baru secara manual yang Anda rencanakan untuk ditetapkan kepada pengguna yang masuk. <br>

    Saat mendesain kata sandi baru Anda, ingatlah panduan kata sandi Microsoft: <br>

    - Minimum 8 karakter, dengan setidaknya:
       - 1 karakter huruf besar
       - 1 karakter huruf kecil
       - 1 karakter khusus Kata sandi tidak akan divalidasi terhadap persyaratan Microsoft sampai Anda mengubah kata sandi lama pada saat pengguna masuk selanjutnya.

2. Saat Anda membuka lingkungan Komputer Virtual penyedia hosting lab, Anda perlu memulai dengan VM Klien 1 (LON-CL1). Jika lingkungan VM Anda terbuka dengan salah satu komputer lain (seperti LON-DC1), maka beralihlah ke **LON-CL1** sekarang.

3. Masuk ke **LON-CL1** sebagai akun **Administrator** lokal yang dibuat oleh penyedia hosting lab Anda dengan kata sandi **Pa55w.rd**. 

4. Pada taskbar, di bawah layar Anda, pilih ikon **Microsoft Edge**. Jika perlu, maksimalkan jendela browser Anda saat terbuka.

5. Di browser Edge Anda, buka halaman **Beranda Microsoft 365** dengan memasukkan URL berikut di bilah alamat: **https://portal.office.com** 

6. Dalam kotak dialog **Masuk** , masukkan **Nama Pengguna Administratif** yang disediakan oleh penyedia hosting lab Anda (ini adalah akun Administrator MOD) untuk penyewa uji coba Microsoft 365 Anda. Nama pengguna harus dalam bentuk **admin@xxxxxZZZZZZ.onmicrosoft.com**, di mana xxxxxZZZZZZ adalah awalan penyewa yang ditetapkan oleh penyedia hosting lab Anda. Pilih **Selanjutnya**. <br/>

    **Catatan:** Dalam instruksi lab yang muncul di lingkungan lab VM Anda, penyedia hosting lab Anda mungkin menyediakan kemampuan untuk memilih tombol **Ketik teks** (atau yang setara) di samping data sumber daya seperti nama pengguna, kata sandi, perintah PowerShell, dan data lain yang harus dimasukkan di sepanjang lab ini. Penyedia hosting lab lainnya dapat menyediakan metode alternatif, seperti kemampuan untuk menyalin dan menempelkan informasi ini. Manfaatkan fungsionalitas ini untuk menyelamatkan diri Anda dari keharusan memasukkan informasi ini secara manual. 

7. Dalam kotak dialog **Masukkan kata sandi**, masukkan **Kata Sandi Administratif** yang telah ditentukan sebelumnya yang disediakan oleh penyedia hosting lab Anda lalu pilih **Masuk**. 

8. Penyedia hosting lab Anda mungkin atau mungkin belum mengonfigurasi akun Admin MOD untuk memerlukan kata sandi baru saat masuk. Jika ya, maka kotak dialog **Perbarui kata sandi Anda** akan muncul. Jika ini terjadi, masukkan **Kata Sandi Administratif** yang disediakan oleh penyedia hosting lab Anda di bidang **Kata sandi saat ini**, lalu masukkan Kata Sandi Administratif Baru di bidang **Kata sandi baru** dan **Konfirmasi kata sandi** dan pilih **Masuk**.

9. Jika kotak dialog **Tetap masuk?** muncul, pilih kotak centang **Jangan perlihatkan ini lagi** lalu pilih **Ya.** 

10. Jika kotak dialog **Selamat Datang di Microsoft 365** muncul di tengah layar, tidak ada opsi untuk menutupnya. Sebagai gantinya, di sebelah kanan jendela, pilih ikon panah maju (**>**) dua kali lalu pilih ikon tanda centang untuk menelusuri slide di jendela olahpesan ini. 

11. Jika kotak dialog **Temukan aplikasi lainnya** atau kotak dialog **Buat dengan Microsoft 365** muncul, pilih **X** di sudut atas kotak untuk menutupnya. Demikian pula, jika kotak dialog Masuk ke Microsoft Edge muncul, pilih tombol **Tidak terima kasih** .

12. Halaman **Selamat Datang di Microsoft 365** muncul di browser Edge Anda di tab **Beranda | Microsoft 365**. Ini adalah halaman beranda Administrator MOD Microsoft 365. <br/>

    Perhatikan bahwa ikon atau lingkaran dengan "MA" (inisial untuk Administrator MOD) muncul di sudut kanan atas layar. Beberapa penyewa uji coba memperlihatkan ikon; yang lain menunjukkan inisial "MA" dalam lingkaran; semuanya tergantung pada apakah penyedia hosting lab Anda menambahkan ikon ke akun Administrator MOD. Ikon atau inisial mewakili **akun Administrator MOD**, yang merupakan akun administrator penyewa yang dibuat oleh penyedia hosting lab Anda yang baru saja Anda masuki. Jika salah satu akun pengguna Microsoft 365 yang sudah ada yang dibuat oleh penyedia hosting lab Anda memiliki gambar yang terkait dengan akun mereka, gambar pengguna akan ditampilkan dan bukan inisial pengguna saat Anda masuk ke Microsoft 365 sebagai pengguna tersebut. Namun, ketika pengguna seperti Administrator MOD tidak memiliki gambar yang ditetapkan untuknya, inisial pengguna akan ditampilkan sebagai pengganti gambar, atau ikon akan ditampilkan jika ada yang ditetapkan ke akun oleh penyedia hosting lab Anda. <br/>

    Pada halaman **Selamat Datang di Microsoft 365**, dalam daftar ikon aplikasi yang muncul di panel navigasi, pilih **Admin**; ini membuka **pusat admin Microsoft 365** di tab browser baru. 

13. Dari panel navigasi **pusat admin Microsoft 365**, pilih **Tampilkan semua**, lalu pilih **Pengaturan**. Di grup **Pengaturan**, pilih **Pengaturan organisasi**. 

14. Pada halaman **Pengaturan organisasi**, tab **Layanan** ditampilkan secara default. Pilih tab **Profil organisasi**.

15. Di tab **Profil organisasi** , pilih **Informasi organisasi** dari daftar data profil.

16. Di panel **Informasi organisasi** yang muncul, masukkan informasi berikut ini: <br/>

    - Nama: **Adatum Corporation** (Catatan: Adatum Corporation adalah anak perusahaan dari Contoso Inc. Penyewa uji coba Microsoft yang diperoleh penyedia hosting lab Anda untuk lab ini mungkin awalnya ditetapkan ke Contoso. Jika **Contoso** (atau nilai lainnya) muncul sebagai nama organisasi, maka ubah menjadi **Adatum Corporation**.)

    - Alamat Jalan: **555 Main Street**

    - Kota: **Redmond**

    - Negara bagian atau provinsi: **Washington**

    - Kode ZIP/kode pos: **98052**

    - Telepon: jangan ubah

    - Kontak teknis: jangan ubah

    - Bahasa pilihan: **Bahasa Inggris**

17. Pilih **Simpan**.

18. Di bagian atas panel **Informasi organisasi**, perhatikan pesan yang menunjukkan perubahan telah disimpan. Pilih **X** di sudut kanan atas panel untuk menutupnya.

19. Tetap masuk ke **LON-CL1** dengan Microsoft Edge terbuka ke **pusat admin Microsoft 365** untuk tugas berikutnya.

### Tugas 2- Membuat tema kustom untuk tim proyek pilot Adatum

Dalam tugas sebelumnya, Anda mempelajari bahwa ketika seseorang masuk ke Microsoft 365, sistem akan menampilkan foto mereka (jika disediakan), atau inisialnya jika tidak ada foto yang disediakan. Holly Dickson, Administrator Microsoft 365 Adatum, tidak puas hanya melihat gambar atau inisial pengguna yang masuk. Dia ingin membuat tema kustom untuk anggota tim proyek pilotnya sehingga juga menampilkan nama pengguna yang masuk. Di akhir proyek pilot, jika anggota tim proyek pilot lebih suka desain ini, dia akan mengonfigurasi opsi yang sama ini dalam tema default sehingga berlaku untuk semua pengguna. 

Tema kustom harus dikaitkan dengan satu atau beberapa grup Microsoft 365. Oleh karena itu, untuk menerapkan perubahan ini, Holly harus terlebih dahulu membuat grup Microsoft 365 untuk anggota tim proyek pilot. Dia kemudian dapat membuat tema kustom yang terkait dengan grup ini yang memungkinkan pengaturan untuk menampilkan nama pengguna yang masuk. Dalam tugas ini, Anda akan membuat grup Microsoft 365 untuk anggota tim proyek pilot Microsoft 365 Adatum. Anda kemudian akan membuat tema kustom yang menampilkan nama pengguna yang masuk, dan Anda akan menetapkan tim proyek pilot ke tema ini. Anda juga akan meninjau opsi lain yang dapat dikonfigurasi dengan tema kustom, dan Anda dapat membuat perubahan warna apa pun yang Anda inginkan.

**Penting:** Di akhir tugas ini, Anda akan mencoba menyimpan tema kustom yang Anda buat. Ada masalah platform yang diketahui di pusat admin Microsoft 365 di mana kadang-kadang menyimpan tema kustom dengan baik- baik saja, dan di lain waktu mengembalikan pesan yang mengatakan "Maaf, kami tidak dapat menyimpan tema Anda. Coba lagi nanti." Jika Anda menerima pesan ini, tidak ada yang dapat Anda lakukan selain melanjutkan. Mencoba menyimpan tema di lain waktu biasanya mengembalikan kesalahan yang sama. Masalah ini tidak akan memengaruhi lab di masa mendatang, selain itu tidak akan menampilkan nama pengguna di samping ikon pengguna atau inisial mereka di baris judul. Terlepas dari masalah yang diketahui ini, kami masih ingin Anda melakukan tugas ini untuk mendapatkan pengalaman dalam membuat tema, meskipun mungkin tidak disimpan di penyewa uji coba Anda.

1. Anda harus tetap masuk ke LON-CL1 sebagai akun **adatum\administrator** lokal, dan di peramban Edge, Anda harus tetap masuk ke Microsoft 365 sebagai **MOD Administrator**. 

2. Di **Pusat admin Microsoft 365**, pilih **Tim & grup** di panel navigasi, lalu di bawahnya, pilih **Tim & grup yang aktif**. 

3. Pada halaman **Tim dan grup yang aktif** terdapat tab untuk melihat masing-masing jenis grup. Tab **Tim & grup Microsoft 365** ditampilkan secara default. Tab ini menampilkan grup Microsoft 365 yang sudah ada.  <br/>

    Pilih opsi **+Tambahkan grup Microsoft 365** yang muncul pada bilah menu di atas daftar Tim dan grup Microsoft 365. Ini akan memulai wizard **Tambahkan grup Microsoft 365** . 

4. Pada wizard **Tambahkan grup Microsoft 365**, pada halaman **Mengatur dasar-dasar**, masukkan **Proyek percontohan Microsoft 365** pada bidang **Nama**, lalu masukkan **Anggota tim proyek percontohan Microsoft 365** pada bidang **Deskripsi** (Catatan: meskipun Anda tidak memasukkan deskripsi, Anda harus tetap memilih ke dalam bidang ini untuk mengaktifkan tombol **Selanjutnya**). Pilih **Selanjutnya**.

5. Anda sekarang akan menetapkan Administrator MOD sebagai pemilik grup **proyek pilot M365**. Di jendela **Tetapkan pemilik**, pilih **+Tetapkan pemilik**.
    
6. Di panel **Tetapkan pemilik** yang muncul, pilih kotak centang di samping **Administrator MOD**, lalu pilih tombol **Tambahkan (1)** di bagian bawah panel.

7. Pada halaman **Tetapkan pemilik** , Administrator MOD akan muncul sebagai pemilik grup. Pilih **Selanjutnya**.

8. Anda sekarang akan menetapkan anggota ke grup proyek pilot M365. Di halaman **Tambahkan anggota**, pilih **+Tambahkan anggota**.

9. Di panel **Tambahkan anggota** yang muncul, pilih kotak centang di samping pengguna berikut (dalam urutan alfabet): **Alex Wilber**, **Allan Deyoung**, **Diego Siciliani**, **Isaiah Langer**, **Joni Sherman**, **Lynne Robbins**, **Megan Bowen**, **ADMINISTRATOR MOD**, **Nestor Wilke**, dan **Patti Fernandez**. Pilih tombol **Tambahkan (10)** di bagian bawah panel.

10. Pada halaman **Tambahkan anggota** , verifikasi bahwa 10 pengguna ini terdaftar sebagai anggota grup. Jika Anda melewatkan pengguna, pilih **+Tambahkan anggota** lalu tambahkan salah satu dari 10 pengguna yang Anda lewatkan. Ketika semua 10 pengguna muncul di halaman ini, pilih **Berikutnya**.

11. Di halaman **Edit pengaturan**, masukkan informasi berikut: <br/>

    - Masukkan **m365pilotproject** di bidang **Alamat email grup**.
    - Di bidang **Privasi**, pilih **Privat**.
    - Di bawah bagian **Tambahkan Microsoft Teams ke grup Anda**, verifikasi kotak centang **Buat tim untuk grup ini** terpilih (pilih jika kosong), lalu pilih **Berikutnya**.

12. Di halaman **Tinjau dan selesaikan penambahan grup**, tinjau konten yang Anda masukkan. Jika ada yang perlu diperbaiki, pilih **Edit** di bawah area tertentu yang memerlukan penyesuaian, buat koreksi yang diperlukan, lalu pilih **Berikutnya** untuk melanjutkan kembali ke halaman ini. Setelah semuanya benar, pilih **Buat grup**.

13. Setelah jendela **grup proyek pilot M365 dibuat** muncul, perhatikan komentar di bagian atas halaman bahwa mungkin perlu waktu 5 menit agar grup baru muncul dalam daftar Grup aktif.  </br>

    Pilih **Tutup.** Ini mengembalikan Anda ke halaman **Tim aktif dan grup**, yang seharusnya menampilkan tab **grup Teams & Microsoft 365**. Karena grup proyek pilot M365 adalah grup Microsoft 365, grup tersebut akhirnya akan ditampilkan pada tab ini. Jika perlu, pilih opsi **Refresh** pada bilah menu hingga Anda melihat grup proyek pilot M365 dalam daftar grup Teams dan Microsoft 365.

14. Di **pusat admin Microsoft 365**, pilih **Pengaturan** di panel navigasi lalu pilih **Pengaturan organisasi**. 

15. Pada halaman **Pengaturan organisasi**, tab **Layanan** ditampilkan secara default. Pilih tab **Profil organisasi**.

16. Tab **Profil organisasi** menampilkan daftar data profil organisasi. Dalam daftar data, pilih **Tema kustom**.

17. Di panel **Kustomisasi Microsoft 365 untuk organisasi Anda** yang muncul, Anda bisa mengkustomisasi tema default yang dilihat pengguna saat masuk ke Microsoft 365, dan Anda bisa menambahkan tema kustom tambahan. Anda ingin membuat tema kustom baru yang hanya berlaku untuk anggota grup **proyek pilot M365** yang sebelumnya Anda buat, jadi pilih opsi **+Tambahkan tema** .

18. Di panel **Tema grup baru** yang muncul, tab **Umum** ditampilkan secara default. Masukkan **tema proyek pilot M365** di bidang **Nama** .

19. Pilih di dalam bidang **Grup**. Dalam daftar grup yang muncul, pilih **proyek pilot M365** jika muncul dalam daftar grup. <br/>

    **Catatan:** Jika **proyek pilot M365** tidak muncul dalam daftar grup, masukkan **M365** di bidang **Grup**. Kotak hasil pencarian akan muncul yang menampilkan grup **proyek percontohan M365**. Pilih **proyek pilot M365**. 

20. Pilih kotak centang **Perlihatkan nama tampilan pengguna**. Ini adalah pengaturan yang Holly ingin sesuaikan untuk anggota tim proyek pilot M365. Opsi ini menampilkan nama pengguna yang masuk di samping inisial mereka di setiap judul jendela.
 
21. Pilih tab **Logo** dan luangkan waktu untuk meninjau opsinya. Lakukan hal yang sama untuk tab **Warna**. Perhatikan berbagai tema dan opsi merek yang tersedia untuk Anda perbarui. <br/>

    Untuk tujuan lab ini, Anda dapat mengubah salah satu opsi atau membiarkan nilai default apa adanya. Misalnya, di lingkungan dunia nyata, Anda dapat menambahkan logo perusahaan Anda dan mengatur gambar latar belakang sebagai default untuk semua pengguna Anda. Untuk lab ini, jangan ragu untuk mengubah warna panel navigasi, warna teks, warna ikon, dan warna aksen Anda. <br/>

    **Lanjutkan dan jelajahi berbagai opsi untuk tema ini yang akan digunakan oleh anggota tim proyek pilot Microsoft 365. Buat perubahan apa pun yang Anda inginkan.** <br/>

    **Tips:** Beberapa pola warna secara estetis mengalihkan perhatian pengguna. Jika Anda mengubah salah satu warna, disarankan agar Anda menghindari penggunaan warna kontras tinggi secara bersama, seperti warna neon dan warna resolusi tinggi seperti merah muda cerah dan putih.

22. Pilih **Simpan**. 

    **Catatan:** Seperti yang disebutkan sebelumnya di awal tugas ini, ada masalah platform yang diketahui di pusat admin Microsoft 365 di mana terkadang ini menyimpan tema kustom baru, dan di lain waktu menampilkan pesan yang bertuliskan "Maaf, kami tidak dapat menyimpan tema Anda. Coba lagi nanti." Jika Anda menerima pesan ini, pesan tersebut tidak akan memengaruhi lab di masa mendatang. Karena tema kustom Anda tidak disimpan, sistem tidak akan menampilkan nama pengguna di samping ikon pengguna atau inisial mereka pada baris judul (ditambah perubahan warna apa pun yang mungkin telah Anda buat tidak akan muncul). Kami masih meminta Anda untuk melakukan tugas ini meskipun Anda mungkin menerima pesan ini untuk mendapatkan pengalaman membuat tema seperti ini. Jadi jika Anda mendapatkan kesalahan ini, lewati langkah berikutnya, yang menguji tema kustom. Namun, Anda masih dapat melakukan langkah-langkah yang tersisa mengikuti langkah berikutnya untuk mempelajari tentang tema Default. Apakah tema kustom Anda disimpan atau tidak, tutup panel **tema proyek pilot M365**.

23. Jika tema kustom Anda tidak disimpan, maka lewati ke langkah berikutnya. Namun, jika tema kustom Anda disimpan, pilih ikon **Refresh** di bagian atas layar, di sebelah kiri bilah alamat. Setelah layar di-refresh, perhatikan bagaimana nama **Administrator MOD** muncul di sebelah kiri lingkaran dengan inisial MA atau ikon yang dipilih untuk akun ini oleh penyedia hosting lab Anda. Saat anggota tim proyek pilot Microsoft 365 masuk ke Microsoft 365, tema kustom ini akan menampilkan nama pengguna mereka, sama seperti nama Administrator MOD yang muncul di sini. 

24. Dalam daftar data profil organisasi, pilih **Tema kustom**.

25. Di panel **Kustomisasi Microsoft 365 untuk organisasi Anda** yang muncul, perhatikan cara menampilkan **tema Default** dan **tema proyek pilot M365** (jika tema disimpan di langkah sebelumnya). Memilih **Tema default**. 

26. Pada panel **Tema default**, perhatikan bagaimana **Opsi Perlihatkan nama tampilan pengguna** tidak dipilih untuk tema default. Jika Holly kemudian memutuskan untuk menjadikan opsi **Tampilkan nama tampilan pengguna** sebagai fitur permanen, dia akan memilih opsi ini di panel **Tema default** sehingga berlaku untuk semua pengguna Adatum, dan dia akan menghapus **tema proyek Pilot M365**. <br/>

    **Catatan:** Jika Anda mendapatkan pesan kesalahan "Maaf, kami tidak dapat menyimpan tema Anda. Coba lagi nanti." saat sebelumnya Anda mencoba menyimpan tema kustom Anda, maka pilih opsi **Tampilkan nama tampilan pengguna** ini pada tema Default, lalu pilih **Simpan**. Kami ingin Anda melihat apa yang terjadi ketika opsi ini dipilih, meskipun jika Anda tidak dapat menyimpan tema kustom Anda. Jika Anda mengatur opsi ini pada tema Default, lalu pilih ikon **Refresh** di bagian atas layar, di sebelah kiri bilah alamat. Setelah layar di-refresh, perhatikan bagaimana nama **Administrator MOD** muncul di sebelah kiri lingkaran dengan inisial MA atau ikon yang dipilih untuk akun ini oleh penyedia hosting lab Anda.
 
27. Tutup panel **Tema default**.

28. Tetap masuk ke **LON-CL1** dengan Microsoft Edge terbuka ke **pusat admin Microsoft 365** untuk tugas berikutnya.

### Tugas 3 – Menginstal Microsoft Graph PowerShell 

Microsoft Graph PowerShell diperlukan untuk melakukan beberapa tugas konfigurasi saat menginstal Microsoft 365. Karena latihan lab di masa mendatang akan melakukan beberapa tugas ini menggunakan Windows PowerShell, Anda harus mulai dengan menginstal modul Microsoft Graph PowerShell. Modul ini memungkinkan Anda melakukan banyak tugas administrasi pengguna dan organisasi Microsoft 365 melalui PowerShell. Ini cocok untuk tugas massal seperti pengaturan ulang kata sandi, kebijakan kata sandi, manajemen lisensi dan pelaporan, dan sebagainya.  

1. Pada LON-CL1, Anda masih harus masuk sebagai akun **adatum\administrator** lokal. Untuk menginstal Microsoft Graph PowerShell, Anda harus membuka instans **Windows PowerShell** yang ditingkatkan. Ketik **daya** dalam kotak Pencarian yang muncul di sudut kiri bawah taskbar. Dalam daftar hasil pencarian, klik kanan pada **Windows PowerShell** (jangan pilih Windows PowerShell ISE) dan pilih **Jalankan sebagai administrator** di menu drop-down yang muncul. 

2. Maksimalkan jendela PowerShell Anda. Di **Windows PowerShell**, ketik perintah berikut pada baris perintah untuk menginstal modul Microsoft Graph PowerShell dari Galeri PowerShell lalu tekan Enter: <br/>

        Install-Module Microsoft.Graph -Scope CurrentUser

3. Anda akan diminta untuk mengonfirmasi apakah Anda ingin menginstal modul dari repositori yang tidak tepercaya (PSGallery). Masukkan **A** untuk memilih **[A] Ya untuk Semua** lalu tekan Enter.  <br/>

    **Catatan:** Respons Anda akan memulai penginstalan semua sub-modul Microsoft Graph. Setelah semua pesan penginstalan untuk setiap sub-modul selesai ditampilkan, masih akan memakan waktu sekitar 5 hingga 10 menit tambahan untuk menyelesaikan penginstalan Microsoft Graph PowerShell. Selama waktu ini, kursor akan terus berkedip di bawah pesan repositori yang tidak tepercaya. <br/>

    **Ini mungkin waktu yang tepat untuk beristirahat sejenak.**

4. Perintah akan muncul setelah Microsoft Graph PowerShell diinstal. Anda sekarang akan menampilkan daftar sub-modul yang diinstal. Untuk melakukannya, jalankan perintah berikut:

        Get-InstalledModule Microsoft.Graph.* | select *name*

5. Verifikasi daftar sub-modul yang diinstal mencakup tiga sub-modul berikut yang akan digunakan dalam latihan lab nanti: 

    - Microsoft.Graph.Groups
    - Microsoft.Graph.Identity.DirectoryManagement
    - Microsoft.Graph.Users
    
    Jika ketiga sub-modul muncul dalam daftar sub-modul yang diinstal, lanjutkan ke langkah berikutnya. Namun, jika salah satu dari tiga sub-modul ini tidak muncul dalam daftar, jalankan perintah PowerShell berikut untuk menginstal sub-modul yang hilang secara manual:

        Install-Module -Name <module name> -Scope CurrentUser

    Misalnya, jika modul Microsoft.Graph.Identity.DirectoryManagement tidak diinstal, maka Anda akan menjalankan perintah berikut:

        Install-Module -Name Microsoft.Graph.Identity.DirectoryManagement

6. Pengaturan kebijakan eksekusi PowerShell menentukan skrip PowerShell apa yang dapat dijalankan pada sistem Windows. Mengatur kebijakan ini ke **Tidak Dibatasi** memungkinkan Holly memuat semua file konfigurasi dan menjalankan semua skrip. Dari baris perintah, ketik perintah berikut, dan tekan Enter:   <br/>

        Set-ExecutionPolicy unrestricted

    Jika Anda diminta untuk memverifikasi bahwa Anda ingin mengubah kebijakan eksekusi, masukkan **A** untuk memilih **[A] Ya untuk Semua.** 

7. Biarkan jendela PowerShell Anda terbuka tetapi minimalkan. Anda akan menggunakannya dalam latihan lab nanti.


**Selamat! Anda telah menyelesaikan semua langkah untuk menginisialisasi penyewa lab Anda. Anda sekarang siap untuk melakukan latihan lab yang tersisa.**

# Akhir Lab 1
