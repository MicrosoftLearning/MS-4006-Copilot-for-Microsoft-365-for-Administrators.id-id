# Jalur Pembelajaran 3 - Lab 3 - Latihan 1 - Menerapkan label Sensitivitas dengan Microsoft Entra ID Protection

Dalam peran Anda sebagai Holly Dickson, Administrator Microsoft 365 baru Adatum, Anda memiliki Microsoft 365 yang disebarkan di lingkungan lab virtual. Saat Melanjutkan proyek pilot Microsoft 365, langkah Anda selanjutnya adalah menerapkan Label Sensitivitas dengan Microsoft Entra ID Protection di Adatum. Di lab ini, Anda akan membuat dan menerbitkan label, dan Anda akan menguji label yang diterbitkan. Namun, dalam melakukannya, Anda tidak akan menguji label yang Anda buat di lab ini. Sebagai gantinya, Anda akan menguji label yang berbeda.

**Penting:** Saat Anda menerbitkan label sensitivitas dan kebijakan label baru, dibutuhkan waktu hingga 24 jam untuk disebarluaskan melalui Microsoft 365. Dengan demikian, Anda tidak akan dapat menguji label yang Anda buat di lab ini. Sebagai gantinya, Anda akan menguji label sensitivitas yang sudah ada sebelumnya bernama **Project - Falcon**. Label yang sudah ada sebelumnya ini hampir identik dengan label yang akan Anda buat, sehingga Anda pada dasarnya dapat melihat hasil yang sama jika Anda dapat menguji label yang Anda buat. 


### Tugas 1 - Instal klien Pelabelan Terpadu Microsoft Entra ID Protection

Untuk menerapkan label Sensitivitas sebagai bagian dari proyek pilot Anda di Adatum, Anda harus terlebih dahulu menginstal klien Microsoft Entra ID Protection dari Pusat Unduhan Microsoft.

**Catatan:** Meskipun rebranding Azure AD ke Microsoft Entra ID masih berlangsung, klien Azure Information Protection belum diubah namanya pada penulisan ini. Ini pada akhirnya akan diubah nama menjadi klien Microsoft Entra ID Protection.

1. Anda masih harus masuk ke LON-CL1 sebagai akun **adatum\administrator** lokal, dan di browser Edge Anda, Anda masih harus masuk ke Microsoft 365 sebagai **Holly Dickson**. 

2. Di **Microsoft Edge**, buka tab baru dan masukkan (atau salin dan tempel) URL berikut di bilah alamat: **https://www.microsoft.com/en-us/download/confirmation.aspx?id=53018** <br/>

    Ini akan memulai unduhan untuk **klien Perlindungan Informasi Microsoft Purview**.

3. Di jendela **Unduhan** yang muncul di kanan atas halaman, Anda akan melihat file **PurviewInfoProtection.exe** sedang diunduh. Setelah file selesai diunduh, pilih tautan **Buka file** yang muncul di bawah nama file.

4. Wizard **Perlindungan Informasi Microsoft Azure** akan terbuka. Jika panduan tidak ditampilkan pada desktop, pilih ikon untuk panduan pada bilah tugas untuk menampilkan panduan.

5. Dalam wizard, pada jendela **Instal **klien Microsoft Purview Information Protection**** yang muncul, pilih pemeriksaan **saya mengakui bahwa Add-in AIP untuk Office akan dihapus instalasinya (diperlukan),** dan bersihkan (hapus centang) kotak centang **Bantu tingkatkan Microsoft Purview Information Protection dengan mengirim statistik penggunaan ke microsoft**. Lalu pilih lagi tombol **Ekspor**.

6. Setelah penginstalan selesai, pilih **Tutup**.

Anda telah berhasil menginstal klien Label Terpadu Azure Information Protection pada VM LON-CL1.

### Tugas 2 – Mengaktifkan label sensitivitas untuk file di SharePoint dan OneDrive

Dalam latihan ini Anda akan mengaktifkan label sensitivitas untuk file Office dan file PDF yang didukung di SharePoint dan OneDrive. Saat fitur ini diaktifkan, pengguna akan melihat tombol **Sensitivitas** pada pita sehingga mereka bisa menerapkan label. Mereka juga melihat nama label yang diterapkan pada bilah status. Untuk SharePoint, pengguna juga dapat melihat dan menerapkan label sensitivitas dari panel detail.

Mengaktifkan fitur ini juga menghasilkan SharePoint dan OneDrive dapat memproses konten file Office dan secara opsional, dokumen PDF yang telah dienkripsi dengan menggunakan label sensitivitas. Label dapat diterapkan di Office untuk web atau di aplikasi desktop Office dan diunggah atau disimpan di SharePoint dan OneDrive Hingga Anda mengaktifkan fitur ini, layanan ini tidak dapat memproses file terenkripsi, yang berarti penulisan bersama, eDiscovery, pencegahan kehilangan data, pencarian, dan fitur kolaboratif lainnya tidak akan berfungsi untuk file-file ini.

Anda akan terlebih dahulu mengaktifkan label sensitivitas untuk file online Office yang disimpan di SharePoint dan OneDrive. Anda kemudian akan mengaktifkan dukungan untuk PDF.

**Catatan:** Seperti semua perubahan konfigurasi tingkat penyewa untuk SharePoint dan OneDrive, diperlukan waktu sekitar 15 menit agar perubahan diterapkan.

1. Di LON-CL1, di browser Edge, Anda masih harus masuk ke Microsoft 365 sebagai **Holly Dickson**.

2. Di browser Edge, Anda masih harus membuka tab untuk **pusat admin Microsoft 365**. Jika tidak, buka tab baru dan masukkan URL berikut: **https://admin.microsoft.com**.

