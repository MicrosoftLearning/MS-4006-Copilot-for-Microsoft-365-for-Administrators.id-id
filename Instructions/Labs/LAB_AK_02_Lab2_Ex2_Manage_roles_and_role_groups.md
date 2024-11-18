# Jalur Pembelajaran 2 – Lab 2 - Latihan 2 - Mengelola peran dan grup peran

Dalam latihan ini, Anda akan melanjutkan peran Anda sebagai Holly Dickson, Administrator Microsoft 365 Adatum yang baru. Sebagai bagian dari proyek pilot Microsoft 365 Adatum, Anda akan mengelola delegasi administrasi dengan menetapkan peran administrator Microsoft 365 ke beberapa akun pengguna Microsoft 365 yang dibuat oleh penyedia hosting lab Anda. Latihan ini akan memberikan Anda pengalaman dalam menggunakan tiga metode berbeda untuk menetapkan peran ini: 1) dengan menetapkan peran langsung ke akun pengguna di pusat admin Microsoft 365, 2) dengan membuat grup peran, menetapkan peran ke grup peran, lalu menetapkan grup peran kepada pengguna di pusat admin Microsoft 365, dan 3) dengan menetapkan peran kepada pengguna menggunakan Windows PowerShell. Setelah menetapkan peran admin Microsoft 365 ke beberapa akun pengguna yang ada, Anda kemudian akan menguji tugas-tugas tersebut dengan memverifikasi bahwa para pengguna memiliki izin untuk bertindak sesuai dengan peran mereka. 


### Tugas 1 - Menetapkan peran administrator di Pusat Admin Microsoft 365

Holly Dickson telah diberi peran Administrator Global Microsoft 365. Saat Anda melanjutkan peran Anda sebagai Holly, Anda akan menggunakan pusat admin Microsoft 365 untuk menetapkan hak administrator kepada salah satu pengguna Adatum. Dalam tugas ini, Anda akan menetapkan peran Administrator Penagihan ke akun pengguna Diego Siciliani.

1. Anda menyelesaikan latihan lab sebelumnya yang mengerjakan LON-DC1. Anda sekarang harus beralih kembali ke **LON-CL1** untuk melakukan tugas administratif Microsoft 365 dalam latihan lab ini. Sebagai praktik terbaik, tugas administratif Microsoft 365 biasanya harus dilakukan pada PC klien dan bukan pada pengendali domain perusahaan.  <br/>

    Beralih ke **LON-CL1**. 

2. Pada **LON-CL1**, di **pusat admin Microsoft 365** di browser Edge Anda, Anda masih harus masuk sebagai Holly Dickson dari latihan lab sebelumnya. Di panel navigasi, pilih **Pengguna** lalu pilih **Pengguna Aktif**. 

3. Di daftar **Pengguna aktif**, pilih **Diego Siciliani**.  <br/>

    **Catatan:** Pilih nama Diego; jangan pilih kotak centang di sebelah kiri namanya. Kotak centang biasanya digunakan untuk memilih beberapa pengguna saat Anda ingin melakukan salah satu tindakan terkait pengguna pada bilah menu yang muncul di atas daftar pengguna, seperti **Mengelola lisensi produk** dan **Mengelola peran**. Memilih nama pengguna akan membuka panel properti khusus untuk pengguna tersebut.

4. Di panel **Diego Siciliani** yang muncul, tab **Akun** ditampilkan secara default. Di tab ini, gulir ke bawah ke bagian **Peran** dan pilih **Kelola peran**. 

5. Di jendela **Kelola peran admin**, opsi **Pengguna (tanpa akses pusat admin)** saat ini dipilih secara default. Sekarang setelah Anda ingin menetapkan peran administrator Diego, pilih opsi **Akses pusat admin**. Ini memungkinkan daftar peran admin yang umum digunakan untuk menjadi pilihan. 

6. Diego telah dipromosikan ke Administrator Penagihan, tetapi karena peran ini tidak muncul dalam daftar peran yang umum digunakan, gulir ke bawah dan pilih **Tampilkan semua menurut kategori**. 

7. Dalam daftar peran yang diurutkan menurut kategori, gulir ke bawah ke kategori **Lainnya** , pilih kotak centang **Administrator Penagihan**, lalu pilih **Simpan perubahan**. <br/>

    **Tips:** Perhatikan pesan yang muncul di bagian atas panel setelah perubahan peran admin disimpan. Pesan ini memberikan praktik terbaik berikut yang harus Anda ingat saat Anda mempertahankan peran administratif dalam penyebaran dunia nyata Anda: **Berikan pengguna hanya akses yang mereka butuhkan dengan menetapkan peran yang paling tidak permisif.**

8. Pada jendela **Kelola peran admin**, pilih **X** di sudut kanan atas layar untuk menutupnya. Ini mengembalikan Anda ke daftar **Pengguna aktif**. 

9. Tetap masuk ke LON-CL1 dan pusat admin Microsoft 365 sebagai Holly Dickson.

### Tugas 2 - Menetapkan peran administrator menggunakan grup peran di pusat admin Microsoft 365

Dalam tugas sebelumnya, Anda menetapkan peran administrator langsung ke akun pengguna Diego Siciliani di pusat admin Microsoft 365. Dalam tugas ini, Anda akan menetapkan peran menggunakan grup peran sebagai gantinya. Anda akan membuat grup peran Keamanan, menetapkan peran manajemen pengguna ke grup tersebut, lalu menetapkan grup peran ke akun pengguna Lynne Robbin di pusat admin Microsoft 365.

1. Di LON-CL1, Anda tetap harus masuk ke pusat admin Microsoft 365 sebagai Holly Dickson. Jika belum, lakukan sekarang.

