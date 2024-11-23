# Jalur Pembelajaran 2 - Lab 2 - Latihan 1 – Mengelola akses pengguna yang aman 

Organisasi harus memastikan bahwa akses ke data perusahaan mereka di Microsoft 365 selalu aman. Microsoft 365 - dan pada gilirannya, Copilot untuk Microsoft 365 - sering menampilkan data sensitif dan rahasia, termasuk email, dokumen, informasi pelanggan, dan kekayaan intelektual. Akses tidak sah ke Microsoft 365 dapat menyebabkan kebocoran data, pencurian identitas, dan aktivitas berbahaya lainnya. Dengan mengamankan akses pengguna, organisasi dapat mencegah individu yang tidak berwenang mengakses dan berpotensi menyalahgunakan atau membocorkan data perusahaan saat bekerja dengan Microsoft 365 dan Copilot untuk Microsoft 365.

Dalam latihan lab berikut, Anda akan melanjutkan peran Anda sebagai Holly Dickson, Administrator Microsoft 365 baru Adatum. Anda akan melakukan beberapa fungsi manajemen pengguna untuk menyiapkan Adatum untuk penyebaran Copilot untuk Microsoft 365 yang akan datang. Anda akan mulai dengan membuat akun pengguna Microsoft 365 untuk Holly, yang akan diberi peran Administrator Global Microsoft 365. 

**Catatan:** Lingkungan VM yang disediakan oleh penyedia hosting lab Anda dilengkapi dengan lebih dari 20 akun pengguna Microsoft 365 serta sejumlah besar akun pengguna lokal yang sudah ada. Beberapa akun pengguna Microsoft 365 yang sudah ada akan digunakan di seluruh lab dalam kursus ini. Meskipun akun Administrator MOD telah dibuat oleh penyedia hosting lab, Anda masih akan membuat akun pengguna Holly Dickson, karena memiliki lebih dari satu pengguna yang diberikan peran Administrator Global Microsoft 365 adalah praktik terbaik. Ini juga akan memberikan Anda pengalaman membuat akun pengguna Microsoft 365 jika Anda tidak terbiasa dengan prosesnya.

Holly kemudian diminta oleh CTO Adatum untuk menyebarkan Autentikasi Multifaktor Microsoft Entra (MFA) dan Penguncian Cerdas Microsoft Entra. Fitur-fitur ini akan membantu memperkuat manajemen kata sandi di seluruh organisasi sebagai persiapan Copilot untuk Microsoft 365. Untuk Penguncian Cerdas, Anda akan menyebarkannya menggunakan Manajemen Kebijakan Grup. 


### Tugas 1 - Membuat Akun Pengguna untuk Administrator Microsoft 365 Enterprise milik Adatum

Holly Dickson adalah Administrator Microsoft 365 baru Adatum. Karena akun pengguna Microsoft 365 belum disiapkan untuknya, dia awalnya masuk ke Microsoft 365 sebagai akun Administrator MOD (administrator Global default) di lab sebelumnya. Dalam tugas ini, Anda akan terus masuk sebagai Administrator MOD, di mana Anda akan membuat akun pengguna Microsoft 365 untuk Holly. Anda juga akan menetapkan peran Administrator Global Microsoft 365 ke akun Holly. Peran ini akan memberi Holly izin yang diperlukan untuk melakukan semua fungsi administratif dalam Microsoft 365. Setelah tugas ini, Anda akan masuk menggunakan akun baru Holly dan Anda akan melakukan semua lab yang tersisa menggunakan persona Holly. 

**Catatan Lisensi:** Sebelum membuat akun Holly, Anda akan terlebih dahulu memverifikasi jumlah lisensi yang tersedia. Dengan demikian, Anda akan mencatat bahwa meskipun penyewa lab Anda menyediakan 20 lisensi Microsoft 365 E5 (tanpa Teams) dan 20 lisensi Microsoft Teams Enterprise, semua lisensi tersebut telah ditetapkan ke akun pengguna yang sudah ada yang dibuat oleh penyedia hosting lab Anda. Dengan demikian, Anda harus terlebih dahulu menghapus penetapan salah satu dari setiap lisensi dari pengguna yang ada supaya Anda dapat menetapkannya ke Holly.

**Penting:** Sebagai praktik terbaik dalam penerapan Anda di dunia nyata, Anda harus selalu menuliskan kredensial akun administrator Global pertama (di lab ini, ini adalah akun Administrator MOD, dengan nama pengguna admin@xxxxxZZZZZZ.onmicrosoft.com, di mana xxxxxZZZZZZ adalah awalan penyewa yang ditetapkan oleh penyedia hosting lab Anda). Anda harus menyimpan informasi akun ini karena alasan keamanan. **Akun ini harus menjadi identitas NON-personalisasi** yang memiliki hak istimewa tertinggi bagi suatu penyewa. Ini **tidak** boleh diaktifkan MFA karena tidak dipersonalisasi. Karena nama pengguna dan kata sandi untuk akun admin Global pertama ini biasanya dibagikan di antara beberapa pengguna, akun ini adalah target yang sempurna untuk serangan; oleh karena itu, selalu disarankan agar organisasi membuat akun admin layanan yang dipersonalisasi (misalnya, admin Exchange, admin SharePoint, dan sebagainya) dan menyimpan admin Global pribadi sedikit mungkin. Untuk admin Global pribadi yang Anda buat dalam penerapan dunia nyata Anda, mereka masing-masing harus dipetakan ke satu pengguna (seperti Holly Dickson), dan mereka masing-masing harus memberlakukan Autentikasi Multifaktor Microsoft Entra (MFA).

1. Pada VM **LON-CL1**, **pusat admin Microsoft 365** masih harus terbuka di browser Microsoft Edge Anda dari latihan lab sebelumnya. Anda harus masuk ke Microsoft 365 sebagai **Administrator MOD**. 

2. Karena Anda menambahkan pengguna baru, Anda harus mulai dengan memeriksa ketersediaan lisensi sebelum menambahkan akun pengguna. Di panel navigasi **pusat admin Microsoft 365**, pilih **Tagihan** untuk memperluas grup Tagihan, lalu pilih **Lisensi**. 

3. Pada halaman **Lisensi** , tab **Langganan** ditampilkan secara default. Dalam daftar langganan, perhatikan bahwa langganan **Microsoft 365 E5 (tanpa Teams)** dan **Microsoft Teams Enterprise** tidak memiliki lisensi yang tersedia. Penyewa lab Anda menyediakan 20 lisensi untuk setiap langganan, tetapi semua 40 lisensi telah ditetapkan. Karena Anda harus menetapkan lisensi **Microsoft 365 E5 (tanpa Teams)** Holly dan lisensi **Microsoft Teams Enterprise**, Anda harus terlebih dahulu menghapus penetapan lisensi dari akun pengguna yang ada agar tersedia untuk Holly. 