3. Pada **pusat admin Microsoft 365**, jika perlu, pilih **... Tampilkan semua**. Pilih **Kepatuhan** di bawah grup **Pusat admin**. Ini membuka portal Microsoft Purview di tab baru.

4. Anda akan mulai dengan mengaktifkan label sensitivitas untuk file online Office yang disimpan di SharePoint dan OneDrive. <br/>

    Di portal **Microsoft Purview**, di bawah bagian **Solusi** di panel navigasi, pilih **Perlindungan informasi**, lalu pilih **Label**.

5. Pada halaman **Label** , pesan berikut ini akan muncul di tengah halaman: **Organisasi Anda belum mengaktifkan kemampuan untuk memproses konten dalam file online Office yang memiliki label sensitivitas terenkripsi yang diterapkan dan disimpan di OneDrive dan SharePoint. Anda dapat mengaktifkan di sini, tetapi perhatikan bahwa konfigurasi tambahan diperlukan untuk lingkungan Multi-Geo.** <br/>

    Di bawah pesan ini adalah tombol **Aktifkan sekarang** . Pilih tombol ini.  <br/>

    **Catatan:** Perintah segera berjalan dan ketika halaman di-refresh berikutnya, Anda tidak lagi melihat pesan atau tombol tersebut.

6. Sekarang Anda akan mengaktifkan perlindungan PDF untuk file di SharePoint dan OneDrive. <br/>

    Di portal **Microsoft Purview**, di bawah **Perlindungan informasi** di panel navigasi, pilih **Pelabelan otomatis**.

7. Pada halaman **Pelabelan** otomatis, Anda akan melihat banner **Lindungi PDF dengan Pelabelan otomatis** di tengah halaman. Pilih judul **Lindungi PDF dengan Pelabelan otomatis** untuk mengaktifkan perlindungan PDF untuk file di SharePoint dan OneDrive. 

8. Dalam kotak dialog **Pelabelan otomatis** yang muncul, pilih **Konfirmasi** untuk mengonfirmasi bahwa Anda ingin mengaktifkan proteksi PDF untuk file di SharePoint dan OneDrive. 

    **Catatan:** Perintah segera berjalan dan ketika halaman berikutnya di-refresh, Anda tidak lagi melihat banner **Lindungi PDF dengan Pelabelan otomatis**.

9. Biarkan browser Edge Anda terbuka bersama dengan semua tab. 

### Tugas 3 – Buat label sensitivitas

Dalam latihan ini Anda akan membuat Label Sensitivitas dan menambahkannya ke kebijakan default sehingga valid untuk semua pengguna penyewa Adatum.

1. Di LON-CL1, di browser Edge, Anda masih harus masuk ke Microsoft 365 sebagai **Holly Dickson**.

2. Di browser Edge, Anda masih harus membuka tab untuk **pusat admin Microsoft 365**. Jika tidak, buka tab baru dan masukkan URL berikut: **https://admin.microsoft.com**.

3. Dari panel navigasi kiri **pusat admin Microsoft 365**, jika perlu, pilih **... Tampilan semua** di panel navigasi. Pilih **Kepatuhan** di bawah grup **Pusat admin**.

4. Pada portal kepatuhan **Microsoft Purview**, pilih **Perlindungan informasi** di panel navigasi lalu pilih **Label**. 

5. Pada halaman **Label**, pesan peringatan ditampilkan dalam kotak berbayang kuning muda di tengah halaman yang menunjukkan: **Organisasi Anda belum mengaktifkan kemampuan untuk memproses konten dalam file online Office yang memiliki label sensitivitas terenkripsi yang diterapkan dan disimpan di OneDrive dan SharePoint. Anda dapat mengaktifkan di sini, tetapi perhatikan bahwa konfigurasi tambahan diperlukan untuk lingkungan Multi-Geo.** <br/>

    Pilih tombol **Aktifkan sekarang** yang muncul di sisi kanan pesan ini. Ini akan memungkinkan Adatum untuk menerapkan label Sensitivitas di dalam lingkungan Microsoft 365-nya. <br/>

    Perhatikan bagaimana pesan sekarang telah berubah untuk menunjukkan: **Anda sekarang dapat membuat label sensitivitas dengan pengaturan kontrol privasi dan akses untuk Teams, situs SharePoint, dan Grup Microsoft 365.** 

6. Pada halaman **Label**, pilih opsi **+Buat label** yang muncul di bilah menu di tengah layar, di bawah pesan sebelumnya. Ini memulai wizard **Label sensitivitas baru**.

7. Di wizard **Label sensitivitas baru**, pada halaman **Berikan detail dasar untuk label ini**, masukkan informasi berikut ini:

    - Nama: **PII**
    
    - Nama tampilan: **PII**

    - Deskripsi untuk pengguna: **Dokumen, file, dan email dengan PII**

    - Deskripsi untuk admin: **Dokumen, file, dan email dengan PII**

    - Warna label: pilih salah satu warna yang ingin Anda tetapkan ke label sensitivitas Anda

8. Pilih **Selanjutnya**.

9. Pada halaman **Tentukan cakupan untuk label ini**, verifikasi kotak centang **Item** dipilih (pilih sekarang jika perlu) lalu pilih **Berikutnya**.

10. Pada halaman **Pilih pengaturan proteksi untuk item berlabel**, pilih kedua kotak centang untuk **Terapkan atau hapus enkripsi** dan **Terapkan penandaan konten**, lalu pilih **Berikutnya**.

11. Pada halaman **Enkripsi** , Anda akan menentukan siapa yang dapat mengakses item yang menerapkan label ini. Pilih opsi **Hapus enkripsi jika file atau email atau kalender dienkripsi** lalu pilih **Berikutnya**.