2. Di **pusat admin Microsoft 365**, pilih **Teams & grup** di panel navigasi, lalu pilih **Tim & grup aktif**. 

3. **Pada halaman Tim & grup** aktif, tab **Teams & Grup Microsoft 365** ditampilkan secara default. Pilih tab **Grup keamanan**.

4. Pada tab **Grup keamanan**, pilih **+Tambahkan grup keamanan** pada bilah menu. Melakukannya memulai wizard **Tambahkan grup keamanan**.

5. Di wizard **Tambahkan grup keamanan**, pada halaman **Atur dasar**, masukkan **Grup peran manajemen pengguna** di bidang **Nama**. Masukkan **Grup peran ini berisi peran manajemen pengguna** di bidang **Deskripsi** . Pilih **Selanjutnya**.

6. Pada halaman **Edit pengaturan** , pilih kotak centang **Peran Azure AD dapat ditetapkan ke grup**, lalu pilih **Berikutnya**.

7. Pada halaman **Tinjau dan selesaikan penambahan grup**, tinjau pengaturannya. Jika ada pengaturan yang perlu diubah, pilih opsi **Edit** yang sesuai dan buat perubahan. Jika semua pengaturan sudah benar, pilih **Buat grup**.

8. Setelah grup **Peran manajemen pengguna** dibuat, pilih **Tutup**.

9. Sekarang setelah Anda membuat grup peran, Anda harus menetapkan peran yang sesuai untuknya. Pada halaman **Tim aktif dan grup** , tab **Grup keamanan** ditampilkan. Pilih grup **Peran manajemen pengguna** untuk membuka panel detailnya.

10. Pada panel **Grup peran manajemen pengguna**, tab **Umum** ditampilkan secara default. Di bawah bagian **Peran** , pilih **Kelola peran**.

11. Pada panel **Kelola peran admin** yang muncul, pilih opsi **Akses pusat admin**. Dalam daftar peran administrator umum yang muncul tepat di bawah opsi ini, pilih kotak centang **Administrator Pengguna** dan **Manajer Keberhasilan Pengalaman Pengguna**. Lalu pilih opsi **Perlihatkan semua menurut kategori**. Gulir ke bawah ke kategori **Identitas**. Perhatikan bagaimana peran **Administrator Pengguna** sudah terpilih, karena Anda memilih ini sebelumnya dalam daftar peran yang umum digunakan. Dalam kategori **Identitas** ini, pilih peran **Administrator Helpdesk** lalu pilih **Simpan perubahan**. 

12. Di panel **Kelola peran admin**, tiga peran yang dipilih akan muncul di bawah opsi **Akses pusat admin**. Pilih **X** di sudut kanan atas panel untuk menutupnya.

13. Di bawah tab **Grup keamanan**, pilih **Grup peran manajemen pengguna**. Di panel **Grup peran manajemen pengguna** yang muncul, verifikasi tiga peran yang muncul di bagian **Peran** . Tutup panel ini.

14. Setelah menetapkan peran ke grup peran, Anda harus menetapkan grup peran ke akun pengguna Lynne Robbin. Di **pusat admin Microsoft 365**, pilih **Pengguna Aktif**.

15. Pada halaman **Pengguna aktif**, pilih **Lynne Robbins**. 

16. Di panel **Lynne Robbins** yang muncul, tab **Akun** ditampilkan secara default. Dalam tugas sebelumnya, saat Anda menetapkan peran Administrator Penagihan ke akun Diego Siciliani, Anda memilih opsi **Kelola peran** di bawah bagian **Peran** . Namun, karena Anda akan menetapkan peran Lynne melalui grup peran, Anda harus menetapkan Lynne sebagai anggota grup peran Keamanan yang baru saja Anda buat. Melalui penugasan grup, Lynne baru akan mewarisi peran yang ditetapkan ke grup peran. Oleh karena itu, di bawah bagian **Grup**, pilih **Kelola grup**. 

17. Pada panel **Kelola grup** , pilih **+Tetapkan keanggotaan**.

18. Pada panel **Tetapkan keanggotaan** , pilih kotak centang **Grup peran manajemen pengguna**, lalu pilih **Tambahkan(1)**.

19. Setelah pemberitahuan **Tersimpan** muncul di bagian atas halaman, tutup panel ini. 

20. Untuk memverifikasi bahwa Lynne mewarisi peran yang ditetapkan ke grup peran manajemen Pengguna, pilih **Lynne Robbins** dari daftar pengguna aktif. 

21. Di panel **Lynne Robbins** yang muncul, di tab **Akun** yang ditampilkan secara default, Anda akan melihat tiga peran Manajemen pengguna yang ditetapkan ke Lynne. Di bawah bagian **Peran** , pilih **Kelola peran**.

22. Di panel **Kelola peran admin** yang muncul, di bawah opsi **Akses pusat admin**, perhatikan tiga peran yang dipilih dan nama grup tempat peran tersebut ditetapkan ke Lynne. Perhatikan juga bagaimana ketiga peran tersebut berwarna abu-abu. Ini menunjukkan bahwa Anda tidak dapat membatalkan peran dari jendela ini. Karena peran ditetapkan ke Lynne dari grup peran yang berisi peran ini, Anda hanya dapat menghapus penetapan peran dengan menghapus Lynne sebagai anggota grup peran. Anda baru saja memverifikasi bahwa Lynne diberi peran ini. Tutup panel **Kelola peran admin** ini.

23. Tetap masuk ke LON-CL1 dan pusat admin Microsoft 365 sebagai Holly Dickson.

