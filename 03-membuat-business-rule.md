# Penjelasan awal

Pada latihan ini kita akan mencoba membuat business rule dari nol. Sebelumnya saya jelaskan dulu beberapa jenis cara membuat business rule. Rule dapat dibuat dalam beberapa bentuk agar memudahkan orang bisnis untuk membuatnya:

1. Kode scripting dengan dialek MVEL atau JAVA. File scripting ini disebut DRL (berasal dari kata Drools Langunage)
2. Decision table yaitu bentuk tabel dengan kombinasi beberapa varibel yang ditampilkan dalam kolom-kolom dan nilai yang diset pada setiap sel (row)
3. Guided rule dimana kita di-guide (dipandu) untuk membuat rule sehingga lebih mudah dibanding kode scripting
4. Decision tree yaitu alur logika yang direpresentasikan dalam bentuk pohon
5. Rule flow atau decision flow yaitu menggabungkan beberapa rule dalam bentuk alir proses


Untuk membuat rule kita bisa gunakan dua alat berikut:

* Web user interface yaitu __business-central__ yang bisa diakses di [http://localhost:8080/business-central](http://localhost:8080/business-central)
* JBoss Developer Studio (JBDS) yaitu IDE berbasis Eclipse.

# Membuat rule menggunakan Business Central

## Membuat organization & repository

## Membuat project

## Membuat data object

Data object adalah model data (business data) yang akan terlibat dalam eksekusi rule. Data object sebenarnya adalah POJO (Plain Old Java Object), sebuah class Java sederhana, dengan sedikit annotation. Untuk seorang programmer membuat class Java sederhana bukanlah masalah tetapi untuk orang binis hal tersebut jadi masalah. Di Business Central, pengguna (orang bisnis) dapat membuat data object dengan mudah tanpa perlu coding.

## Membuat rule

## Men-deploy project

### Mendaftarkan (register) rule server

### Membuat rule container

## Mengakses rule engine (Ekseksusi rule)