4. Di panel navigasi **pusat admin Microsoft 365**, pilih **Pengguna** lalu pilih **Pengguna aktif**. Dalam daftar **Pengguna aktif**, Anda akan melihat daftar akun pengguna yang sudah ada yang dibuat oleh penyedia hosting lab Anda. Karena Christie Cline akan pindah ke peran baru di perusahaan dan tidak akan lagi menjadi bagian dari proyek pilot Microsoft 365, Anda akan menghapus penetapan lisensi **Microsoft 365 E5 (tanpa Teams)** dan **Microsoft Teams Enterprise** dari akunnya sehingga Anda dapat menetapkannya kembali ke akun baru Holly Dickson.

5. Pada halaman **Pengguna aktif**, dalam daftar pengguna, pilih **Christie Cline** (pilih Nama hyperlink Christie dan bukan kotak centang di samping namanya).

6. Di panel **Christie Cline** yang muncul, tab **Akun** ditampilkan secara default. Pilih tab **Lisensi dan aplikasi** . Di bawah **Lisensi (2)**, pilih kotak centang di samping **Microsoft 365 E5 (tanpa Teams)** dan **Microsoft Teams Enterprise** untuk menghapusnya, lalu pilih **Simpan perubahan**. Setelah perubahan disimpan, tutup panel **Christie Cline** . 

7. Anda sekarang siap untuk membuat akun pengguna untuk Holly Dickson, yang merupakan Administrator Microsoft 365 baru Adatum. Dengan demikian, Anda akan menetapkan peran Administrator Global Microsoft 365 kepada Holly, yang memberi Holly akses global ke sebagian besar fitur dan data manajemen di seluruh layanan online Microsoft. Anda juga akan menetapkan dua lisensi ke Holly yang baru saja Anda batalkan penetapannya dari Christie Cline. <br/>

    Di jendela **Pengguna Aktif**, pilih opsi **Tambahkan pengguna** yang muncul di bilah menu di atas daftar pengguna aktif. Ini akan memulai wizard **Tambahkan pengguna** .

8. Pada halaman **Siapkan dasar-dasar** di wizard **Tambahkan pengguna** masukkan informasi berikut:

    - Nama depan: **Holly**

    - Nama belakang: **Dickson** 

    - Nama tampilan: Saat Anda masuk ke bidang ini, **Holly Dickson** akan muncul.

    - Nama pengguna: **Holly** <br/>
    
        **PENTING:** Di sebelah kanan bidang **Nama pengguna** adalah bidang domain. Ini akan diisi sebelumnya dengan **domain cloud xxxxxZZZZZZ.onmicrosoft.com** (di mana xxxxxZZZZZZ adalah prefiks penyewa yang disediakan oleh penyedia hosting lab Anda).<br/>
    
    - Kosongkan (hapus centang) kotak centang **Buat kata sandi secara otomatis** yang akan menampilkan bidang baru untuk memasukkan kata sandi yang ditentukan administrator.

    - Masukkan Kata Sandi Administratif Baru di bidang **Kata Sandi** yang muncul 

    - Hapus (centang) kotak centang **Wajibkan pengguna ini mengubah kata sandi saat pertama kali masuk**  

9. Pilih **Selanjutnya**. Jika kotak dialog **Simpan kata sandi** muncul di bagian atas layar, pilih **Jangan Pernah**.

10. Pada halaman **Tetapkan lisensi produk** masukkan informasi berikut: <br/>

    - Pilih lokasi: **Amerika Serikat**

    - Lisensi: Di bawah opsi **Tetapkan lisensi produk kepada pengguna** pilih kotak centang **Microsoft 365 E5 (tanpa Teams)** dan **Microsoft Teams Enterprise** 

11. Pilih **Selanjutnya**.

12. Pada halaman **Pengaturan opsional** pilih panah tarik-turun di sebelah kanan **Peran**. 

13. Di bagian **Peran** , pilih opsi **Akses pusat admin** . Dengan memilih opsi ini, peran administrator Microsoft 365 yang paling umum digunakan diaktifkan di bawahnya.  <br/>

    **Catatan:** Semua peran admin akan ditampilkan jika Anda memilih **Tampilkan semua menurut kategori**, yang muncul setelah peran umum terakhir. Untuk Holly, Anda tidak perlu melihat semua peran admin berdasarkan kategori, karena Holly akan diberi peran Administrator Global yang muncul dalam daftar peran yang umum digunakan.

14. Pilih kotak centang **Administrator Global** . <br/>

    **Catatan:** Pesan peringatan akan ditampilkan yang menunjukkan bahwa Adatum sudah memiliki 7 admin Global. Dalam lingkungan normal, ini akan berlebihan dan tidak direkomendasikan. Untuk tujuan lab ini, penyedia hosting lab menetapkan peran Admin global ke Administrator MOD dan enam akun pengguna lainnya, yang bukan sesuatu yang biasanya Anda lihat dalam penyebaran dunia nyata. Namun, untuk tujuan lab ini di lingkungan lab Adatum fiktif Anda, abaikan pesan ini. **Meskipun demikian, pedoman praktik terbaik yang harus Anda ikuti adalah memiliki dari dua hingga empat Administrator Global dalam penyebaran Microsoft 365 dunia nyata Anda.** 

15. Pilih **Selanjutnya**.

16. Pada jendela **Tinjau dan selesai** , tinjau pilihan Anda. Jika ada yang harus diubah, pilih tautan **Edit** yang sesuai dan buat perubahan yang diperlukan. Jika tidak, jika semuanya benar, pilih **Selesaikan penambahan**. 

17. Pada halaman **Holly Dickson ditambahkan ke pengguna aktif** di bawah bagian **Perincian pengguna** pilih opsi **Tampilkan** untuk memverifikasi kata sandi Holly sama dengan **Kata Sandi Administrasi** yang disediakan oleh penyedia hosting lab Anda untuk akun admin penyewa (misalnya, akun Administrator MOD).  <br/>

    **Catatan:** Jika Anda tidak sengaja memasukkan kata sandi yang berbeda, setelah kembali ke halaman **Pengguna Aktif** Anda harus memilih ikon **Setel ulang kata sandi** (ikon kunci yang muncul saat Anda mengarahkan kursor ke akun Holly) untuk mengubah kata sandinya ke nilai yang benar.

18. Pilih **Tutup.**

19. Tetap masuk ke VM Klien 1 (LON-CL1) dengan pusat admin Microsoft 365 terbuka di browser Anda untuk tugas berikutnya.


### Tugas 2 - Perbarui grup proyek pilot Microsoft 365