12. Pada halaman **Penandaan konten**, atur pengalih **Penandaan konten** ke **Aktif**. Ini menampilkan tiga opsi yang memungkinkan Anda menyesuaikan bagaimana Anda ingin menandai file dan email. <br/>

    Pilih ketiga kotak centang. Di bawah setiap pengaturan, pilih **Sesuaikan teks**. Ini membuka panel untuk mengkustomisasi pengaturan tertentu tersebut. Masukkan informasi berikut di panel **Kustomisasi** untuk setiap opsi (pilih **Simpan** setelah memasukkan pengaturan untuk setiap opsi): <br/>

    - **Menambahkan marka air** 
        - Teks marka air: **Sensitif - Jangan Bagikan** (Petunjuk: setelah memasukkan nilai ini, salin (Ctrl+C) sehingga Anda dapat menempelkannya (Ctrl+V) di dua pengaturan teks lainnya)
        - Ukuran font: **25**
        - Warna font: **Biru**
        - Tata letak teks: **Diagonal**
            
    - **Tambahkan header** 
        - Teks header: **Sensitif - Jangan Bagikan**
        - Ukuran font: **25**
        - Warna font: **Merah**
        - Ratakan teks: **Tengah**
            
    - **Menambahkan footer**
        - Teks footer: **Sensitif - Jangan Bagikan**
        - Ukuran font: **25**
        - Warna font: **Merah**
        - Ratakan teks: **Tengah**

13. Pada halaman **Konfirmasi**, pilih **Berikutnya**. 

14. Pada halaman **Pelabelan otomatis untuk file dan email**, atur **pengalih Pelabelan otomatis untuk file dan email** ke **Aktif**. Ini memungkinkan serangkaian opsi yang akan Anda perbarui di langkah berikutnya.

15. Di bawah **Deteksi konten yang cocok dengan kondisi ini**, pilih **+Tambahkan kondisi** lalu pilih **Konten berisi**.

16. Di jendela **Konten berisi** , pilih panah drop-down **Tambahkan** lalu pilih **Jenis info sensitif**.

17. Di jendela **Jenis info sensitif**, arahkan mouse Anda ke sebelah kiri judul kolom **Nama** . Pilih kotak centang yang muncul, yang secara otomatis memilih semua jenis informasi sensitif. Pilih **Tambahkan**, yang akan menambahkan semua jenis informasi sensitif ini ke label Anda.

18. Pada halaman **Pelabelan otomatis untuk file dan email**, semua jenis informasi sensitif yang Anda pilih akan ditampilkan. Gulir ke bagian bawah pada jendela dan perbarui pengaturan berikut:

    - Saat konten cocok dengan kondisi ini: pilih **Terapkan Label secara otomatis**

    - Tampilkan pesan ini kepada pengguna saat label diterapkan: masukkan **Konten sensitif telah terdeteksi dan akan dienkripsi**.
        
19. Pilih **Selanjutnya**.

20. Pada halaman **Tentukan pengaturan proteksi untuk grup dan situs** , biarkan kedua kotak centang kosong dan pilih **Berikutnya**.

21. Pada halaman **Pelabelan otomatis untuk aset data skema (pratinjau)**, jangan aktifkan Pelabelan otomatis untuk aset data skema (pratinjau). Pilih **Selanjutnya**. 

22. Pada halaman **Tinjau pengaturan dan selesai** , tinjau informasi yang Anda masukkan. Jika ada pengaturan yang perlu dikoreksi, pilih opsi **Edit** yang sesuai dan buat perubahan yang diperlukan. Saat semua informasi muncul dengan benar, pilih **Buat label**.

23. Kotak dialog **Kesalahan Klien** akan muncul yang menyatakan blob aturan yang dihasilkan untuk label yang Anda coba buat terlalu panjang. Ukuran maksimum pilihan jenis informasi sensitif yang dapat Anda buat pada satu waktu sesuai aturannya adalah **49152**. Dengan memilih semua jenis informasi sensitif seperti yang Anda lakukan di jendela **Jenis info sensitif** beberapa langkah ke belakang, Anda telah melebihi batas ini. <br/>

    **CATATAN: Kami sengaja meminta Anda memilih semua jenis informasi sensitif sehingga Anda akan menerima kesalahan ini.** Kami ingin Anda mengalami kesalahan ini sehingga jika itu terjadi di lingkungan produksi Anda, Anda akan tahu mengapa Anda menerima kesalahan ini dan bagaimana Anda dapat memperbaikinya.  <br/>

    Untuk memperbaiki masalah ini, pilih **OK** dalam kotak dialog **Kesalahan Klien**, lalu pada halaman **Tinjau pengaturan dan selesai**, gulir ke bawah ke bagian **Pelabelan otomatis untuk file dan email** dan pilih **Edit**.
    
24. Ini akan mengembalikan Anda ke halaman **Pilih pengaturan perlindungan untuk item berlabel** dalam panduan. Pilih **Berikutnya** di halaman ini, pilih **Berikutnya** di halaman **Enkripsi**, lalu pilih **Berikutnya** di halaman **Penandaan Konten**. Ini akan membawa Anda ke **halaman Pelabelan otomatis untuk file dan email** . 

25. Pada halaman **Pelabelan otomatis untuk file dan email**, di sebelah kanan kondisi **Konten berisi**, pilih **ikon tempat sampah**. Ini akan menghapus kondisi **Konten berisi** yang ada untuk label **PII** yang Anda buat. <br/>

    Di langkah-langkah yang tersisa, Anda akan menambahkan kondisi baru yang hanya berisi dua jenis informasi sensitivitas dan bukan semua jenis informasi sensitivitas seperti yang Anda lakukan pada awalnya.

