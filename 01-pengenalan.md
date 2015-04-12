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
perhitungan harga pengiriman barang dan promosi atau diskon.

Yang akan anda buat adalah membuat business rule dari harga pengiriman barang dan promosi diskon di JBoss BRMS.

Bagaimana aturan yang akan dibuat?
----------------------------------
Begini..
Karena setiap pembelian barang, barang akan dikirim lewat perusahaan shipping (3rd party) maka setiap barang yang dibeli
ada biaya pengiriman barang. Semakin banyak atau mahal barang yang dibeli maka biaya pengiriman semakin besar.

Aturannya standarnya adalah seperti ini, jika jumlah pembelian barang antara  0 atau lebih kecil dari $25 maka biaya 
pengiriman adalah $2.99. Jika pembelian antara $25 atau lebih kecil dari $50 maka biaya pengiriman adalah $4.99.
Dan seterusnya seperti tertera pada tabel berikut:

No.  | Deskripsi        | Total        | Total       | Biaya 
     |                  | pembelian >= | pembelian < | Pengiriman 
=====|==================|==============|=============|============
1    | Shipping Tier 1  |            0 |         25  |   2.99
2    | Shipping Tier 2  |           25 |         50  |   4.99
3    | Shipping Tier 3  |           50 |         75  |   6.99
4    | Shipping Tier 4  |           75 |        100  |   8.99
5    | Shipping Tier 5  |          100 |    1000000  |  10.99


Supaya menarik pembeli agar membeli lebih banyak item, maka saat ini RodHot akan memberikan potongan untuk biaya pengiriman barang jika total pembelian sama dengan atau lebih besar dari $75 maka biaya pengirimannya __gratis__. Jadi pembelian diatas $75, biaya pengirimannya bukan lagi $8.99 atau $10.99 seperti terlihat pada tabel diatas.