Setelah menyelesaikan tugas sebelumnya, Anda masih harus masuk ke **Pusat admin Microsoft 365** sebagai akun **Administrator MOD** . Dalam tugas ini, Anda akan mulai mengimplementasikan proyek pilot Microsoft 365 Adatum sebagai Holly Dickson, Administrator Microsoft 365 Adatum yang baru. Oleh karena itu, Anda akan memulai tugas ini dengan keluar dari Microsoft 365 sebagai Administrator MOD dan Anda akan masuk kembali sebagai Holly. 

Dalam tugas sebelumnya, Anda membuat grup Microsoft 365 untuk anggota tim proyek pilot Adatum sehingga Anda dapat membuat tema kustom untuk grup tersebut. Dalam tugas ini, Anda akan menambahkan Holly ke grup ini. 

1. Pada VM LON-CL1, **pusat admin Microsoft 365** masih harus terbuka di browser Microsoft Edge Anda dari tugas sebelumnya. Anda harus masuk ke Microsoft 365 sebagai **Administrator MOD**. <br/>

    Pada tab **pusat admin Microsoft 365** di sudut kanan atas layar, perhatikan bahwa tab tersebut menampilkan nama Administrator MOD dan ikon megafon. Nama ditampilkan karena tema kustom yang Anda buat di latihan lab sebelumnya yang terkait dengan sekelompok pengguna proyek pilot Microsoft 365 yang menyertakan Administrator MOD. Ingatlah hal ini setelah Anda masuk kembali sebagai Holly Dickson. <br/>

    Pilih ikon pengguna atau lingkaran dengan inisial "MA" untuk **Administrator MOD** di sudut kanan atas browser Anda. Di jendela **Administrator MOD** yang muncul, pilih **Keluar.** <br/>
    
    **Penting:** Saat keluar dari satu akun pengguna dan masuk sebagai akun lain, Anda harus menutup semua tab browser Anda kecuali untuk tab **Keluar** . Ini adalah praktik terbaik yang membantu menghindari kebingungan dengan menutup jendela yang terkait dengan pengguna sebelumnya. Setelah Anda keluar dari akun Administrator MOD, luangkan waktu sejenak dan tutup semua tab browser lainnya kecuali tab **Keluar** . 
    
2. Di browser Microsoft Edge Anda, di tab **Keluar**, masukkan URL berikut di bilah alamat untuk masuk kembali ke Microsoft 365: **https://portal.office.com**. 

3. Di jendela **Pilih akun** , hanya akun admin penyewa Administrator MOD (akun admin@xxxxxZZZZZZ.onmicrosoft.com) yang baru saja Anda keluarkan yang muncul. Pilih **Akun AWS lain**. 

4. Di jendela **Masuk**, masukkan **Holly@xxxxxZZZZZZ.onmicrosoft.com**(di mana xxxxxZZZZZZ adalah prefiks penyewa yang diberikan oleh penyedia hosting lab Anda). Pilih **Selanjutnya**.

5. Di jendela **Masukkan kata sandi** , masukkan Kata Sandi Administratif Baru yang Anda tetapkan ke akun Holly lalu pilih **Masuk**. 

6. Jika kotak dialog **Tetap masuk?** muncul, pilih kotak centang **Jangan perlihatkan ini lagi** lalu pilih **Ya.** 

7. Jika kotak dialog **Selamat Datang di Microsoft 365** muncul di tengah layar, tidak ada opsi untuk menutupnya. Sebagai gantinya, di sebelah kanan jendela, pilih ikon panah maju (**>**) dua kali lalu pilih ikon tanda centang untuk menelusuri slide di jendela olahpesan ini. 

8. Jika jendela **Buat dengan Microsoft 365** muncul, pilih **X** di sudut atas jendela untuk menutupnya. 

9. Halaman **Selamat Datang di Microsoft 365** muncul di browser Edge Anda di tab **Beranda | Microsoft 365** . Ini adalah halaman beranda Microsoft 365 Holly. Perhatikan bahwa inisial Holly muncul di sudut kanan atas layar; tetapi nama Holly tidak ditampilkan. Ini karena akun Holly tidak ada pada saat Anda menambahkan pengguna proyek pilot Microsoft 365 ke grup yang terkait dengan tema kustom dalam latihan lab sebelumnya. Karena Holly ingin melihat namanya di bagian atas setiap jendela Microsoft 365 saat masuk ke sistem, dia pertama-tama ingin menambahkan akunnya ke grup pengguna proyek pilot Microsoft 365. <br>

    Di kolom ikon aplikasi yang muncul di panel navigasi di sisi layar, pilih **Admin**. Ini membuka **pusat admin Microsoft 365** di tab browser baru. 

10. Di **Pusat admin Microsoft 365**, pilih **Tim & grup** di panel navigasi, lalu di bawahnya, pilih **Tim & grup yang aktif**. 

11. Pada halaman **Tim dan grup yang aktif** terdapat tab untuk melihat masing-masing jenis grup. Tab **Tim & grup Microsoft 365** ditampilkan secara default. Di tab ini, pilih **proyek pilot M365**.

12. Di panel **proyek pilot M365** yang muncul, tab **Umum** ditampilkan secara default. Pilih tab **Keanggotaan**.

13. Di tab **Keanggotaan** , sub-tab **Pemilik** ditampilkan secara default di panel navigasi yang muncul di sisi panel. Pilih sub-tab **Anggota** yang muncul di bawahnya.

14. Di sub-tab **Keanggotaan**, pilih **+Tambahkan anggota**.

15. Di panel **Tambahkan anggota grup ke proyek pilot M365** yang muncul, pilih di dalam bidang **Cari menurut nama atau alamat email**. Dalam daftar pengguna yang muncul, gulir ke bawah dan pilih **Holly Dickson**. Pilih tombol **Tambahkan (1)**, lalu tutup panel **Tambahkan anggota grup ke proyek pilot M365** setelah Holly ditambahkan ke grup.

16. Tetap masuk ke LON-CL1 dengan **pusat admin Microsoft 365** terbuka di browser Anda untuk tugas berikutnya.


### Tugas 3: Membuat Kebijakan Akses Bersyarat untuk menerapkan MFA

Seperti yang ditunjukkan oleh pelatihan Anda, ada tiga cara untuk menerapkan MFA - dengan kebijakan Akses Bersyarat, dengan default keamanan, dan dengan MFA setiap pengguna lama (tidak disarankan untuk organisasi yang lebih besar). Dalam latihan ini, Anda akan mengaktifkan MFA melalui kebijakan Akses Bersyarat, yang merupakan metode yang direkomendasikan Microsoft. Adatum telah mengarahkan Holly untuk mengaktifkan MFA untuk semua pengguna Microsoft 365-nya - baik internal maupun eksternal. Namun, untuk tujuan menguji implementasi proyek pilot Microsoft 365 Adatum, Holly ingin mengecualikan anggota grup proyek pilot M365 agar tidak harus menggunakan MFA untuk masuk. Setelah proyek pilot selesai, Holly akan memperbarui kebijakan dengan menghapus pengecualian grup ini dari persyaratan MFA. Kebijakan ini juga akan mencakup dua persyaratan lainnya. Ini akan memerlukan MFA untuk semua aplikasi cloud, dan akan memerlukan MFA bahkan jika pengguna masuk dari lokasi tepercaya. 