### Tugas 3 - Menetapkan peran administrator menggunakan Windows PowerShell  

Dalam tugas ini, Anda akan menggunakan Windows PowerShell untuk menetapkan peran ke akun pengguna. Melakukannya akan memberi Anda pengalaman melakukan fungsi manajemen ini di PowerShell, karena beberapa administrator lebih suka melakukan pemeliharaan seperti ini menggunakan PowerShell.  

Dalam tugas ini, Holly ingin menetapkan Patti Fernandez ke peran Administrator Dukungan Layanan. Untuk menambahkan pengguna ke peran admin menggunakan modul Microsoft Graph PowerShell, Anda harus terlebih dahulu mendapatkan ID objek pengguna dan ID objek peran tersebut. Jika peran belum diaktifkan (artinya belum ditetapkan ke pengguna atau belum diaktifkan secara fisik), maka Anda harus mengaktifkan peran terlebih dahulu sebelum dapat menetapkannya kepada pengguna menggunakan PowerShell. Dalam tugas ini, Anda akan mengaktifkan peran Administrator Dukungan Layanan terlebih dahulu sebelum menetapkannya ke Patti Fernandez.

PowerShell juga memungkinkan Anda menampilkan semua pengguna yang ditetapkan ke peran tertentu, yang bisa menjadi sangat penting saat mengaudit penyebaran Microsoft 365 Anda. Dalam tugas ini, Anda juga akan mempelajari cara menggunakan PowerShell untuk menampilkan semua pengguna yang ditetapkan ke peran tertentu. 

1. Pada LON-CL1, pilih ikon Windows PowerShell pada taskbar yang Anda biarkan terbuka dari lab sebelumnya. Jika Anda telah menutup jendela PowerShell, buka instans yang ditingkatkan menggunakan instruksi yang sama seperti sebelumnya. 

2. Sesi PowerShell Anda masih harus tersambung ke Microsoft Graph PowerShell dari lab sebelumnya tempat Anda memulihkan grup yang dihapus menggunakan PowerShell. Namun, jika sebelumnya Anda menutup PowerShell dan baru saja membukanya kembali, maka impor sub-modul Microsoft.Graph.Identity.DirectoryManagement menggunakan langkah-langkah dari latihan lab sebelumnya. 

3. Untuk melakukan tugas pemeliharaan pengguna Microsoft 365 di Microsoft Graph PowerShell, Anda harus terlebih dahulu mengimpor sub-modul Microsoft.Graph.Users dan meminta izin Baca/Tulis. Untuk mengimpor sub-modul ini, ketik perintah berikut pada prompt perintah lalu tekan Enter:   <br/>

        Import-Module Microsoft.Graph.Users

4. Dalam latihan lab sebelumnya, Anda tersambung ke Microsoft Graph dan meminta izin "Directory.ReadWrite.All" untuk menjalankan cmdlet yang memulihkan grup yang dihapus. Untuk memperbarui objek Pengguna dan peran dalam tugas ini, Holly sekarang harus meminta izin Baca/Tulis untuk setiap objek. Untuk meminta izin ini, ketik perintah berikut pada prompt perintah lalu tekan Enter:  <br/>

        Connect-MgGraph -Scopes 'User.ReadWrite.All', 'RoleManagement.ReadWrite.Directory'

5. Di jendela **Pilih akun** yang muncul, pilih akun Holly Dickson. 

6. Pada kotak dialog **Izin yang diminta** yang muncul, pilih kotak centang **Setuju atas nama organisasi Anda** lalu pilih **Terima**.

7. Holly ingin menetapkan **Patti Fernandez** ke peran **Administrator Dukungan Layanan** . Untuk menetapkan peran ini menggunakan Microsoft Graph PowerShell, Anda harus terlebih dahulu mendapatkan ID objek peran Administrator Dukungan Layanan sehingga Anda dapat menetapkannya ke Patti. Namun, di Microsoft Graph PowerShell, Anda hanya dapat menetapkan peran yang telah "diaktifkan". Peran yang diaktifkan adalah peran yang diaktifkan dari templat peran, atau peran tersebut telah ditetapkan kepada pengguna melalui PowerShell atau pusat admin Microsoft 365. <br/>

    **Penting:** Sebelum Anda melakukan langkah ini, verifikasi bahwa jendela PowerShell Anda dalam mode layar penuh. Nama peran muncul di kolom akhir di sisi paling kanan layar. Jika Anda tidak dalam mode layar penuh, Anda tidak akan melihat nama peran yang terkait dengan setiap ID Objek. 

    Untuk melihat semua peran yang diaktifkan di Microsoft 365, masukkan perintah berikut di baris perintah lalu tekan Enter: <br/>
    
        Get-MgDirectoryRole    <br/>

    **Catatan:** Perintah ini menampilkan peran yang telah diaktifkan sejauh ini di Microsoft 365. Jika peran Administrator Dukungan Layanan muncul dalam daftar ini, Anda dapat langsung melanjutkan ke langkah 13 untuk menetapkan peran ke Patti. Namun, karena Administrator Dukungan Layanan tidak disertakan dalam daftar peran yang diaktifkan ini, Anda harus melakukan langkah 8-12 untuk mengaktifkan peran dari templat peran yang sesuai sebelum Anda dapat menetapkan Patti ke peran di langkah 13. 

