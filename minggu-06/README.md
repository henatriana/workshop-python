## Workshop Python Pertemuan 6 Tutorial 8 (Source : https://docs.python.org/3/tutorial/errors.html)

# 8. Errors and Exceptions
Ada (setidaknya) dua jenis kesalahan yang dapat dibedakan: *syntax errors* dan *exceptions*.

## 8.1. Syntax Errors
Kesalahan sintaksis, juga dikenal sebagai kesalahan parsing.

Parser mengulangi garis yang menyinggung dan menampilkan sedikit ‘panah’ yang menunjuk pada titik paling awal di garis tempat kesalahan terdeteksi. Kesalahan disebabkan oleh (atau setidaknya terdeteksi pada) token sebelum panah: dalam contoh, kesalahan terdeteksi pada fungsi cetak (), karena titik dua (':') hilang sebelum itu. Nama file dan nomor baris dicetak sehingga Anda tahu ke mana harus mencari seandainya input berasal dari skrip.

## 8.2. Exceptions
Bahkan jika suatu pernyataan atau ungkapan secara sintaksis benar, itu dapat menyebabkan kesalahan ketika suatu usaha dilakukan untuk menjalankannya. Kesalahan yang terdeteksi selama eksekusi disebut *exceptions* dan tidak berakibat fatal.

Baris terakhir dari pesan kesalahan menunjukkan apa yang terjadi. Exceptions ada dalam tipe berbeda, dan tipe dicetak sebagai bagian dari pesan: tipe dalam contoh adalah ZeroDivisionError, NameError dan TypeError. String yang dicetak sebagai jenis exceptions adalah nama exceptions bawaan yang terjadi. Ini berlaku untuk semua exceptions bawaan, tetapi tidak harus benar untuk exceptions yang ditentukan pengguna (meskipun ini adalah konvensi yang bermanfaat). Nama exceptions standar adalah pengidentifikasi bawaan (bukan kata kunci yang dipesan).

Sisa dari baris memberikan detail berdasarkan jenis pengecualian dan apa yang menyebabkannya.

Bagian sebelumnya dari pesan kesalahan menunjukkan konteks di mana pengecualian terjadi, dalam bentuk stack traceback. Secara umum berisi baris sumber traceback daftar stack; namun, ini tidak akan menampilkan baris yang dibaca dari input standar.

Built-in Exceptions mencantumkan built-in exceptions dan artinya.

## 8.3. Handling Exceptions
Pernyataan *try* berfungsi sebagai berikut:
- Pertama, klausa try (pernyataan) antara try dan kata kunci except) dieksekusi.
- Jika tidak ada exceptions terjadi, kalusa except dilewati dan eksekusi pernyataan try selesai.
- Jika exceptions terjadi selama eksekusi klausa try, sisa klausa dilewati. Kemudian jika jenisnya cocok dengan exceptions yang dinamai dengan kata kunci except, klausa kecuali dijalankan, dan kemudian eksekusi berlanjut setelah pernyataan try.
- Jika exceptions terjadi yang tidak cocok dengan exceptions yang disebutkan dalam klausa except, itu diteruskan ke pernyataan try luar; jika tidak ada yang ditemukan, itu adalah exceptions yang tidak tertangani dan eksekusi berhenti dengan pesan.

Pernyataan try mungkin memiliki lebih dari satu klausa except, untuk menentukan penangan untuk exceptions yang berbeda. Paling banyak satu penangan akan dieksekusi. Penangan hanya menangani exceptions yang terjadi pada klausa try yang sesuai, bukan pada penangan lain dari pernyataan try yang sama.

Kelas dalam klausa except cocok dengan exception jika kelasnya sama atau kelas dasarnya (tetapi bukan sebaliknya - klausa yang mencantumkan kelas turunan tidak kompatibel dengan kelas dasar).

Pernyataan try ... except memiliki klausa opsional lain, yang, jika ada, harus mengikuti semua klausa except. Ini berguna untuk kode yang harus dijalankan jika klausa try tidak menimbulkan exception.

Penggunaan klausa else lebih baik daripada menambahkan kode tambahan ke klausa try karena klausa menghindari secara tidak sengaja menangkap pengecualian yang tidak dimunculkan oleh kode yang dilindungi oleh try ... except pernyataan.

Klausa except dapat menentukan variabel setelah nama exception. Variabel terikat ke instance exception dengan argumen yang disimpan di instance.args. Untuk kenyamanan, instance exception mendefinisikan __str __ () sehingga argumen dapat dicetak langsung tanpa harus merujuk .args. Seseorang juga dapat membuat instantiate exception terlebih dahulu sebelum menaikkannya dan menambahkan atribut apa pun yang diinginkan.

## 8.4. Raising Exceptions
Pernyataan *raise* memungkinkan programmer untuk memaksa pengecualian yang ditentukan terjadi.

## 8.5. User-defined Exceptions
Program dapat memberi nama exception sendiri dengan membuat kelas exception baru. Exceptions biasanya berasal dari kelas Exceptions, baik secara langsung maupun tidak langsung.

## 8.6. Defining Clean-up Actions
Pernyataan try memiliki klausa opsional lain yang dimaksudkan untuk mendefinisikan tindakan clean-up yang harus dijalankan dalam semua keadaan.

Jika ada klausa finally, klausa finally akan dieksekusi sebagai tugas finally sebelum pernyataan try selesai. Klausa finally berjalan apakah pernyataan try menghasilkan exception atau tidak. Poin-poin berikut membahas kasus yang lebih kompleks ketika exception terjadi:
- Jika exception terjadi selama eksekusi klausa try, exception dapat ditangani oleh klausa *except*. Jika exception tidak ditangani oleh klausa except, exception akan muncul kembali setelah klausa finally telah dieksekusi.
- Exception dapat terjadi selama eksekusi klausa except atau else. Sekali lagi, exception akan dimunculkan kembali setelah klausa finally telah dieksekusi.
- Jika pernyataan try mencapai break, continue atau return pernyataan, klausa finally akan mengeksekusi tepat sebelum eksekusi pernyataan break, continue atau rerturn.
- Jika klausa finally menyertakan pernyataan pengembalian, nilai yang dikembalikan akan menjadi salah satu dari finally klausa pernyataan return, bukan nilai dari try pernyataan  klausa return.

## 8.7. Predefined Clean-up Actions
Pernyataan with memungkinkan objek seperti file untuk digunakan dengan cara yang memastikan mereka selalu dibersihkan dengan cepat dan benar.