1. Pada VM LON-CL1, **pusat admin Microsoft 365** masih harus terbuka di browser Microsoft Edge Anda dari tugas sebelumnya. Anda harus masuk ke Microsoft 365 sebagai **Holly Dickson**.
   
2. Dari **pusat admin Microsoft 365**, di bawah bagian **Pusat admin** pada panel navigasi, pilih **Identitas**. Melakukannya akan membuka pusat admin Microsoft Entra di tab browser baru. Jika jendela **Pilih akun** muncul, pilih **akun Holly Dickson**.

3. Di **pusat admin Microsoft Entra**, pilih **Perlindungan** di panel navigasi, lalu pilih **Akses Bersyarat**.

4. Pada Halaman **Akses Bersyarat | Gambaran umum**, pilih **Kebijakan** di panel navigasi tengah.

5. Pada halaman **Akses Bersyarat**, di bar menu di bagian atas halaman, pilih **+Kebijakan baru**.

6. Pada jendela **Kebijakan Akses Bersyarat baru**, masukkan **MFA untuk semua pengguna** Microsoft 365 di bidang **Nama** .

7. Anda akan mulai dengan menentukan persyaratan MFA untuk pengguna. Di grup **Pengguna**, pilih **0 pengguna dan grup yang terpilih**. Melakukannya akan menampilkan dua tab - **Sertakan** dan **Kecualikan**.

8. Pada tab **Sertakan**, pilih **Semua Pengguna**. Perhatikan pesan peringatan yang muncul. Anda akan mengatasi ini pada dua langkah berikutnya.

9. Pilih tab **Kecualikan** . Untuk menghindari penguncian sistem, seperti yang ditunjukkan oleh pesan peringatan sebelumnya, Anda ingin mengecualikan administrator Global Anda - dalam hal ini, Holly. Holly juga ingin mengecualikan anggota grup proyek pilot Microsoft 365 lainnya demi kelancaran saat pengujian. Setelah Microsoft 365 digunakan langsung di Adatum, Holly akan menghapus grup proyek pilot dari daftar Kecualikan dalam kebijakan Akses Bersyarat ini dan hanya mengecualikan dirinya sendiri, Administrator MOD, dan beberapa admin Global lainnya. Namun untuk saat ini, Holly ingin mengecualikan seluruh grup proyek pilot. <br/>

    Untuk melakukannya, pilih kotak centang **Pengguna dan grup**. 

10. Di jendela **Pilih pengguna dan grup yang dikecualikan** yang muncul, Anda ingin memilih grup proyek pilot Microsoft 365. Tab **Semua** ditampilkan secara default. Untuk menemukan grup proyek pilot dengan cepat, pilih tab **Grup** . Dalam daftar grup aktif, pilih kotak centang di samping grup **proyek pilot M365**, lalu pilih tombol **Pilih** di bagian bawah jendela. Kembali ke jendela **Kebijakan Akses Bersyarat Baru**, perhatikan pesan yang muncul di bawah bagian **Pengguna** . 

11. Anda sekarang akan menentukan persyaratan MFA untuk semua aplikasi cloud. Di bagian **Sumber daya target**, pilih **Tidak ada sumber daya target yang dipilih**. Melakukannya akan menampilkan dua tab - **Sertakan** dan **Kecualikan**.

12. Pilih bidang drop-down **Pilih apa yang diterapkan kebijakan ini** untuk melihat berbagai opsi di menu drop-down. Pilih **Aplikasi cloud**. 

13. Di bawah tab **Sertakan**, perhatikan bahwa pengaturan default adalah **Tidak Ada**. Jika Anda tidak mengubah pengaturan ini, maka tidak ada aplikasi cloud yang memerlukan MFA - dan itu termasuk Microsoft 365. Jadi, meskipun jika Anda membuat kebijakan ini dan memilih opsi untuk mewajibkan MFA untuk semua pengguna, tetapi Anda membiarkan pengaturan **Sumber daya Target** ini ke **Tidak Ada**, maka setiap pengguna yang masuk ke Microsoft 365 tidak perlu menggunakan MFA. <br/>

    Di bawah tab **Sertakan**, pilih **Pilih aplikasi**. Melakukannya menampilkan dua bagian - **Edit filter** dan **Pilih**. Di bawah bagian **Pilih** , pilih **Tidak Ada**. 

14. Di panel **Pilih Aplikasi cloud** yang muncul, gulir ke bawah melalui daftar aplikasi untuk melihat semua aplikasi berbeda yang mungkin MFA-nya Anda perlukan. **JANGAN pilih salah satu aplikasinya.** Kami membuat Anda menggulir daftar ini hanya untuk merasakan seberapa terperinci yang bisa Anda dapatkan saat memerlukan MFA jika Anda memutuskan untuk membatasi MFA ke aplikasi tertentu dalam penerapan dunia nyata.  <br/>

    Untuk Adatum, Holly ingin mewajibkan MFA untuk semua aplikasi cloud, yang biasanya merupakan skenario bisnis yang lebih umum daripada memilih aplikasi tertentu. Di bawah tab **Sertakan** , pilih opsi **Semua aplikasi cloud**. Adatum tidak akan mengecualikan aplikasi cloud apa pun dari autentikasi MFA. Anda dapat memilih tab **Kecualikan** jika Anda ingin melihat opsi yang disediakannya. Ini berfungsi pada dasarnya sama dengan tab **Sertakan**. Anda dapat melihat tab ini, tetapi JANGAN pilih aplikasi cloud apa pun untuk dikecualikan. 

15. Terakhir, Anda akan menentukan persyaratan MFA untuk semua lokasi masuk pengguna. Dalam beberapa skenario, organisasi mungkin hanya memerlukan MFA jika pengguna masuk dari lokasi yang tidak tepercaya. Namun, Adatum ingin mewajibkan MFA untuk semua pengguna yang disertakan, terlepas dari lokasi tempat mereka masuk. <br/>

    Di bagian **Kondisi**, pilih **0 kondisi yang terpilih**. Melakukannya akan menampilkan daftar kondisi potensial yang akan diperiksa oleh kebijakan. Untuk latihan lab ini, di bawah kondisi **Lokasi** , pilih **Tidak dikonfigurasi**. Melakukannya menampilkan tombol alih **Konfigurasi** dan dua tab - **Sertakan** dan **Kecualikan**. Kedua tab saat ini dinonaktifkan.