8. Untuk mengaktifkan peran di Microsoft Graph PowerShell, Anda harus terlebih dahulu menemukan templatnya untuk mendapatkan ID objek templat. Anda perlu mengetahui ID objek templat untuk mengaktifkan peran dari templat. Ada dua cara di mana Anda dapat melihat templat peran - Anda dapat menampilkan seluruh daftar templat peran, atau Anda dapat menampilkan templat untuk peran tertentu. Sebagai pengalaman belajar, Anda akan melakukan kedua metode sehingga Anda dapat melihat perbedaannya. <br/>

    Mari kita mulai dengan menampilkan daftar lengkap templat peran bersama dengan ID objek dan nama tampilannya. Untuk melakukannya, ketik perintah berikut, lalu tekan Enter: <br/>

        Get-MgDirectoryRoleTemplate | Format-List Id, DisplayName   <br/>

    Seperti yang Anda lihat, setelah menjalankan perintah ini, Anda harus menggulir daftar templat peran untuk mencari peran Administrator Dukungan Layanan. Anda bisa melihat dengan mudah betapa ini bisa membosankan. Sebagai alternatif, jalankan perintah berikut untuk mengkueri templat peran tertentu - dalam hal ini, templat peran "Administrator Dukungan Layanan": <br/>

        Get-MgDirectoryRoleTemplate | ? DisplayName -eq "Service Support Administrator"   <br/>

    Setelah menjalankan perintah ini, Anda dapat melihat bahwa ini hanya menampilkan templat peran yang diminta. Tentu saja, mungkin ada kalanya menampilkan seluruh daftar templat peran yang diperlukan. Tetapi ketika Anda perlu mencari templat peran tunggal, menjalankan perintah PowerShell kedua akan jauh lebih efisien daripada harus menggulir seluruh daftar templat.
    
9. Sekarang setelah Anda mengkueri templat peran Administrator Dukungan Layanan di langkah sebelumnya, sorot **ID**-nya (misalnya, fe930be7-5e62-47db-91af-98c3a49a38b1) dan tekan **Ctrl+C** untuk menyalinnya ke clipboard (saat Anda menyalinnya, sorotan akan menghilang).

10. Anda sekarang akan membuat variabel yang mengambil atribut untuk templat Administrator Dukungan Layanan. Saat Anda mengetikkan perintah berikut, tekan **Ctrl+V** untuk menempelkan ID templat Administrator Dukungan Layanan yang Anda salin ke clipboard di langkah sebelumnya. <br/>

    Dari baris perintah, ketik perintah berikut, dan tekan Enter: <br/>

        $ServiceSupportRoleTemplate = @{ RoleTemplateID = "paste in template ID here" }  <br/>

    Misalnya: $ServiceSupportRoleTemplate = @{ RoleTemplateID = "fe930be7-5e62-47db-91af-98c3a49a38b1" }

11. Anda sekarang siap untuk mengaktifkan peran Administrator Dukungan Layanan berdasarkan atribut templat yang Anda ambil dalam variabel $ServiceSupportRoleTemplate. Ketik perintah berikut, lalu tekan Enter:  <br/>

        New-MgDirectoryRole -BodyParameter $ServiceSupportRoleTemplate

12. Untuk memverifikasi peran Administrator Dukungan Layanan telah diaktifkan, ketik perintah berikut dan tekan enter. Perintah ini akan menampilkan daftar peran yang diaktifkan:  <br/>
            
        Get-MgDirectoryRole <br/>

    **Catatan:** Perintah ini menampilkan ID objek dari semua peran yang diaktifkan, termasuk peran Administrator Dukungan Layanan yang baru saja Anda aktifkan dari templatnya. Anda nantinya akan menyalin dan menempelkan ID objek peran Administrator Dukungan Layanan di langkah 15 saat menetapkan Patti ke peran ini.

13. Untuk menetapkan Patti Fernandez ke peran Administrator Dukungan Layanan yang baru diaktifkan, Anda harus terlebih dahulu mendapatkan ID objek untuk akun pengguna Patti. Untuk melakukannya, ketik perintah berikut, lalu tekan Enter: <br/>

        Get-MgUser | Format-List ID, DisplayName

14. Sekarang setelah Anda mengetahui ID objek dari peran Administrator Dukungan Layanan yang baru diaktifkan dan ID objek akun pengguna Patti, Anda dapat menetapkan peran ke Patti. Untuk menyelesaikan proses, lakukan langkah-langkah berikut: <br/>

    a. Di perintah sebelumnya, Anda menampilkan daftar pengguna aktif. Sorot **Id** untuk akun Patti dan salin (**Ctrl+C**) ke clipboard. Sorotan menghilang setelah disalin ke clipboard.  <br/>

    b. Jalankan perintah berikut yang membuat variabel yang berisi objek direktori untuk akun pengguna Patti. Saat mengetik dalam perintah ini, tempelkan (**Ctrl+V**) ID yang baru saja Anda salin untuk akun pengguna Patti. <br/>

        $UserObject = @{ "@odata.id" = "https://graph.microsoft.com/v1.0/directoryObjects/paste in Patti's user account ID here" }  <br/>

    Misalnya: $UserObject = @{ "@odata.id" = "https://graph.microsoft.com/v1.0/directoryObjects/22fddbf7-42d2-4698-be65-ebc972a023e3" }

    c. Di langkah 12, Anda menampilkan daftar peran yang diaktifkan. Sorot ID untuk peran Administrator Dukungan Layanan dan salin (**Ctrl+C**) ke clipboard. <br/>

    d. Jalankan perintah berikut yang menetapkan variabel yang berisi akun pengguna Patti ($UserObject) ke peran direktori. Saat mengetik dalam perintah ini, tempelkan (**Ctrl+V**) ID yang baru saja Anda salin untuk peran Administrator Dukungan Layanan. <br/> 

        New-MgDirectoryRoleMemberByRef -DirectoryRoleId 'paste in the ID of the role here' -BodyParameter $UserObject
                