26. Pada halaman **Pelabelan otomatis untuk file dan email**, di bawah **Deteksi konten yang cocok dengan kondisi ini**, pilih **+Tambahkan kondisi** lalu pilih **Konten berisi**.

27. Di jendela **Konten berisi** , pilih panah drop-down **Tambahkan** lalu pilih **Jenis info sensitif**.

28. Di jendela **Jenis info sensitif**, dalam daftar jenis informasi sensitif, hanya pilih **nomor perutean ABA** dan kotak centang **Nomor Jaminan Sosial AS (SSN),** lalu pilih **Tambahkan**. Kembali ke **halaman Pelabelan otomatis untuk file dan email**, kedua jenis informasi sensitif ini akan muncul. Pilih **Selanjutnya**.

29. Pada halaman **Tentukan pengaturan perlindungan untuk grup dan situs** , biarkan dua kotak centang ini kosong dan pilih **Berikutnya**.

30. Pada halaman **Pelabelan otomatis untuk aset data skema (pratinjau),** jangan aktifkan Pelabelan otomatis untuk kolom database. Pilih **Selanjutnya**.

31. Pada halaman **Tinjau pengaturan Anda dan selesai**, pilih **Buat label**.

32. Pada halaman **Label sensitivitas Anda telah dibuat**, pilih opsi **Jangan buat kebijakan dulu,** lalu pilih **Selesai**. Ini mengembalikan Anda ke halaman **Label**.

33. Sekarang saatnya untuk menerbitkan label **PII** . Pada halaman **Label**, jika label **PII** tidak muncul dalam daftar label, pilih **Refresh** pada bilah menu. Setelah label **PII** muncul, pilih kotak centang yang muncul di sebelah kirinya. 

34. Pilih opsi **Terbitkan label** yang muncul di bilah menu di atas daftar label. Ini akan memulai wizard **Buat kebijakan**.

35. Di wizard **Buat kebijakan**, pada halaman **Pilih label sensitivitas untuk diterbitkan**, label **PII** sudah tercantum, jadi pilih **Berikutnya**. 

36. Pada halaman **Tetapkan unit admin**, pilih **Berikutnya** karena Anda akan menetapkan kebijakan PII ini ke direktori lengkap Adatum, bukan hanya sekelompok unit admin tertentu.

37. Pada halaman **Terbitkan ke pengguna dan grup** , Anda dapat memilih apakah akan membuat kebijakan Anda tersedia untuk semua pengguna dan grup, atau Anda dapat membatasi kebijakan untuk pengguna dan grup yang dipilih. Untuk lab ini, Anda ingin membuat kebijakan tersedia untuk semua orang. Opsi **Pengguna dan grup** sudah dipilih secara default (jika tidak, lalu pilih sekarang). Ini akan membuat kebijakan Anda tersedia untuk semua pengguna dan grup. Pilih **Selanjutnya**.  <br/>

    **Catatan:** Saat melakukan ini di penerapan dunia nyata Anda, jika Anda ingin membatasi kebijakan Anda ke sejumlah pengguna atau grup tertentu, maka Anda akan memilih **Edit** dan membuat pilihan tersebut. 

38. Pada halaman **Pengaturan kebijakan**, pilih kotak centang **Pengguna harus menyediakan pembenaran untuk menghapus label atau menurunkan klasifikasinya**, lalu pilih **Berikutnya**. 

39. Pada halaman **Terapkan label default ke dokumen**, pilih **PII** di menu drop-down yang muncul, lalu pilih **Berikutnya**.

40. Pada halaman **Terapkan label default ke email**, pilih **PII** di menu drop-down yang muncul, lalu pilih **Berikutnya**.

41. Pada halaman **Terapkan label default ke rapat dan acara kalender**, pilih **PII** di menu drop-down yang muncul, lalu pilih **Berikutnya**.

42. Pada halaman **Terapkan label default ke konten Fabric dan Power BI**, pilih **PII** di menu drop-down yang muncul, lalu pilih **Berikutnya**.

43. Pada halaman **Namai kebijakan Anda**, masukkan **Kebijakan PII** di bidang **Nama**, lalu masukkan (atau salin dan tempel) deskripsi berikut untuk kebijakan label sensitivitas ini: **Tujuan kebijakan ini adalah untuk mendeteksi informasi sensitif seperti nomor perutean bank ABA dan nomor keamanan sosial AS dalam email dan dokumen, dan untuk mengenkripsi informasi ini saat ditemukan. Pengguna harus memberikan penjelasan untuk menghapus label klasifikasi ini.** Pilih **Selanjutnya**.

44. Pada halaman **Tinjau dan selesai**, tinjau informasi yang Anda masukkan. Jika ada yang perlu dikoreksi, pilih opsi **Edit** yang sesuai dan buat koreksi yang diperlukan. Jika semua informasi sudah benar, pilih **Kirim**.

45. Pada halaman **Kebijakan baru dibuat**, pilih **Selesai**.


### Tugas 4 – Menetapkan Label Sensitivitas yang sudah ada sebelumnya pada sebuah dokumen

Seperti yang diuraikan dalam instruksi di awal lab ini, tidak mungkin untuk segera menguji label sensitivitas dan kebijakan label yang Anda buat di tugas sebelumnya. Ini karena diperlukan waktu hingga 24 jam agar kebijakan label baru disebarluaskan melalui Microsoft 365 dan agar labelnya terlihat dalam aplikasi seperti Microsoft Word dan Outlook.