16. Atur tombol alih **Konfigurasi** ke **Ya**, yang akan mengaktifkan dua tab. 

17. Di bawah tab **Sertakan**, verifikasi **Jaringan atau lokasi apa pun** terpilih (pilih jika perlu). Pilih tab **Kecualikan** . Jika organisasi Anda mengenali alamat IP atau rentang alamat tertentu sebagai "tepercaya", Anda dapat mengecualikan persyaratan MFA jika pengguna masuk dari salah satu lokasi tersebut. Namun, Adatum ingin mewajibkan MFA untuk semua upaya masuk pengguna, terlepas dari lokasi mereka. Hal ini akan mencakup login pengguna internal dan eksternal. Verifikasi bahwa opsi **Jaringan dan lokasi yang dipilih** sudah dipilih, lalu di bawah bagian **Pilih**, verifikasi bahwa pilihannya adalah **Tidak Ada**. Dengan tidak menentukan lokasi yang dipilih, pengaturan ini memastikan bahwa tidak ada lokasi yang dikecualikan dari MFA. 

18. Di bawah bagian **Kontrol akses**, di bawah grup **Berikan**, pilih **0 kontrol terpilih**. Melakukannya menampilkan panel **Berikan**.

19. Di panel **Berikan** yang muncul, verifikasi opsi **Berikan akses** terpilih (pilih jika perlu). Perhatikan semua kontrol akses yang tersedia yang dapat diaktifkan dengan kebijakan ini. Kebijakan ini hanya akan memerlukan MFA, jadi pilih **kotak centang Memerlukan autentikasi multifaktor**. Pilih tombol **Pilih** di bagian bawah panel **Berikan**, yang akan menutup panel. 

20. Di bagian bawah jendela **Kebijakan Akses Bersyarat Baru**, di bidang **Aktifkan kebijakan**, pilih **Aktif**.

21. Perhatikan pesan peringatan dan opsi yang muncul di bagian bawah halaman yang memperingatkan Anda untuk tidak mengunci diri sendiri. Pilih opsi **Saya paham bahwa akun saya akan terpengaruh oleh kebijakan ini. Lanjutkan saja.** Bahkan, Holly tidak akan terpengaruh karena dia adalah anggota grup proyek pilot M365 yang dikecualikan dari kebijakan ini.

22. Terakhir, pilih tombol **Buat** untuk membuat kebijakan tersebut.

23. Pada Jendela **Akses Bersyarat | Kebijakan** yang muncul, verifikasi bahwa **MFA untuk semua kebijakan pengguna Microsoft 365** muncul dan **Statusnya** diatur ke **Aktif**.

24. Tetap masuk ke LON-CL1 dengan semua tab browser Microsoft Edge Anda terbuka untuk tugas berikutnya.


### Tugas 4: Menguji MFA untuk pengguna yang disertakan dan dikecualikan

Untuk menguji kebijakan Akses Bersyarat yang baru saja Anda buat, Anda akan keluar dari Microsoft 365 sebagai Holly, lalu Anda akan masuk kembali sebagai Adele Vance. Adele bukan anggota grup proyek pilot M365, jadi Microsoft Entra semestinya mengharuskan dia menggunakan MFA saat masuk. Setelah Anda masuk sebagai Adele dan memverifikasi bahwa MFA berfungsi, Anda akan keluar sebagai Adele dan kemudian masuk kembali sebagai Holly. Karena Holly adalah anggota grup proyek pilot M365 yang dikecualikan dari penggunaan MFA dalam kebijakan Akses Bersyarat, Anda tidak harus menggunakan MFA saat masuk sebagai Holly. Demikian pula, Anda tidak perlu menggunakan MFA saat masuk sebagai berbagai anggota grup proyek pilot M365 di laboratorium yang tersisa dalam kursus ini.

**Penting:** Untuk menerapkan MFA, Anda harus menggunakan ponsel untuk menerima kode verifikasi sehingga Anda dapat memasukkannya ke penyewa Anda sebagai bentuk autentikasi kedua. Jika Anda tidak memiliki telepon, Anda masih dapat menguji kebijakan Akses Bersyarat. Untuk siswa tanpa telepon, ketika Anda masuk sebagai Adele Vance, sistem akan mengharuskan Anda untuk masuk dengan bentuk autentikasi kedua. Pada saat itu, Anda cukup membatalkan upaya masuk Anda dan kemudian masuk kembali sebagai Holly, yang tidak akan memerlukan MFA. Meskipun Anda tidak akan menyelesaikan proses masuk MFA untuk Adele, Anda masih dapat memverifikasi bahwa sistem memaksa Anda untuk menggunakannya saat mencoba masuk.

1. Pada VM LON-CL1, **pusat admin Microsoft 365** masih harus terbuka di browser Microsoft Edge Anda dari tugas sebelumnya. Anda harus masuk ke Microsoft 365 sebagai **Holly Dickson**. Anda akan mulai dengan keluar dari Microsoft 365. Pada tab **pusat admin Microsoft 365**, pilih nama Holly di sudut kanan atas browser Anda. Di jendela **Holly Dickson** yang muncul, pilih **Keluar.** 
    
2. Setelah Anda keluar dari Microsoft 365 sebagai Holly, tutup sesi browser Anda untuk menghapus cache Anda. Lalu pilih ikon **Edge** di taskbar Anda untuk membuka sesi browser baru. Di browser Anda, buka halaman **Beranda Microsoft 365** dengan memasukkan URL berikut di bilah alamat: **https://portal.office.com/** 

3. Di jendela **Pilih akun** yang muncul, pilih **Gunakan akun lain**. 

4. Di jendela **Masuk**, masukkan **AdeleV@xxxxxZZZZZZ.onmicrosoft.com** (di mana xxxxxZZZZZZ adalah prefiks penyewa unik yang diberikan oleh penyedia host lab Anda), lalu pilih **Berikutnya**. Di jendela **Masukkan kata sandi** , masukkan **Kata Sandi Pengguna** yang disediakan oleh penyedia hosting lab Anda dan pilih **Masuk**.

5. Karena MFA diaktifkan untuk semua pengguna kecuali untuk anggota grup proyek pilot M365 (di mana, Adele bukanlah anggota), jendela **Informasi lebih lanjut diperlukan** akan muncul. Pilih **Selanjutnya**. Ini mengembalikan halaman **Microsoft Authenticator**, yang merupakan titik awal untuk masuk dengan MFA. <br/>

    **Penting:** Jika Anda tidak memiliki telepon, maka ini titik terjauh yang bisa Anda lakukan saat mencoba masuk sebagai Adele. Meskipun Anda tidak dapat menyelesaikan upaya masuk, Anda telah memverifikasi bahwa bagian pertama dari kebijakan Akses Bersyarat Anda berfungsi, karena mengharuskan Adele untuk masuk menggunakan MFA. Pada titik ini, lewati ke langkah #18 sehingga Anda dapat masuk kembali sebagai Holly.