15. Anda sekarang ingin memverifikasi bahwa Patti telah ditetapkan ke peran Administrator Dukungan Layanan. Anda sebelumnya menyalin ID Objek peran ini ke clipboard, dan Anda menempelkannya di perintah sebelumnya. Anda juga harus menempelkannya ke dalam perintah ini. Ketik perintah berikut, lalu tekan Enter:
    
        Get-MgDirectoryRoleMember -DirectoryRoleId 'paste in the ID of the role here' 
                
16. Perintah sebelumnya hanya menampilkan ID pengguna yang ditetapkan ke peran yang dipilih. Namun, Anda dapat mencocokkan ID yang ditampilkan dengan ID Patti untuk memverifikasi bahwa akunnya telah diberi peran **Administrator Dukungan Layanan** . Seperti yang Anda lihat, Patti adalah satu-satunya pengguna yang ditetapkan untuk peran tersebut. 

17. Sekarang mari kita ulangi proses ini untuk melihat semua pengguna yang ditetapkan ke peran Administrator Global. Ulangi langkah 15 untuk memverifikasi berapa banyak pengguna Adatum yang telah ditetapkan ke peran **Administrator Global** . Untuk menyelesaikan perintah ini, Anda harus terlebih dahulu menyalin (**Ctrl+C**) ID peran Administrator Global ke clipboard. Anda dapat menemukan ID ini di daftar peran yang diaktifkan ketika Anda menjalankan langkah 12. <br/>

    **Peringatan:** Salin ID peran Administrator Global dan BUKAN ID templat peran Administrator Global.

18. Verifikasi ada beberapa pengguna Adatum yang telah diberi peran Administrator Global. Dalam skenario dunia nyata, Administrator Microsoft 365 akan menggunakan perintah PowerShell ini untuk memantau berapa banyak admin global yang ada dalam penyebaran Microsoft 365 mereka. Mereka kemudian akan menghapus peran Administrator Global dari setiap pengguna yang benar-benar tidak boleh memilikinya (ingat, pedoman praktik terbaik adalah memiliki antara 2 hingga 4 admin global dalam penyebaran Microsoft 365, tergantung pada ukuran organisasi).  <br/>

    Dalam kasus lab ini, sementara penyedia hosting lab Anda menetapkan peran Administrator Global kepada pengguna selain Administrator MOD (dan Anda menetapkannya ke Holly Dickson), Anda akan meninggalkan pengguna ini apa adanya. Dalam penyebaran Adatum fiktif ini, tidak ada gunanya membuang-buang waktu Anda menghapus peran ini dari akun mereka. Selain itu, beberapa tugas lab di masa mendatang didasarkan pada pengguna ini yang diberi peran Administrator Global. <br/>

    **PENTING:** Ingatlah bahwa dalam penyebaran dunia nyata Anda, Administrator Microsoft 365 harus memantau peran Administrator Global secara berkala untuk menjaga jumlah pengguna yang ditetapkan antara 2 dan 4.
    
19. Biarkan sesi Windows PowerShell Anda terbuka untuk latihan lab di masa mendatang, tetapi kecilkan sebelum melanjutkan ke tugas berikutnya.


### Tugas 4 - Memvalidasi penetapan peran 

Dalam tugas ini, Anda akan mulai dengan memeriksa properti administratif dua pengguna, Joni Sherman dan Lynne Robbins. Anda kemudian akan masuk ke beranda Microsoft 365 di VM Klien 2 (LON-CL2) sebagai setiap pengguna untuk mengonfirmasi beberapa perubahan yang Anda buat saat mengelola delegasi administratif mereka di tugas sebelumnya. Akhirnya, sebagai Lynne Robbins, Anda akan melakukan dua tugas pemeliharaan akun pengguna penting - mengatur ulang kata sandi dan memblokir akun pengguna.

1. Di LON-CL1, Anda tetap harus masuk ke pusat admin Microsoft 365 sebagai Holly Dickson. Jika belum, lakukan sekarang.

2. Di **Pusat admin Microsoft 365**, jika Anda tidak menampilkan **Pengguna Aktif**, maka navigasikan halaman tersebut sekarang.  

3. Di daftar **Pengguna aktif** , pilih **Joni Sherman**. 

4. Di jendela properti **Joni Sherman** , tab **Akun** ditampilkan secara default. Di bawah bagian **Peran** , itu harus menunjukkan bahwa Joni **Tidak memiliki akses administrator**. Pilih **X** di sudut kanan atas untuk menutup jendela properti Joni.

5. Pada daftar **Pengguna aktif** pilih **Lynne Robbins**. 

6. Pada jendela properti **Lynne Robbins** seharusnya menunjukkan bahwa Lynne telah diberi peran **Administrator Pengguna** . Tutup jendela properti Lynne.

7. Beralih ke VM Klien 2 (**LON-CL2**).

8. Di **LON-CL2**, pada layar masuk, Anda akan masuk sebagai akun **Admin** lokal dengan kata sandi **Pa55w.rd**.

9. Jika jendela **Jaringan** muncul, pilih **Ya**.

10. Pada taskbar, pilih ikon **Microsoft Edge**. Maksimalkan jendela browser Edge Anda jika perlu.

11. Di browser **Edge** Anda, navigasikan ke **https://portal.office.com**. 