Sebagai gantinya, Anda akan menguji salah satu label sensitivitas Microsoft 365 yang sudah ada sebelumnya. Untuk lab ini, Anda akan menggunakan label sensitivitas **Project - Falcon**, yang merupakan label Sangat Rahasia. Label ini mirip dengan label yang Anda buat di tugas sebelumnya - satu pengecualiannya adalah tidak menyertakan header atau footer. Menggunakan label yang sudah ada sebelumnya ini akan memberikan Anda gambaran yang baik tentang bagaimana label yang Anda buat akan bekerja di Adatum.

1. Di LON-CL1, di browser Edge, Anda masih harus masuk ke Microsoft 365 sebagai **Holly Dickson**.

2. Anda akan terlebih dahulu meninjau label sensitivitas **Project-Falcon** yang akan Anda terapkan ke dokumen dalam tugas ini.  Di browser Edge, Anda masih harus membuka tab untuk portal **Microsoft Purview** dari tugas sebelumnya. Di portal **Microsoft Purview**, di bawah grup **Perlindungan informasi** di panel navigasi, pilih **Label**. 

3. Pada halaman **Label**, dalam daftar label, pilih panah kanan (**>**) di samping **Sangat Rahasia** untuk memperlihatkan sub-label di bawah label ini. Melakukannya akan menampilkan label **Project - Falcon** yang sudah ada sebelumnya.

4. Pilih label **Project - Falcon** (bukan kotak centang; pilih nama label). Melakukannya akan membuka panel detail **Project - Falcon** . Tinjau informasi yang ditentukan untuk label ini, lalu tutup panel saat Anda selesai.  

5. Anda sekarang akan menetapkan label sensitivitas **Project-Falcon** ke dokumen. Pilih Tab **Beranda | Microsoft 365** di browser Anda untuk kembali ke beranda Microsoft 365. Pilih ikon **Aplikasi** di sisi kiri layar. Pada halaman **Aplikasi** yang muncul, klik kanan pada petak **Word** dan pilih **Buka di tab baru**. 

6. Di tab **Word | Microsoft 365**, di bawah bagian **Buat baru** di bagian atas halaman, pilih **Dokumen kosong**.

7. Jika jendela **opsi privasi Anda** muncul, pilih **Tutup**.

8. Jika pita Word menampilkan ikon untuk setiap fitur tetapi tidak memecah ikon menurut grup, maka pilih panah bawah di sisi paling kanan pita, lalu di bawah **Tata letak pita**, pilih **Pita Klasik**. Ini akan mengalihkan pita ke gaya pita tradisional yang dipecah menurut grup fitur (seperti Batalkan, Clipboard, Font, Paragraf, Gaya, dan sebagainya).

9. Dalam dokumen **Word**, ketik teks berikut: **Menguji label sensitivitas pada dokumen dengan informasi pengidentifikasi pribadi (PII); dalam hal ini, Nomor Jaminan Sosial AS: 111-11-1111.**

10. Karena Anda mengaktifkan label Sensitivitas di awal latihan ini, **Word** harus menampilkan grup **Sensitivitas** pada pita di bagian atas halaman. Pilih panah bawah dalam grup **Sensitivitas** . Di menu drop-down yang muncul, itu harus menampilkan daftar jenis label sensitivitas. Pilih **Sangat Rahasia**, lalu di sub-menu yang muncul, pilih **Project - Falcon**. <br/>

    **Catatan:** Setelah 24 jam, label yang Anda buat di tugas sebelumnya akan muncul di sub-menu Sangat Rahasia, di samping label Project-Falcon. Tetapi untuk saat ini, Anda akan menggunakan label **Project - Falcon** sebagai gantinya.

11. Dalam dokumen, perhatikan bagaimana label menerapkan marka air **CONFIDENTIAL - ProjectFalcon** di bagian atas dokumen. Label Project - Falcon dikonfigurasi sama seperti label yang Anda buat, di mana marka air seharusnya muncul secara diagonal di tengah halaman. Jadi mengapa muncul di bagian atas halaman? Jawabannya adalah Anda menggunakan **Word untuk Web**, yang secara default menampilkannya seperti yang Anda lihat di sini. Untuk melihat tampilannya dari seseorang yang membaca dokumen, Anda harus menampilkan dokumen dalam **Tampilan Baca**, yang akan Anda lakukan sekarang. <br/>

    Pilih tab **Tampilan** lalu di pita Word, pilih **Tampilan Baca**. Perhatikan bagaimana marka air muncul secara diagonal di tengah dokumen. Ini adalah bagaimana marka air akan tampil bagi seseorang yang membaca dokumen. Perhatikan bahwa jika Anda menggunakan aplikasi desktop Word, itu menampilkan marka air seperti yang ditunjuk oleh label, yang dalam hal ini akan sama seperti yang Anda lihat di sini dalam Tampilan Baca. <br/>

    Untuk keluar dari Tampilan Baca, pilih **Edit Dokumen** pada bilah menu di bagian atas halaman. Di menu drop-down yang muncul, pilih **Word**.

12. Dalam pengujian validasi pertama ini, Anda akan menghapus label sensitivitas ini agar tidak diterapkan ke dokumen ini. Salah satu opsi kebijakan label mewajibkan pengguna memberikan alasan untuk menghapus label atau memilih label klasifikasi yang lebih rendah. Anda sekarang akan memverifikasi apakah pengaturan ini berfungsi dengan baik. <br/>

    Di grup **Sensitivitas** di pita Word, pilih panah bawah. Di menu drop-down yang muncul, perhatikan bahwa tanda centang muncul di samping **Sangat Rahasia**. Tahan mouse Anda di atas **Sangat Rahasia** untuk menampilkan sub-menu. Perhatikan bagaimana tanda centang muncul di samping **Project - Falcon**. Tanda centang mengidentifikasi label saat ini yang diterapkan ke dokumen.  <br/>
 
    Untuk menghapus label dari dokumen ini, pilih label **Project - Falcon** yang muncul di menu drop-down ini.
    