6. Pada halaman **Microsoft Authenticator** yang muncul, Anda dapat mengunduh aplikasi seluler ini atau menggunakan metode yang berbeda untuk verifikasi MFA. Untuk keperluan lab ini, kami sarankan Anda menggunakan ponsel sehingga Anda tidak perlu meluangkan waktu untuk menginstal aplikasi Microsoft Authenticator yang mungkin tidak akan Anda gunakan lagi setelah kelas pelatihan ini. Pilih opsi **Saya ingin menyiapkan metode yang berbeda** di bagian bawah halaman (**Penting:** JANGAN tertukar antara tautan ini dengan **saya ingin menggunakan aplikasi autentikasi lain** yang muncul di atasnya). 

7. Dalam kotak dialog **Pilih metode lain** yang muncul, pilih panah drop-down di bidang **Metode mana yang ingin Anda gunakan?**, pilih **Telepon**, lalu pilih **Konfirmasi**. 

8. Di jendela **Telepon** yang muncul, di bawah bidang **Nomor telepon apa yang ingin Anda gunakan?**, pilih negara atau wilayah Anda, lalu di bidang di sampingnya, masukkan nomor telepon Anda (dalam format **nnn-nnn-nnnn**). Verifikasi opsi **Terima kode** terpilih lalu pilih **Berikutnya**.

9. Ambil kode verifikasi dari pesan teks yang dikirim ke ponsel Anda.

10. Di jendela **Telepon**, masukkan kode verifikasi 6 digit di bidang kode lalu pilih **Berikutnya**. Saat jendela **Telepon** menampilkan pesan yang menunjukkan ponsel Anda berhasil didaftarkan, pilih **Berikutnya**.

11. Pada halaman **Sukses!** , pilih **Selesai**.

12. Microsoft telah menerapkan kebijakan keamanan baru di penyewa uji coba yang digunakan di lab pelatihannya. Semua akun pengguna uji coba yang telah ditentukan sebelumnya dikonfigurasi sehingga siswa harus mengubah kata sandi awal mereka pada rincian masuk berikutnya. Anda mengalami ini sebelumnya saat masuk ke Microsoft 365 sebagai Administrator MOD di latihan lab pertama. Anda harus melakukannya sekarang dengan Adele. <br>

    Di jendela **Perbarui kata sandi** Anda yang muncul, masukkan **Kata Sandi** Pengguna yang disediakan oleh penyedia hosting lab Anda di bidang **Kata sandi saat ini**. Kemudian di bidang **Kata sandi baru** dan **Konfirmasi kata sandi**, masukkan Kata Sandi Pengguna Baru yang Anda tentukan untuk semua pengguna uji coba di awal lab. Pilih **Masuk**.

13. Jika kotak dialog **Tetap masuk?** muncul, pilih kotak centang **Jangan perlihatkan ini lagi** lalu pilih **Ya.** 

14. Jika kotak dialog **Selamat Datang di Microsoft 365** muncul, pilih panah kanan dua kali lalu pilih tanda centang.

15. Jika jendela **Buat dengan Microsoft 365** muncul, pilih **X** untuk menutupnya.

16. Pada halaman **Selamat Datang di Microsoft 365** , pilih ikon **Word** yang muncul di kolom ikon aplikasi di sisi kiri layar. Ini akan membuka **Microsoft Word Online**. Melakukannya memvalidasi bahwa Anda dapat mengakses aplikasi Microsoft 365 setelah masuk menggunakan MFA.  <br/>

    **Penting:** Anda sekarang telah memverifikasi bahwa bagian pertama dari kebijakan Akses Bersyarat yang Anda buat berfungsi. Kebijakan ini mengharuskan pengguna yang bukan anggota tim proyek pilot Microsoft 365 harus masuk menggunakan MFA. Anda memverifikasi bahwa ini berfungsi saat Anda masuk sebagai Adele. Anda sekarang akan keluar sebagai Adele dan masuk kembali sebagai Holly, di mana Anda akan memverifikasi bahwa bagian kedua dari kebijakan Akses Bersyarat juga berfungsi. Anda TIDAK perlu menggunakan MFA saat masuk sebagai Holly, karena dia adalah anggota grup proyek pilot M365, yang dikecualikan dari persyaratan MFA dalam kebijakan Akses Bersyarat.

17. Pada tab **pusat admin Microsoft 365**, pilih ikon untuk akun Adele di sudut kanan atas browser Anda. Di jendela **Adele Vance** yang muncul, pilih **Keluar.** <br/>
    
18. Tutup sesi browser Anda untuk menghapus cache Anda. Pilih ikon **Edge** di taskbar Anda untuk membuka sesi browser baru. Di browser Anda, buka halaman **Beranda Microsoft 365** dengan memasukkan URL berikut di bilah alamat: **https://portal.office.com/** 

19. Di jendela **Pilih akun**, pilih **Holly@xxxxxZZZZZZ.onmicrosoft.com**(di mana xxxxxZZZZZZ adalah awalan penyewa yang disediakan oleh penyedia hosting lab Anda) lalu pilih **Berikutnya**. Di jendela **Masukkan kata sandi** , masukkan Kata Sandi Administratif baru yang Anda tentukan untuk semua pengguna uji coba di awal lab dan kemudian ditetapkan ke akun Holly. Pilih **Masuk**.

20. Karena MFA diperlukan untuk semua pengguna kecuali untuk anggota tim proyek pilot M365 (di mana, Holly adalah anggota), MFA tidak akan diperlukan. Karena MFA tidak diperlukan, sistem menampilkan halaman **Beranda Microsoft 365** di tab **Beranda | Microsoft 365** . 

21. Jika kotak dialog **Selamat Datang di Microsoft 365** muncul, pilih panah kanan dua kali lalu pilih tanda centang.

22. Jika jendela **Buat dengan Microsoft 365** muncul, pilih **X** untuk menutupnya.

23. Pada halaman **Selamat Datang di Microsoft 365**, pilih ikon **Admin** di panel samping untuk menavigasi ke **pusat admin Microsoft 365**. <br/>

    **Penting:** Anda sekarang telah memverifikasi bahwa bagian kedua dari kebijakan Akses Bersyarat yang Anda buat berfungsi. Kebijakan ini mengecualikan anggota grup proyek pilot Microsoft 365 agar tidak masuk menggunakan MFA. Holly adalah anggota grup ini, dan dia tidak perlu masuk menggunakan MFA.

24. Tetap masuk ke LON-CL1 dengan **pusat admin Microsoft 365** terbuka di browser Anda.


