# LIBSVM_PREON32
# Profil
Nama : Qolbi Fathurrohim
Judul Skripsi : Porting LIBSVM ke Node Sensor Preon32
Dosen Pembimbing : Elisati Hulu, M.T
# Deskripsi
Program ini adalah program yang diporting dari program LIBSVM dengan menyesuaikan kode yang hanya dibutuhkan dan sesuai dengan lingkungan sensor saja,
dalam hal ini hanya fungsi prediksi pada LIBSVM yang digunakan. Progam ini tidak memiliki tampilan antar muka, karena nantinya ketika dilapangan,
program ini akan berjalan otomatis, dan hanya nilai yang dihasilkannya saja yang akan diambil untuk dikumpulkan pada base station. 
Namun agar dapat melihat hasil prediksi, dibutuhkan komputer dan preon32 itu sendiri karena hasil programnya akan ditampilkan melalui jendela console.
Sensor akan sensing data sesuai keadaan suhu, kelembaban udara, dan tekanan udara disekitarnya, 3 variable tersebut akan menjadi sebuah masukan untuk memprediksi apakah yang disensing oleh sensor itu menyatakan siang(1.0) atau malam(0.0).
# Perangkat Lunak yang Dibutuhkan
1. Eclipse IDE
2. Preon32 Sandbox
3. JRE
# Perangkat Keras yang Dibutuhkan
1. Desktop/Laptop PC
2. Kabel USB Tipe A versi 2.0 male ke USB Tipe micro-A 2.0 male
3. Node Sensor Preon32
# Penjelasan Program
Pada repositori ini terdapat 3 folder berbeda, yang membedakan adalah kernel yang dipakai untuk memprediksi.
Saat ini hanya folder dengan kernel Linear yang dapat menghasilkan nilai prediksi yang akurat.
Sementara pada Polynomial, program dapat berjalan hanya saja menghasilkan nilai prediksi yang tidak tepat jika dibandingkan dengan program asli LIBSVM yang dijalankan pada komputer.
Sementara pada RBF, program sama sekali tidak dapat berjalan, dugaan saat ini adalah karena Support Vector yang digenerate pada saat melakukan Train terlalu banyak (Lebih dari 100 baris) sehingga sensor tidak mampu untuk mengolah datanya.
# Cara Menjalankan
1. Buka program Eclipse, lalu import folder program Linear sebagai existing project
2. Hubungkan sensor dengan komputer
3. Lihat comport pada Device Manager
4. Buka file context.properties pada folder config
5. Cocokan mainClass.name dengan file java yang berada pada folder src
6. Beri nama modul sesingkat mungkin pada module.name
7. Cocokan comport pada Device Manager pada comport dalam file
8. (jika belum) Tambahkan buildfiles pada apache ant
9. Pada buildfiles/apache ant, jalankan fungsi devel.clean
10. Lalu compile kembali menggunakan fungsi devel.all
11. Upload module yang sudah dicompile menggunakan fungsi cmd.module.upload.run
12. Program akan langsung menjalankan fungsi prediksi LIBSVM.