13. Di jendela **Justifikasi Diperlukan** yang muncul, pilih opsi **Lainnya (jelaskan).** Di bidang **Jelaskan mengapa Anda mengubah label ini**, masukkan **Menguji apa yang terjadi saat label dihapus dari dokumen** lalu pilih **Ubah**.

14. Perhatikan bagaimana marka air dalam dokumen telah hilang. Di grup **Sensitivitas** di pita Word, pilih panah bawah. Di menu drop-down yang muncul, perhatikan bahwa saat **Proyek Sangat Rahasia** > **Project - Falcon** ditampilkan, tidak ada tanda centang yang muncul di sampingnya. Ini menunjukkan bahwa label sensitivitas tidak lagi diterapkan ke dokumen ini.  

15. Untuk menerapkan kembali label sensitivitas ke dokumen, pilih **Proyek Sangat Rahasia** > **Project - Falcon** di menu drop-down. Perhatikan bagaimana marka air muncul kembali dalam dokumen.

16. Anda sekarang akan menyimpan dokumennya sehingga Anda bisa membagikannya di tugas berikutnya. Bidang nama dokumen yang berisi panah turun bawah muncul di sudut kiri atas halaman, di sebelah kanan ikon Word (Word mungkin menampilkan **Dokumen** atau **Dokumen1** sebagai nama file sementara). Pilih panah drop-down. Di menu drop-down yang muncul, konfirmasikan **Lokasi** file menampilkan **Dokumen > Holly Dickson**. <br/>

    Di bidang **Nama File**, ganti nama file menjadi **ProtectedDocument1** lalu pilih di luar menu nama file ini (pilih di dalam dokumen). Perhatikan nama baru yang ditetapkan ke file muncul di bilah judul. 

17. Biarkan tab **ProtectedDocument1** terbuka menampilkan dokumennya. Anda akan kembali ke dokumen ini dalam tugas berikutnya untuk membagikan dokumennya dengan Joni Sherman.

Anda baru saja berhasil membuat dokumen Word yang berisi label Sangat Rahasia berjudul **Project - Falcon**. 


### Tugas 5 – Melindungi dokumen menggunakan Perlindungan Informasi Microsoft Purview

Dalam tugas sebelumnya, Anda membuat dokumen Word dan memproteksinya dengan label sensitivitas **Project - Falcon** . Label ini menyisipkan marka air dalam dokumen. Dalam tugas ini, Anda akan membagikan dokumen yang Anda buat dengan Joni Sherman, dan Anda akan membatasi Joni untuk izin "Lihat saja". Ini akan memungkinkan Anda untuk melihat bagaimana Microsoft Purview Information Protection melindungi dokumen berdasarkan parameter yang Anda konfigurasikan.

Untuk memverifikasi apakah perlindungan yang Anda tetapkan ke dokumen berfungsi, Anda akan terlebih dahulu mengirim dokumen melalui email kepada dua orang - ke Joni Sherman dan ke alamat email pribadi Anda sendiri. Anda kemudian akan memverifikasi bahwa Joni hanya dapat melihat dokumen dan tidak mengeditnya, dan Anda akan memverifikasi bahwa Anda tidak dapat mengakses dokumen karena tidak dibagikan dengan Anda. Terakhir, Anda akan mengubah izin pada dokumen sehingga Joni dapat mengeditnya, dan Anda akan mengirim dokumen yang diperbarui ini melalui email kepadanya untuk pengujian. Tujuan dari dua email ke Joni ini, satu dengan tautan dokumen yang menyediakan akses baca-saja dan yang lain dengan tautan dokumen yang menyediakan kemampuan untuk mengedit dokumen, adalah untuk melihat bagaimana Microsoft Entra ID Protection dapat menyediakan berbagai tingkat perlindungan dokumen. 

1. Di LON-CL1, di browser Edge Anda, Anda masih harus masuk ke Microsoft 365 sebagai **Holly Dickson** dari tugas sebelumnya dengan tab **Word** terbuka.

2. Di browser Edge Anda, pilih tab **Aplikasi | Microsoft 365**. 

3. Di halaman **Aplikasi**, klik kanan pada petak **Outlook** dan pilih **Buka di tab baru**. Ini membuka kotak surat Holly di Outlook di web pada tab browser baru. 

4. Pada **Outlook di Web**, pilih **Email baru** di bagian atas layar.

5. Sertakan informasi berikut dalam formulir email:

    - Kepada: Masukkan **Joni** lalu pilih **Joni Sherman** dari daftar pengguna. 

    - CC: Masukkan alamat email pribadi Anda sendiri (JANGAN masukkan alamat email Holly; sebagai gantinya, masukkan alamat email pribadi Anda sendiri), lalu pilih pesan **Gunakan alamat ini: <your email address>** yang muncul

    - Menambahkan subjek: **Pengujian Dokumen Terproteksi - Izin hanya lihat **

    - Isi pesan: masukkan **Buka dokumen terproteksi yang dilampirkan ke email ini dan coba ubah.**

6. Di isi pesan, di bawah teks yang Anda tambahkan di langkah sebelumnya, Anda akan melampirkan tautan ke dokumen yang Anda buat di tugas sebelumnya. Namun, untuk melakukannya, Anda harus terlebih dahulu berbagi dokumen dengan Joni Sherman, dan ketika melakukannya, Anda akan menerapkan izin **Hanya lihat** yang dibatasi. Untuk melakukannya, Anda harus meninggalkan email ini dan kembali ke dokumen Anda dan membagikannya dengan Joni. Setelah menyalin tautan yang dibuat selama proses berbagi, Anda akan kembali ke email ini dan menempelkan tautan tersebut. <br/>

    Di browser Edge Anda, pilih tab **ProtectedDocument1** , yang seharusnya masih menampilkan dokumen yang Anda buat di tugas sebelumnya. Di sisi kanan atas halaman, di bawah nama dan inisial Holly Dickson, pilih tombol **Bagikan**. Di menu drop-down yang muncul, pilih **Bagikan**.