### Tugas 5: Mengerahkan Penguncian Cerdas Microsoft Entra

CTO Adatum telah meminta Anda untuk menerapkan Microsoft Entra Smart Lockout, yang membantu mengunci aktor jahat yang mencoba menebak kata sandi pengguna Anda atau menggunakan metode brute-force untuk masuk ke jaringan Anda. Penguncian Cerdas dapat mengenali aktivitas masuk yang berasal dari pengguna yang valid dan memperlakukan mereka secara berbeda dari penyerang dan sumber lain yang tidak diketahui. 

CTO ingin menerapkan Penguncian Cerdas karena akan mengunci penyerang sambil membiarkan pengguna Adatum terus mengakses akun mereka dan menjadi produktif. CTO telah meminta Holly untuk mengonfigurasi Smart Lockout sehingga pengguna tidak dapat menggunakan kata sandi yang sama lebih dari sekali, dan mereka tidak dapat menggunakan kata sandi yang dianggap terlalu sederhana atau umum. 

**Catatan:** Anda dapat mempertahankan pengaturan Kebijakan Penguncian Akun di Editor Manajemen Kebijakan Grup dan di Microsoft Entra melalui fitur Penguncian Cerdasnya. Tugas lab ini menunjukkan kepada Anda cara mengakses setiap metode, meskipun Anda hanya akan memperbarui pengaturan Penguncian Cerdas di Microsoft Entra saja. Anda harus menggunakan pengendali domain perusahaan (LON-DC1) untuk mengakses Editor Manajemen Kebijakan Grup. 

1. Dalam tugas sebelumnya, Anda bekerja di LON-CL1. Dalam tugas ini, Anda akan bekerja dari pengendali domain Adatum, LON-DC1. <br/>

    Beralih ke **LON-DC1**.

2. Pada **LON-DC1**, Anda harus memilih **Ctrl+Alt+Delete** untuk masuk (instruktur Anda akan memandu Anda tentang cara menemukan opsi ini di lingkungan VM Anda). Masuk ke LON-DC1 sebagai akun administrator Adatum lokal yang dibuat oleh penyedia hosting lab (**Administrator**) Anda dengan kata sandi **Pa55w.rd**.

3. Pada LON-DC1, **Manajer Server** mulai secara otomatis saat boot-up. Di **Manajer Server**, pilih **Alat** di bilah menu kanan atas, dan di menu drop-down, pilih **Manajemen Kebijakan Grup.** Maksimalkan jendela **Manajemen Kebijakan Grup** yang muncul.

4. Anda ingin mengedit kebijakan grup yang menyertakan kebijakan penguncian akun organisasi Anda. Jika perlu, di pohon konsol akar di panel samping, perluas **Forest:Adatum.com**, lalu perluas **Domain**, lalu perluas **Adatum.com**.  <br/>

    Di bawah **Adatum.com**, klik kanan **Kebijakan Domain Default** lalu pilih **Edit** di menu.

5. Maksimalkan jendela **Editor Manajemen Kebijakan Grup** yang muncul.

6. Di pohon **Kebijakan Domain Default** di panel samping, di bawah **Konfigurasi Komputer**, perluas **Kebijakan**, perluas **Pengaturan Windows**, perluas **Pengaturan Keamanan**, lalu perluas **Kebijakan Akun.**

7. Pada folder **Kebijakan Akun** pilih **Kebijakan Penguncian Akun**.

8. Seperti yang Anda lihat di panel yang muncul, tidak ada parameter penguncian cerdas yang telah ditentukan. Alih-alih mempertahankan parameter penguncian ini di Editor Manajemen Kebijakan Grup, Anda akan menggunakan pusat admin Microsoft Entra. Meskipun Anda dapat menggunakan Editor Manajemen Kebijakan Grup, metode ini biasanya digunakan di lingkungan Active Directory lokal. Kami menunjukkan kepada Anda editor ini sehingga Anda dapat melihat alternatif ini. Namun, untuk organisasi yang secara ketat menggunakan layanan berbasis cloud seperti Microsoft 365, atau yang merasa bahwa menggunakan pusat admin Microsoft Entra jauh lebih mudah digunakan daripada mengakses Editor Manajemen Kebijakan Grup, menggunakan **Pusat admin Microsoft Entra** untuk menetapkan nilai yang sesuai dalam konteks ID Entra lebih disukai. <br/>  

    Perlu diingat juga bahwa perilaku penguncian dan opsi penyesuaian berbeda antara kedua metode. Dengan Editor Manajemen Kebijakan Grup, Anda memiliki kontrol yang lebih terperinci atas pengaturan kebijakan, termasuk Ambang Penguncian Akun, Durasi Penguncian, dan Atur Ulang Penghitung Penguncian Akun Setelahnya. Namun, menggunakan metode ini memerlukan keakraban dengan Kebijakan Grup dan administrasi Direktori Aktif. Sebaliknya, Kebijakan Penguncian Akun di Microsoft Entra tidak dapat disesuaikan secara ekstensif. Namun, lebih mudah digunakan, meskipun tidak memiliki beberapa opsi penyempurnaan yang tersedia dalam Kebijakan Grup. <br/>

    Untuk Adatum, Holly telah memilih untuk menggunakan pusat admin Microsoft Entra untuk mengonfigurasi kebijakan Penguncian Akun perusahaan. Pada bilah tugas di bagian bawah layar Anda, pilih ikon **Microsoft Edge** . Jika perlu, maksimalkan jendela browser Anda saat terbuka.

9. Di browser Edge Anda, buka halaman **Beranda Microsoft 365** dengan memasukkan URL berikut di bilah alamat: **https://portal.office.com** 

10. Dalam kotak dialog **Masuk** , Anda harus masuk sebagai Holly Dickson. Masukkan **Holly@xxxxxZZZZZZ.onmicrosoft.com**, di mana xxxxxZZZZ ADALAH prefiks penyewa yang ditetapkan oleh penyedia hosting lab Anda. Pilih **Selanjutnya**. <br/>

11. Dalam kotak dialog **Masukkan kata sandi** , masukkan Kata Sandi Administratif Baru yang Anda tetapkan ke akun Holly lalu pilih **Masuk**. 

12. Pada kotak dialog **Tetap masuk?** , pilih kotak centang **Jangan perlihatkan ini lagi** lalu pilih **Ya.** Pada kotak dialog **Simpan kata sandi** yang muncul, pilih **Jangan Pernah**.

13. Jika kotak dialog **Selamat Datang di Microsoft 365** muncul di tengah layar, tidak ada opsi untuk menutupnya. Sebagai gantinya, di sebelah kanan jendela, pilih ikon panah maju (**>**) dua kali lalu pilih ikon tanda centang untuk menelusuri slide di jendela olahpesan ini. 