12. Anda akan mulai dengan masuk ke Microsoft 365 sebagai **Joni Sherman**. Pada jendela **Masuk** masukkan **JoniS@xxxxxZZZZZZ.onmicrosoft.com** (di mana xxxxxZZZZZZ adalah prefiks penyewa yang disediakan oleh penyedia hosting lab Anda). Karena Anda masuk sebagai Joni Sherman, masukkan **Kata Sandi Pengguna** yang disediakan oleh penyedia hosting lab Anda di jendela **Masukkan kata sandi**. <br>

    Dalam kotak dialog **Perbarui kata sandi Anda** yang muncul, masukkan **Kata Sandi Pengguna** yang disediakan oleh penyedia hosting lab Anda di bidang **Kata sandi saat ini**. Lalu masukkan Kata Sandi Pengguna Baru di bidang **Kata sandi baru** dan **konfirmasi kata sandi**, lalu pilih **Masuk**.

13. Pada jendela **Tetap masuk?** , pilih kotak centang **Jangan perlihatkan ini lagi** lalu pilih **Ya**. Jika jendela **Simpan kata sandi** muncul, pilih **Jangan Pernah**.

14. Jika kotak dialog **Selamat Datang di Microsoft 365** muncul di tengah halaman, pilih panah maju (>) dua kali lalu tanda centang untuk menutupnya.

15. Jika jendela **Temukan aplikasi lainnya** atau jendela **Buat dengan Microsoft 365** atau jenis pengantar lainnya muncul, pilih **X** di sudut atas jendela untuk menutupnya.

16. Pada jendela **Selamat Datang di Microsoft 365** , yang merupakan beranda Microsoft 365 Joni, panel navigasi muncul di sisi layar yang menunjukkan aplikasi yang dapat diakses pengguna. Di panel **Aplikasi** ini, perhatikan bagaimana opsi **Admin** tidak ditampilkan. Ini karena Joni tidak pernah diberi peran administrator Microsoft 365. 

17. Anda sekarang akan keluar dari Microsoft 365 sebagai Joni. Di **Microsoft Edge**, di kanan atas halaman **Selamat Datang di Microsoft 365** , pilih ikon pengguna untuk **Joni Sherman** (lingkaran di sudut atas dengan gambar Joni di dalamnya), dan di jendela **Joni Sherman** yang muncul, pilih **Keluar.** 

18. Anda sekarang akan masuk kembali ke Microsoft 365 sebagai **Lynne Robbins**. Di tab browser **Edge** Anda saat ini, itu harus menampilkan pesan yang menunjukkan **Joni, Anda telah keluar sekarang**. Di jendela ini, Anda memiliki opsi untuk masuk kembali sebagai Joni, atau masuk sebagai pengguna yang berbeda. <br/>

    Pilih **Beralih ke akun yang lain**, dan di bidang **Alamat email** yang muncul, masukkan **LynneR@xxxxxZZZZZZ.onmicrosoft.com**(di mana xxxxxZZZZZZ adalah awalan penyewa yang disediakan oleh penyedia hosting lab Anda) lalu pilih **Masuk.** Di jendela **Masukkan kata sandi** , masukkan **Kata Sandi Pengguna** yang disediakan oleh penyedia hosting lab Anda dan pilih **Masuk**. <br>

    Dalam kotak dialog **Perbarui kata sandi Anda** yang muncul, masukkan **Kata Sandi Pengguna** yang disediakan oleh penyedia hosting lab Anda di bidang **Kata sandi saat ini**. Lalu masukkan Kata Sandi Pengguna Baru di bidang **Kata sandi baru** dan **konfirmasi kata sandi**, lalu pilih **Masuk**. 

19. Jika kotak dialog **Selamat Datang di Microsoft 365** muncul, pilih panah maju (>) dua kali lalu pilih tanda centang untuk menutup jendela.

20. Jika jendela **Temukan aplikasi lainnya** atau jendela **Buat dengan Microsoft 365** atau jenis pengantar lainnya muncul, pilih **X** di sudut atas jendela untuk menutupnya.

21. Pada jendela **Selamat Datang di Microsoft 365** , yang merupakan beranda Microsoft 365 Lynne, perhatikan bagaimana ikon **Admin** ditampilkan di panel navigasi di sisi layar. Ikon ini muncul karena Lynne ditetapkan ke peran administrator Microsoft 365. Pilih ikon **Admin** untuk membuka pusat admin Microsoft 365.

22. Di **pusat admin Microsoft 365**, pilih **Pengguna** di panel navigasi lalu pilih **Pengguna aktif**. 

23. Sebagai **Administrator Pengguna**, Lynne memiliki izin untuk mengubah kata sandi pengguna. Lynne baru-baru ini dihubungi oleh **Diego Siciliani** dan **Pradeep Gupta**, yang masing-masing melaporkan bahwa kata sandi mereka mungkin telah disusupi. Sesuai kebijakan perusahaan Adatum, Lynne harus mengatur ulang kata sandi mereka ke nilai sementara, dan kemudian memaksa mereka untuk mengatur ulang kata sandi mereka pada login berikutnya.   <br/>

    Di daftar **Pengguna aktif**, saat Anda memindahkan mouse dari satu akun pengguna ke akun pengguna lain, perhatikan ikon **kunci (Atur ulang kata sandi)** yang muncul di sebelah kanan nama setiap pengguna. Pilih ikon kunci yang muncul di sebelah kanan nama **Diego Siciliani** .

24. Di jendela **Atur ulang kata sandi** untuk Diego, jika kotak centang **Buat kata sandi** secara otomatis menampilkan tanda centang, maka pilih kotak ini untuk menghapusnya. Ini akan memungkinkan Lynne untuk menetapkan kata sandi sementara kepada Diego secara manual.  