7. Di jendela **Bagikan "ProtectedDocument1"** yang muncul, pilih ikon gerigi (**Pengaturan tautan**) yang muncul di samping tombol **Salin tautan**. 

8. Pada jendela **Pengaturan tautan** yang muncul, pilih opsi **Orang yang Anda pilih**.
    
9. Di bawah **Pengaturan lainnya**, opsi saat ini adalah **Bisa mengedit**. Anda berencana untuk berbagi dokumen ini dengan Joni Sherman, tetapi Anda hanya ingin Joni bisa melihat dokumen saja. Untuk membuat perubahan izin ini, pilih **Bisa mengedit**. Di menu yang muncul, tinjau opsi yang tersedia. Anda dapat melihat bahwa **Dapat mengedit** memiliki tanda centang di sampingnya, yang menunjukkan ini adalah pengaturan saat ini. Untuk membatasi Joni ke izin hanya baca, pilih **Bisa melihat** lalu pilih **Terapkan**.

10. Ini mengembalikan Anda ke jendela **Bagikan "ProtectedDocument1"** . Masukkan **Joni** di Bidang **Tambahkan nama, grup, atau email** . Daftar pengguna yang namanya dimulai dengan **Joni** akan muncul. Pilih **Joni Sherman**.

11. Pada jendela **Bagikan "ProtectedDocument1"** , arahkan mouse Anda ke atas ikon "mata" yang muncul di sebelah kanan nama Joni. Melakukannya akan menampilkan **Dapat melihat**, yang merupakan pengaturan saat ini yang Anda tetapkan kepadanya untuk dokumen ini. Ikon "mata" adalah sebutan untuk "Dapat melihat". Pilih tombol **Salin tautan**. 

12. Setelah pesan **Tautan disalin** muncul di bagian bawah jendela **Bagikan "ProtectedDocument1"**, lalu pilih X di sudut atas jendela untuk menutupnya.

13. Di browser Edge Anda, pilih tab **Email - Holly Dickson -Outlook** untuk kembali ke pesan email Anda. Di isi pesan, di bawah teks yang Anda tambahkan sebelumnya, tempelkan (Ctrl+V) di tautan ke dokumen bersama yang baru saja Anda salin ke clipboard Anda. Tautan untuk file bernama **ProtectedDocument1.docx** akan muncul. 

14. Pilih **Kirim**.

15. Pesan **Penerima tidak dapat mengakses tautan** akan muncul. Pesan ini adalah hasil dari Microsoft Entra ID Protection yang mengenali fakta bahwa Anda menyertakan alamat email pribadi Anda dalam email, yang tidak memiliki izin untuk mengakses dokumen. Untuk tujuan pengujian lab ini, pilih **Tetap kirim**.

16. Beralih ke **LON-CL2**. 

17. Pada **LON-CL2**, Anda harus masuk ke **Outlook di Web** sebagai **Lynne Robbins** dari latihan lab sebelumnya. Keluar sebagai Lynne.

18. Di browser Edge Anda, tutup semua tab kecuali untuk tab **Keluar** . Di tab ini, masukkan URL berikut di bilah alamat: **https://outlook.office365.com** 

19. Di jendela **Pilih akun** , pilih **Gunakan akun lain**.

20. Di jendela **Masuk**, masukkan **JoniS@xxxxxZZZZZZ.onmicrosoft** (di mana xxxxxZZZZZZ adalah prefiks penyewa yang diberikan oleh penyedia host lab Anda), lalu pilih **Berikutnya**.

21. Pada jendela **Masukkan kata sandi**, masukkan Kata Sandi Pengguna Baru yang sebelumnya Anda tetapkan ke akun Joni lalu pilih **Masuk**. 

22. Jika jendela **Selamat Datang** muncul, pilih X untuk menutupnya.

23. Di **Kotak Masuk** Joni di **Outlook di Web**, Anda akan melihat email yang baru saja dikirim Holly yang baris Subjeknya menunjukkan dokumen hanya memiliki izin Hanya lihat. Buka email ini.

24. Di email, pilih file terlampir untuk membukanya.

25. Di jendela **Opsi privasi Anda** yang muncul, pilih **Tutup**. Dokumen terbuka di **Word di Web** di tab browser baru berjudul tab ** ProtectedDocument1.docx**. Perhatikan bagaimana dokumen muncul dalam Tampilan Baca di **Word di Web**. Ini adalah indikasi Joni bahwa dia hanya memiliki izin Hanya lihat dan tidak dapat mengedit dokumen. Untuk memverifikasi ini, coba pilih dokumen tersebut. Perhatikan pesan yang muncul menunjukkan: **Hanya baca. Dokumen ini bersifat baca-saja.** Perhatikan marka air yang ditentukan dalam **kebijakan Project - Falcon** . <br/>

    Setelah Anda selesai meninjau dokumen, tutup tab **ProtectedDocument1.docx** . 

26. Anda sekarang akan menguji apa yang terjadi ketika Anda mencoba membuka dokumen yang dikirim ke alamat email pribadi Anda. Gunakan ponsel atau PC kelas Anda untuk mengakses kotak surat pribadi Anda. Buka email yang baru saja dikirim Holly ke alamat email pribadi Anda, lalu coba buka file terlampir. 

