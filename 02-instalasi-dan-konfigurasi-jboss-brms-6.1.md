Materi ini bersumber dari materi Quickstart yang bisa anda akses disini: [http://www.jboss.org//quickstarts/brms/index.html](http://www.jboss.org//quickstarts/brms/index.html)

# Instalasi dan Mengkonfigurasi JBoss BRMS

Pastikan Java 1.8 dan Maven sudah terinstal di komputer anda.

1. Download BRMS 6.1.0 dari Red Hat Customer Portal atau dari JBoss.org

  Opsi #1:
  - Jika anda Login ke Red Hat Customer Portal di [https://access.redhat.com/jbossnetwork/restricted/listSoftware.html/](https://access.redhat.com/jbossnetwork/restricted/listSoftware.html/)
  - Pilih BRMS dari daftar produk Business Automation Platforms 
  - Cari **Red Hat JBoss BRMS 6.1.0 Installer** dari daftar file dan kemudian klik Download
  - Simpan file installer `jboss-brms-installer-6.1.0.GA-redhat-<version>.jar` di direktori lokal  

  Opsi #2:
  - Buka halaman JBoss BRMS di [https://www.jboss.org/products/brms.html/](https://www.jboss.org/products/brms.html/)
  - Pilih Download JBoss BRMS 6.1.0, login atau buat account baru lalu setujui *download terms and conditions*.
  - Simpan file installer `jboss-brms-installer-6.1.0.GA-redhat-<version>.jar` di direktori lokal 

2. Jalankan installer dengan perintah `java -jar jboss-brms-installer-6.1.0.GA-redhat-<version>.jar`.

   Sebuah window installer wizard akan muncul dan anda dapat dengan mudah mengikuti langkah-langkahnya dengan mengklik tombol Next
   
   ![image](https://cloud.githubusercontent.com/assets/3068071/11017298/1d4cd946-85cd-11e5-8882-d2450f11d150.png)
   
   
   Jika anda instalasi dalam mode console atau di komputer yang tidak memiliki Window Manager, anda dapat menjalankan installer dengan mode console yaitu dengan perintah:
   
   `java -jar jboss-brms-installer-6.1.0.GA-redhat-<version>.jar -console`
   
   > Misal anda memilih lokasi instalasi di `/Server/BRMS-6.1`, pada artikel ini tempat tersebut akan saya sebut sebagai `$ROOT_DIR` untuk memudahkan.
   
   > Setelah selesai instalasi, direktori BRMS akan berlokasi di direktori `$ROOT_DIR/jboss-eap-6.4/`. Untuk memudahkan direktori tersebut saya sebut sebagai `$EAP_HOME`

3. Tambahkan user aplikasi 
   
   Di Linux:   
   
   ```
   $EAP_HOME/bin/add-user.sh -a -u 'quickstartUser' -p 'P@ssw0rd' -ro 'admin,analyst'
   ```
   
   Di Windows: 
   
   ```
   $EAP_HOME\bin\add-user.bat  -a -u 'quickstartUser' -p 'P@ssw0rd' -ro 'admin,analyst'
   ```

4. Jalankan JBoss BRMS. 

   Buka console atau command prompt lalu masuk ke direktori root dari JBoss server (EAP_HOME)
   
   Di Linux:   `$EAP_HOME/bin/standalone.sh`
   
   Di Windows: `EAP_HOME\bin\standalone.bat`

# Test instalasi dengan menjalankan project quickstart

1. Impor BRMS Repository yang berisi sample projects 
  
   - Pastikan JBoss BRMS sudah dijalankan dengan perintah diatas. Lalu buka web browser dan akses [http://localhost:8080/business-central](http://localhost:8080/business-central)
   - Log in dengan credentials berikut:
      
      
      * Username: `quickstartUser`
      * Password: `P@ssw0rd`
      
      
   - Pilih menu  *Authoring* -> *Administration*
   - Pilih sub-menu *Repositories* -> *Clone repository*
   - Isi form seperti sesuai informasi berikut:

      ```
      Repository Name:      jboss-brms-repository
      Organizational Unit:  example
      Git URL:              file:///path/to/jboss-brms-repository
      or
      Git URL:              https://github.com/jboss-developer/jboss-brms-repository.git
      User Name:            <leave blank>
      Password:             <leave blank>
      ```
      
   - Klik tombol *Clone*. Jika berhasil meng-clone repository anda akan mendapatkan pesan "The repository is cloned successfully".
   
   > Anda dapat juga meng-clone repository dengan menggunakan perintah `git` ke direktori lokal dahulu lalu baru meng-clone ke BRMS
   > 
   > ```
   > cd /path/to/
   > git clone jboss-brms-repository
   > ```

2. Pilih menu *Authoring* -> *Project Authoring*
3. Navigasikan Project Explorer ke path berikut:

   ```
   Organizational Unit:     example
   Repository Name:         jboss-brms-repository
   BRMS Kmodule (Project):  helloworld-brms-kmodule
   ```
   
   ![image](https://cloud.githubusercontent.com/assets/3068071/11017536/ac5bcb36-85d4-11e5-8218-cb7b64a7c413.png)
   
   Untuk melihat aset (artifacts) dari project klik tanda `[+]` disebelah kanan path `example/jboss-brms-repository/helloworld-brms-kmodule` untuk melihat struktur direktori dari project tersebut, lalu ekspansikan directory explorer tersebut sampai ke direktori `<default>/org/jboss/quickstart/brms`. Hasilnya aset akan muncul di Project Explorer yaitu beberapa Data Object, Enumeration Definitions dan Guided Rules.


4. Klik tombol *Project Editor* di Project Explorer, kemudian di window sebelah kanan klik *Build* -> *Build & Deploy*

   ![image](https://cloud.githubusercontent.com/assets/3068071/11017539/c3e01d66-85d4-11e5-878e-6aaf882ba9d2.png)
   
   Anda akan mendapatkan pesan: "Also save possible changes to project?". Klik Yes.
   Kemudian akan diminta memasukan komentar. Isi komentar kemduaian klik tombol Save.
   
   Proses ini akan membuat artifact `helloworld-brms-kmodule-1.0.0.jar`ke BRMS Maven repository. 
   Anda bisa verifikasi dengan melihat di menu *Authoring* –> *Artifact Repository*
   
   ![image](https://cloud.githubusercontent.com/assets/3068071/11023189/6b6886e8-86a4-11e5-845f-bc6ceaeb3e45.png)
   
   Proses tersebut juga akan men-deploy artifact tersebut ke BRMS Runtime Engine, anda bisa verifikasi dengan melihat di halmanan Deployment, klik menu *Deploy* -> *Process Deploymnet*. Anda akan lihat sebuah deployment dengan nama `org.jboss.quickstarts.brms:helloworld-brms-kmodule:1.0.0` ada di daftar.
   
   ![image](https://cloud.githubusercontent.com/assets/3068071/11023197/b4b0020e-86a4-11e5-9c28-a6b16456789a.png)
   