14. Jika jendela **Temukan lebih banyak aplikasi** atau jendela **Buat dengan Microsoft 365** muncul, pilih **X** di sudut paling atas jendela untuk menutupnya. 

15. Pada halaman **Selamat Datang di Microsoft 365** dalam daftar ikon aplikasi yang muncul di panel jendela samping, pilih **Admin**; ini membuka **pusat admin Microsoft 365** di tab browser baru. 

16. Pada **Pusat admin Microsoft 365**, pilih **Tampilkan semua** di panel navigasi. Di bawah **Pusat admin**, pilih **Identitas**, yang akan menampilkan **Pusat admin Microsoft Entra** di tab baru.

17. Pada **Pusat admin Microsoft Entra**, pilih **Proteksi** pada panel navigasi, lalu pilih **Metode autentikasi**.

18. Dalam **metode Autentikasi |Halaman Kebijakan** di panel tengah di bawah bagian **Kelola** pilih **Perlindungan kata sandi.**

19. Pada jendela **Metode autentikasi| Proteksi kata sandi** pada panel detail di sebelah kanan, masukkan informasi berikut:

    - Pada bagian **Penguncian cerdas kustom** :

        - **Ambang batas penguncian:** bidang ini menunjukkan berapa kali gagal masuk yang diizinkan pada akun sebelum penguncian pertama. Nilai default adalah 10. Untuk tujuan pengujian, Adatum telah meminta Anda mengatur ini ke **3**.

        - **Durasi penguncian dalam detik:** Ini adalah durasi dalam detik dari setiap penguncian. Durasi defaultnya adalah 60 detik (satu menit). Adatum memintamu mengubahnya menjadi **90** detik.

    - Di bagian **Kata sandi yang dilarang** :

        - **Terapkan daftar kustom**: pilih **Ya**

        - **Daftar kata sandi terlarang kustom:** Masukkan nilai berikut (tekan Enter setelah memasukkan setiap nilai sehingga setiap nilai berada di baris terpisah):

            - **Kata sandi01**

            - **F00tball01**

            - **Se@Hawks1**

            - **Never4get!!**

    - Di bagian **Mode** , pilih **Diberlakukan**

20. Pilih ikon **Simpan** di bagian atas halaman.

21. Anda sekarang harus menguji fungsionalitas kata sandi yang dilarang. Pilih ikon pengguna Holly Dickson di sudut kanan atas layar, dan di menu yang muncul pilih **Tampilkan akun**. 

22. Pada jendela **Akun saya** yang muncul, pada petak **Kata Sandi**, pilih **UBAH KATA SANDI**.

23. Tab baru akan terbuka menampilkan jendela **Ubah kata sandi** . Pada bidang **Kata sandi lama** masukkan kata sandi Holly yang sudah ada, yaitu Kata Sandi Administratif Baru. <br/>

    Masukkan **Never4get!!** di bidang **Buat kata sandi baru** dan **Konfirmasi kata sandi baru** lalu pilih **Kirim**. Pilih pesan kesalahan yang Anda terima.

24. Di browser Anda, tutup tab **Ubah kata sandi** . 

25. Anda sekarang akan menguji fungsionalitas ambang penguncian. Kau akan melakukannya menggunakan akun Patti Fernandez. Pilih ikon pengguna Holly Dickson di sudut kanan atas layar, dan di menu yang muncul pilih **Keluar**.  

26. Setelah Anda keluar sebagai Holly, jendela **Pilih akun** akan muncul di tab **Masuk ke Microsoft Entra** Sebagai praktik terbaik saat keluar dari layanan online Microsoft sebagai satu pengguna dan masuk kembali sebagai pengguna lain, tutup semua tab browser Anda kecuali tab **Keluar** atau **Masuk** Dalam kasus ini, tutup tab lain sekarang dan biarkan tab **Masuk** terbuka.  <br/>

    Di jendela **Pilih akun** , pilih **Gunakan akun lain**. 

27. Pada jendela **Masuk** masukkan **pattif@xxxxxZZZZZZ.onmicrosoft.com** (di mana xxxxxZZZZZZ adalah prefiks penyewa yang diberikan kepada Anda oleh penyedia hosting lab Anda), lalu pilih **Berikutnya**. 

28. Pada jendela **Masukkan kata sandi** , masukkan campuran acak huruf dan angka lalu pilih **Masuk**. Perhatikan pesan kesalahan kata sandi yang tidak valid yang muncul. 

    Ulangi langkah ini 2 kali lagi. 
    
    Karena Anda mengatur **ambang batas Penguncian** ke **3**, Anda akan menerima pesan kesalahan yang menunjukkan bahwa akun ini dikunci setelah upaya masuk ketiga yang gagal. <br/>

    **Catatan:** Jika Anda tidak menerima pesan penguncian ini setelah upaya ketiga, maka sistem belum selesai menyebarluaskan perubahan ambang batas penguncian ini di seluruh layanan. Diperlukan waktu beberapa menit agar aturan diterapkan. Tunggu beberapa menit lalu masuk lagi dengan kata sandi palsu. Pengujian lab ini telah melihat berbagai hasil. Perubahan terkadang segera disebarluaskan sehingga Anda terkunci setelah upaya masuk ketiga. Lain kali telah diambil dari 5 hingga 10 menit sebelum pesan penguncian ditampilkan. Lanjutkan proses ini hingga Anda menerima pesan penguncian, di mana akun Patti akan dikunci sementara untuk mencegah akses yang tidak sah.

29. Anda akan dilarang masuk lagi sebagai Patti sampai setelah **durasi penguncian 90 detik** yang Anda tetapkan sebelumnya. <br/>

    Setelah Anda terkunci, tunggu 90 detik, lalu masuk kembali sebagai **pattif@xxxxxZZZZZZ.onmicrosoft.com** (di mana xxxxxZZZZZZ adalah prefiks penyewa yang diberikan kepada Anda oleh penyedia hosting lab Anda). Pada bidang **Kata sandi** masukkan kata sandi Patti, yaitu **Kata Sandi Pengguna** yang disediakan oleh penyedia hosting lab Anda. 
 
30. Seingat Anda, semua akun pengguna uji coba yang telah ditentukan sebelumnya di penyewa uji coba Anda dikonfigurasi sehingga Anda harus mengubah kata sandi awal mereka pada rincian masuk berikutnya. Saat jendela **Perbarui kata sandi** Anda muncul, verifikasi bahwa upaya masuk Anda menggunakan kata sandi aktual Patti berhasil. <br>

    **Catatan:** Anda TIDAK perlu menyelesaikan proses masuk untuk Patti, karena ini adalah latihan lab terakhir Anda menggunakan pengendali domain LON-DC1. Anda dapat menutup semua aplikasi di LON-DC1.
 
# Lanjutkan ke Lab 2 - Latihan 2