25. Masukkan **diego** di bidang **Kata Sandi** . Perhatikan di sebelah kanan kata sandi, sistem menampilkan pesan yang menunjukkan ini adalah kata sandi yang **Lemah**. Perhatikan juga pesan yang muncul di bawah bidang yang menunjukkan persyaratan untuk kata sandi yang kuat. Terakhir, perhatikan bagaimana tombol **Atur ulang kata sandi** di bagian bawah panel tidak diaktifkan. **Tombol ini hanya akan diaktifkan setelah Anda memasukkan kata sandi yang kuat**.  

26. Verifikasi kotak centang **Wajibkan pengguna ini untuk mengubah kata sandi mereka saat pertama kali masuk** dipilih (jika tidak, maka pilih sekarang untuk menampilkan tanda centang). Masukkan **Pa55w.rd** di bidang **Kata Sandi** . Perhatikan bahwa bidang **Kata Sandi** menunjukkan ini adalah kata sandi yang kuat. <br/>

    Namun, sekarang pilih kotak centang **Wajibkan pengguna ini untuk mengubah kata sandi mereka saat pertama kali masuk** untuk menghapusnya. Perhatikan pesan kesalahan yang muncul yang menunjukkan kata sandi (Pa55w.rd) berisi kata, frasa, atau rangkaian angka yang membuatnya mudah ditebak. Dalam hal ini, Anda memasukkan variasi **kata sandi**, yang akan memicu kesalahan ini. Sistem ini memungkinkan Anda memasukkan kata sandi ini jika Anda memaksa pengguna untuk mengubahnya saat mereka masuk pertama kali. Tetapi jika Anda tidak memaksa pengguna untuk memasukkan kata sandi yang berbeda saat mereka masuk pertama kali, maka kata sandi ini tidak diizinkan.

27. Setelah dua kali percobaan kata sandi yang gagal ini, Lynne memutuskan untuk membiarkan Microsoft 365 secara otomatis menghasilkan kata sandi. Pilih kotak centang **Buat kata sandi secara otomatis** sehingga menampilkan tanda centang. 
    
28. Kata sandi yang dibuat secara otomatis hanya akan menjadi kata sandi sementara karena Lynne ingin memaksa Diego untuk mengubahnya saat ia masuk kembali. Oleh karena itu, verifikasi bahwa kotak centang **Wajibkan pengguna ini untuk mengubah kata sandi mereka saat pertama kali masuk** menampilkan tanda centang; jika kotaknya kosong, maka pilih agar menampilkan tanda centang.

29. Pilih **Reset kata sandi**.

30. Jika diminta untuk menyimpan kata sandi, pilih **jangan pernah** untuk menutup jendela.

31. Anda harus menerima pesan kesalahan yang menunjukkan bahwa Anda tidak dapat mengatur ulang kata sandi Diego karena dia telah diberi peran admin. Dalam kasus Diego, Anda menugaskannya peran Administrator Penagihan sebelumnya dalam latihan lab ini. Karena hanya administrator Global yang dapat mengubah kata sandi administrator lain, dan karena Lynne bukan administrator Global, dia harus meminta Holly Dickson untuk membuat perubahan ini. Pilih **Tutup** di panel **Atur ulang kata sandi** . 

32. Jika jendela permintaan survei muncul, pilih **Batalkan**.

33. Anda sekarang ingin mengubah kata sandi Pradeep Gupta. Pada daftar **Pengguna aktif** pilih ikon **tombol (Atur ulang kata sandi)** yang muncul di sebelah kanan **Pradeep Gupta**. 

34. Pada jendela **Atur ulang kata sandi** yang muncul untuk Pradeep, pastikan kotak centang **Otomatis membuat kata sandi** menampilkan tanda centang; jika tidak, pilih kotak ini sekarang agar sistem membuat kata sandi untuk Pradeep secara otomatis.  <br/>

    Ini hanya kata sandi sementara karena Lynne ingin memaksa Pradeep untuk mengubahnya saat berikutnya dia masuk. Oleh karena itu, verifikasi bahwa kotak centang **Wajibkan pengguna ini untuk mengubah kata sandi mereka saat pertama kali masuk** menampilkan tanda centang; jika kotaknya kosong, maka pilih agar menampilkan tanda centang.
    
35. Pilih tombol **Atur ulang kata sandi** .

36. Pada jendela **Kata Sandi telah diatur ulang** , Anda harus menerima pesan yang menunjukkan bahwa Anda berhasil mengatur ulang kata sandi untuk Pradeep. Pilih **Tutup.**

37. Manajemen baru-baru ini menemukan bahwa nama pengguna Alex Wilber mungkin telah disusupi. Akibatnya, Lynne telah diminta untuk memblokir akun Alex sehingga tidak ada yang dapat masuk dengan nama penggunanya sampai manajemen dapat menentukan sejauh mana masalah tersebut. Pada daftar **Pengguna aktif** pilih kotak centang di sebelah kiri nama **Alex Wilber** (JANGAN pilih nama Alex itu sendiri).  <br/>

    **Penting:** Karena Anda akan menjalankan perintah global daripada perintah yang terkait dengan akun Alex, Anda hanya ingin akun Alex dipilih dalam daftar pengguna aktif. Jika ada akun pengguna lain yang dipilih, Anda harus membatalkan pilihan akun pengguna tersebut sebelum melanjutkan. Gulir daftar pengguna aktif dan verifikasi bahwa tidak ada akun pengguna lain yang dipilih. Jika akun selain Alex dipilih, pilih kotak centang akun untuk menghapusnya. **Hanya akun Alex Wilber yang harus dipilih.**

38. Di bilah menu di bagian atas halaman, pilih **ikon elipsis (...)** untuk menampilkan menu drop-down tindakan tambahan. Di menu yang muncul, pilih **Edit status masuk** .

