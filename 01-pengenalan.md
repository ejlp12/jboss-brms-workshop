Sebelum memulai workshop, sebaiknya ada mengerti konsep-konsep berikut
 - Business Rule Management System (BRMS) atau Rule Engine
 - Complex Event Processing (CEP)
 - Business Process Management (BPM)

Sebaiknya anda browsing dan baca-baca dulu, dan atau melihat file presentasi berikut:

[Introduction to JBoss BRMS and BPM Suite](http://bpmworkshop-onthe.rhcloud.com/introduction.html#/)

Pada workshop ini kita akan menggunakan produk __Red Hat JBoss BRMS__ versi 6.0 dengan materi sebagai berikut: 

 1. The introduction and installation of JBoss BRMS 
 2. Creating a new project
 3. Creating a domain model
 4. Creating a Domain Specific Language (DSL)
 5. Creating Guided Rules
 6. Creating Technical Rules (DRL)
 7. Creating Guided Decision Tables
 8. Create RuleFlow Process
 9. Create Test Scenarios
10. Running the Cool Store

Apa yang akan dibuat?
---------------------

Anggaplah anda mendapatkan proyek dari RodHot untuk membuat aplikasi online web shopping sebutlah namanya __Cool Store__. 
Aplikasi tersebut akan menampilkan barang yang dijual, sehingga calon pembeli bisa memilih barang yang akan dibeli. 
Tampilan halaman web akan dibuat sederhana seperti ini:

![Tampilan Web Cool Store](http://2.bp.blogspot.com/-X64UDSwHcxo/Ux8rHmJbA-I/AAAAAAAAVOk/Xgn2fRUjbAo/s1600/coolstore-shoppingcart.png)


Pada aplikasi tersebut, RodHot ingin mengimplementasikan mekanisme diskon pada pembeli sebagai sarana promosi. Tentu saja
promosi diskon ini akan berubah-ubah besarannya atau aturannya (rule).

Anda tidak perlu punya kemampuan untuk programming web, tidak perlu menguasai HTML, CSS, JavaScript maupun Java, karena bagian
web user interface (UI) sudah dibuat dan komponen UI sudah dibuat agar dapat memanggil JBoss BRMS untuk mengeksekusi aturan 
promosi diskon.

Yang akan anda buat adalah membuat aturan proposi diskon di JBoss BRMS.

Bagaimana aturan yang akan dibuat?
----------------------------------