27. Karena Anda tidak memiliki izin untuk mengakses dokumen, jendela **Pilih akun** akan muncul. Dalam skenario dunia nyata, Anda dapat secara opsional masuk dengan akun yang memiliki izin untuk mengakses file, atau meminta akses dari **Holly@xxxxxZZZZZZ.onmicrosoft.com** akun tersebut. <br/>

    Untuk tujuan pengujian ini, Anda baru saja memverifikasi bahwa Anda tidak dapat mengakses file karena tidak dibagikan dengan Anda. Anda juga memverifikasi bahwa Joni hanya dapat melihat file, tetapi tidak mengeditnya. Anda sekarang akan mengubah izin Bagikan pada file dengan mengizinkan Joni mengeditnya. Anda akan melakukannya untuk melihat bagaimana pengalaman ini berbeda dari yang baru saja Anda selesaikan. 

28. Beralih ke **LON-CL1**. 

29. Di LON-CL1, di browser Edge Anda, Anda masih harus masuk ke Microsoft 365 sebagai **Holly Dickson**, dan Anda harus membuka tab untuk **Word** dan **Outlook**. Pilih tab **Email - Holly Dickson - Outlook** . 

30. Di kotak surat Holly, buat email lain ke Joni Sherman. JANGAN sertakan alamat email pribadi Anda di baris CC. Sertakan informasi berikut dalam formulir email:

    - Kepada: Masukkan **Joni** lalu pilih **Joni Sherman** dari daftar pengguna. 

    - CC: Biarkan kosong.

    - Menambahkan subjek: **Pengujian Dokumen Terproteksi - Izin edit**

    - Isi pesan: masukkan **Buka dokumen terproteksi yang dilampirkan ke email ini dan coba ubah.**

31. Sama seperti email sebelumnya, Anda sekarang harus berbagi dokumen dengan Joni, tetapi kali ini dengan izin Edit. Lakukan langkah-langkah berikut: <br/>

    - Pilih tab **ProtectedDocument1** di browser Anda lalu di sisi kanan bilah menu pilih tombol **Bagikan**. Di menu drop-down yang muncul, pilih **Bagikan**. 
    - Di jendela **Bagikan "ProtectedDocument1"** , masukkan **Joni** di bidang **Tambahkan nama, grup, atau email** lalu pilih **Joni Sherman**.
    - Di sebelah kanan nama Joni terdapat ikon pensil (**Bisa mengedit**). Ini adalah izin default saat berbagi dokumen. Pilih tombol **Salin tautan** untuk melihat apa yang terjadi.
    - Perhatikan pesan **Link yang disalin** yang muncul. Pesan menunjukkan bahwa siapa pun dapat mengedit dokumen, meskipun Anda menentukan nama Joni. Ini bukan yang Anda inginkan, yaitu membatasi Joni sebagai satu-satunya orang yang dapat mengeditnya. Untuk menempatkan pembatasan tersebut, pilih ikon gigi (**Pengaturan tautan**) di samping tombol **Salin tautan** . 
    - Pada jendela **Pengaturan tautan** yang muncul, pilih opsi **Orang yang Anda pilih**. Opsi ini adalah kunci untuk membatasi izin kepada pengguna yang dipilih. 
    - Di bawah **Pengaturan lainnya**, jika **Bisa mengedit** muncul, maka pilih **Terapkan**. Namun, jika **Bisa lihat** muncul, maka pilih **Bisa lihat**, dan di menu yang muncul, pilih **Bisa mengedit** lalu pilih **Terapkan**. 
    - Di jendela **Bagikan "ProtectedDocument1"** , pilih tombol **Salin tautan** .
    - Perhatikan pesan **Link yang disalin** yang muncul. Kali ini pesan menunjukkan bahwa hanya orang yang Anda tentukan yang dapat mengedit dokumen. Dalam hal ini, pengeditan akan terbatas pada Joni, karena dia satu-satunya orang yang Anda tentukan. 
    - Pilih tab **Email - Holly Dickson - Outlook** di browser Anda lalu tempelkan tautan ke dalam isi pesan email. 

32. Pilih **Kirim**.

33. Beralih ke **LON-CL2**. 

34. Di **LON-CL2**, Anda masih harus masuk ke **Outlook di Web** sebagai **Joni Sherman**. Di **Kotak Masuk** Joni, Anda akan melihat email yang baru saja dikirim Holly yang baris Subjeknya menunjukkan dokumen memiliki izin Edit. Buka email ini.

35. Di email, pilih file terlampir untuk membukanya.

36. Ketika Joni hanya memiliki izin Hanya lihat, dokumen dibuka di panel Tampilan Baca. Dengan demikian, Joni tidak dapat mengedit dokumen. Versi dokumen ini memberi Joni izin Edit, jadi kali ini dokumen akan terbuka di Word dalam mode edit normal. Verifikasi bahwa Anda bisa memasukkan teks dalam dokumen. 

    **Catatan:** Dalam tugas ini, Anda baru saja memverifikasi bahwa Microsoft Purview Information Protection melindungi dokumen berdasarkan parameter kebijakan PII yang Anda konfigurasikan. Ketika Joni diberi izin Hanya lihat, dokumen dibuka dalam tampilan Baca dan dia tidak dapat mengubahnya. Ketika Joni diberi izin Edit, dokumen tersebut dibuka di Word dan dia bisa mengubahnya. Dan karena Holly tidak berbagi dokumen dengan Anda, Anda tidak dapat membukanya saat dia mengirim dokumen dalam email ke kotak surat pribadi Anda. 

## Akhir Lab 3


# Selamat! Anda baru saja menyelesaikan lab akhir dalam kursus ini.