39. Di panel **Blokir masuk** yang muncul, verifikasi alamat email Alex muncul di bawah judul **Blokir masuk** . Pilih kotak centang **Blokir pengguna ini agar tidak masuk** , lalu pilih **Simpan perubahan.** 

40. Jendela **Blokir masuk** akan menampilkan pesan yang menunjukkan bahwa Alex sekarang diblokir untuk masuk (dan tidak ada yang bisa masuk dengan nama pengguna Alex jika nama penggunanya telah disusupi). Selain itu, Alex akan secara otomatis keluar dari layanan Microsoft dalam waktu 60 menit. Pilih **X** di sudut kanan atas panel untuk menutupnya. 

41. Lynne baru saja diberi tahu bahwa nama pengguna **Nestor Wilke** juga berpotensi disusupi. Ulangi langkah 37 hingga 40 untuk memblokir Nestor agar tidak masuk (dan memblokir orang lain agar tidak menggunakan nama penggunanya untuk masuk). <br/>

    Ketika Anda mencoba memblokir masuk Nestor, Anda seharusnya menerima pesan kesalahan yang menunjukkan **Perubahan tidak dapat disimpan**. Alasan Anda menerima kesalahan ini adalah bahwa Nestor adalah Administrator Global, dan Lynne tidak. Hanya Administrator Global yang dapat memblokir Admin Global lain agar tidak dapat masuk. Lynne perlu meminta Holly Dickson untuk membuat perubahan ini. <br/>

    Tutup panel **Blokir masuk** .

42. Anda sebelumnya memblokir Alex Wilber agar tidak bisa masuk. Untuk memverifikasi apakah dia diblokir, Anda akan mencoba masuk sebagai Alex. Keluar dari Microsoft 365 dengan memilih ikon pengguna untuk **Lynne Robbins** (lingkaran dengan gambar Lynne di sudut atas), dan di jendela **Lynne Robbins** yang muncul, pilih **Keluar.** 

43. Sebagai praktik terbaik, tutup semua tab browser Anda kecuali tab **Keluar** setelah Anda keluar. Pada tab **Keluar** navigasikan ke **https://portal.office.com**. 

44. Di jendela **Pilih akun** , pilih **Gunakan akun lain**. Pada jendela **Masuk** masukkan **AlexW@xxxxxZZZZZZ.onmicrosoft.com** (di mana xxxxxZZZZZZ adalah prefiks penyewa yang disediakan oleh penyedia hosting lab Anda). Di jendela **Masukkan kata sandi** , masukkan **Kata Sandi Pengguna** yang disediakan oleh penyedia hosting lab Anda.  <br/>

    Jendela **Pilih akun** akan muncul, dan akan menampilkan pesan kesalahan yang menunjukkan **akun Anda telah dikunci. Hubungi orang dukungan Anda untuk membuka kuncinya, lalu coba lagi.** Anda baru saja memverifikasi bahwa Alex (atau seseorang yang telah mendapatkan nama pengguna dan kata sandi Alex) tidak dapat masuk. <br/>

    **Catatan:** Perlu waktu beberapa menit agar blok akun dapat sepenuhnya diterapkan. Hingga blok diterapkan dalam sistem, Alex mungkin masih dapat masuk, tetapi tidak ada layanan Microsoft 365 yang akan tersedia untuknya, dan tidak akan muncul di portal Microsoft 365. Setelah akun tidak diblokir, layanan akan tersedia lagi. <br/>

    Jika Anda dapat masuk sebagai Alex, keluar dan tunggu beberapa menit. Ini mungkin waktu yang tepat untuk beristirahat sejenak. Kemudian coba untuk masuk kembali sebagai Alex. Pada saat ini, Anda mudah-mudahan telah menerima pesan kesalahan yang menunjukkan akun Alex telah diblokir untuk masuk. 
    
45. Beralih kembali ke **LON-CL1**. 

46. Di **LON-CL1**, Anda masih harus masuk ke **Microsoft 365** sebagai Holly Dickson di browser Edge Anda. Daftar **Pengguna aktif** harus ditampilkan di **pusat admin Microsoft 365** dari yang sebelumnya dalam tugas ini. 

47. Setelah penyelidikan lebih lanjut, CTO Adatum telah menentukan bahwa akun Alex Wilber, pada kenyataannya, tidak disusupi; oleh karena itu, CTO telah meminta Holly untuk menghapus blok pada akun pengguna Alex. Ulangi langkah 37 sampai 40 untuk membuka blokir akunnya. Perhatikan bagaimana jendela **Blokir masuk** dari langkah 39 sekarang menampilkan jendela **Buka blokir masuk** sebagai gantinya.  <br/>

    Di jendela **Buka blokir masuk** , kotak centang **Blokir pengguna ini agar tidak masuk** saat ini dipilih. Pilih kotak centang ini untuk menghapusnya, lalu pilih **Simpan perubahan**. <br/>
    
    **PENTING:** Pesan peringatan ditampilkan yang menunjukkan bahwa diperlukan waktu hingga 15 menit sebelum Alex dapat masuk lagi. Mengingat batasan waktu dalam pelatihan, Anda **TIDAK** akan mencoba memverifikasi apakah Alex dapat masuk kembali. Jika mau, Anda dapat mencoba masuk sebagai Alex di lain waktu jika Anda sedang istirahat atau memiliki waktu luang dan Anda ingin mengujinya. Untuk saat ini, tetap berada di LON-CL1 dan cukup tutup jendela **Buka blokir masuk**.
    
48. Di LON-CL1, biarkan browser Anda dan semua tab terbuka dan lanjutkan ke latihan berikutnya. 


# Akhir Lab 2

