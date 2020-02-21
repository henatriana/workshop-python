## Workshop Python Pertemuan 3 Tutorial 5 (Source : https://docs.python.org/3/tutorial/datastructures.html)
---

# 5. Data Structures
---

## 5.1. More on Lists
Tipe data list memiliki beberapa method. Berikut ini method list objek :
- list.append(x)
- list.extend(iterable)
- list.insert(i, x)
- list.remove(x)
- list.pop([i])
- list.clear()
- list.index(x[, start[, end]])
- list.count(x)
- list.sort(key=None, reverse=False)
- list.reverse()
- list.copy()

### 5.1.1. Using Lists as Stacks
Method pada list membuatnya sangat mudah untuk menggunakan list sebagai stack, di mana elemen terakhir yang ditambahkan adalah elemen pertama yang diambil ("last-in, first-out"). Untuk menambahkan item ke bagian atas stack, gunakan append (). Untuk mengambil item dari atas stack, gunakan pop () tanpa indeks eksplisit.

### 5.1.2. Using Lists as Queues
Dimungkinkan juga untuk menggunakan list sebagai queue, di mana elemen pertama yang ditambahkan adalah elemen pertama yang diambil ("first-in, first-out"); namun, list tidak efisien untuk tujuan ini. Sementara appends dan pops dari akhir list cepat, melakukan memasukkan atau pops dari awal list lambat (karena semua elemen lain harus digeser satu). Untuk mengimplementasikan queue, gunakan collections.deque yang dirancang untuk append cepat dan pops dari kedua ujung.

### 5.1.3. List Comprehensions
List comperhensions menyediakan cara singkat untuk membuat list. Aplikasi umum adalah membuat list baru di mana setiap elemen adalah hasil dari beberapa operasi yang diterapkan pada setiap anggota dari urutan lain atau dapat diubah, atau untuk membuat urutan elemen-elemen yang memenuhi kondisi tertentu.
List comperhenseions dapat berisi ekspresi kompleks dan fungsi bersarang.

### 5.1.4. Nested List Comprehensions
Ekspresi awal dalam List comperhensions dapat berupa ekspresi sembarang, termasuk list comperhensions lainnya.

---
## 5.2. The del statement
Ada cara untuk menghapus item dari list yang diberikan indeksnya, bukan nilainya: pernyataan del. Ini berbeda dari metode pop () yang mengembalikan nilai. Pernyataan del juga dapat digunakan untuk menghapus irisan dari daftar atau menghapus seluruh daftar (yang kami lakukan sebelumnya dengan menetapkan daftar kosong ke slice).

---
## 5.3. Tuples and Sequences
List dan string memiliki banyak properti umum, seperti operasi pengindeksan dan irisan. Itu adalah contoh tipe data sequences. Karena Python adalah bahasa yang berkembang, tipe data sewuence lainnya dapat ditambahkan. Ada juga tipe data urutan standar lain: tuple. Sebuah tuple terdiri dari sejumlah nilai yang dipisahkan oleh koma.

---
## 5.4. Sets
Python juga menyertakan tipe data untuk set. Set adalah koleksi yang tidak diurut tanpa elemen duplikat. Penggunaan dasar meliputi pengujian keanggotaan dan menghilangkan entri duplikat. Set objek juga mendukung operasi matematika seperti intersection, persimpangan, perbedaan, dan perbedaan simetris.

Kurung kurawal atau fungsi set () dapat digunakan untuk membuat set. Catatan: untuk membuat set kosong Anda harus menggunakan set (), bukan {}; yang terakhir membuat  empty dictionary, struktur data yang kita bahas di bagian selanjutnya.

---
## 5.5. Dictionaries
Tipe data lain yang berguna yang dibangun ke dalam Python adalah *dictionary* . Dictionaries kadang-kadang ditemukan dalam bahasa lain sebagai "memori asosiatif" atau "array asosiatif". Tidak seperti sequences, yang diindeks oleh sejumlah angka, dictionaries diindeks oleh kunci, yang bisa berupa tipe apa pun yang tidak berubah; string dan angka selalu bisa menjadi kunci. Tuples dapat digunakan sebagai kunci jika hanya berisi string, angka, atau tupel; jika sebuah tuple berisi objek yang bisa berubah baik secara langsung atau tidak langsung, itu tidak dapat digunakan sebagai kunci. Anda tidak dapat menggunakan list sebagai kunci, karena daftar dapat dimodifikasi di tempat menggunakan penugasan indeks, penugasan slice, atau metode seperti append () dan extend ().
Yang terbaik adalah memikirkan dictionary sebagai satu set kunci: pasangan nilai, dengan persyaratan bahwa kunci itu unik (dalam satu dictionary). Sepasang kurung kurawal membuat dictionary kosong: {}. Menempatkan list kunci yang dipisah koma: pasangan nilai dalam kurung menambah kunci awal: pasangan nilai ke dictionary; ini juga cara dictionary ditulis pada output.

Operasi utama pada dictionary adalah menyimpan nilai dengan beberapa kunci dan mengekstraksi nilai yang diberikan kunci. Dimungkinkan juga untuk menghapus kunci: pasangan nilai dengan del. Jika Anda menyimpan menggunakan kunci yang sudah digunakan, nilai lama yang terkait dengan kunci itu dilupakan. Merupakan kesalahan untuk mengekstraksi nilai menggunakan kunci yang tidak ada.
Melakukan list (d) pada dictionary mengembalikan list semua kunci yang digunakan dalam dictionary, dalam urutan penyisipan (jika Anda ingin diurutkan, gunakan saja sorted (d) sebagai gantinya). Untuk memeriksa apakah satu kunci ada di dictionary, gunakan *in* keywoard.

---
## 5.6. Looping Techniques
Saat perulangan melalui dictionaries, kunci dan nilai terkait dapat diambil pada saat yang sama menggunakan metode *items ()*.

Saat mengulang melalui sequences, indeks posisi dan nilai terkait dapat diambil pada saat yang sama menggunakan fungsi *enumerate ()*.

Untuk mengulang dua atau lebih sequence secara bersamaan, entri dapat dipasangkan dengan fungsi *zip ()*.

Untuk mengulang urutan secara reverse, pertama tentukan sequence dalam arah maju dan kemudian panggil fungsi *reversed ()*.

Untuk mengulangi urutan dalam urutan diurutkan, gunakan fungsi *sorted()* yang mengembalikan daftar diurutkan baru sambil membiarkan sumber tidak diubah.

---
## 5.7. More on Conditions
Kondisi yang digunakan di while dan if statements dapat berisi operator apa pun, bukan hanya perbandingan.

Operator perbandingan masuk dan tidak memeriksa apakah suatu nilai terjadi (tidak terjadi) secara berurutan. Operator adalah dan tidak membandingkan apakah dua objek benar-benar objek yang sama; ini hanya penting untuk objek yang dapat diubah seperti daftar. Semua operator pembanding memiliki prioritas yang sama, yang lebih rendah daripada semua operator numerik.

Perbandingan bisa dirantai. Sebagai contoh, a < b == c menguji apakah a kurang dari b dan apalagi b sama dengan c.

Perbandingan dapat digabungkan dengan menggunakan operator Boolean and dan or, dan hasil perbandingan (atau ekspresi Boolean lainnya) dapat dinegasikan dengan not. Ini memiliki prioritas lebih rendah daripada operator pembanding; di antara mereka, tidak memiliki prioritas tertinggi dan atau terendah, sehingga A and not B or C setara dengan (A and(not B)) or C. Seperti biasa, tanda kurung dapat digunakan untuk mengekspresikan komposisi yang diinginkan.

Operator Boolean and dan or disebut operator shor-circuit: argumen mereka dievaluasi dari kiri ke kanan, dan evaluasi berhenti segera setelah hasilnya ditentukan. Misalnya, jika A dan C benar tetapi B salah, A dan B dan C tidak mengevaluasi ekspresi C. Ketika digunakan sebagai nilai umum dan bukan sebagai Boolean, return value dari operator short-circuit adalah argumen terakhir yang dievaluasi.

Dimungkinkan untuk menetapkan hasil perbandingan atau ekspresi Boolean lainnya ke variabel.
Perhatikan bahwa dalam Python, tidak seperti C, penugasan di dalam ekspresi harus dilakukan secara eksplisit dengan operator walrus: =. Ini menghindari kelas masalah umum yang dihadapi dalam program C: mengetik = dalam ekspresi ketika == dimaksudkan.

---
## 5.8. Comparing Sequences and Other Types
Objek urutan biasanya dapat dibandingkan dengan objek lain dengan jenis urutan yang sama. Perbandingan menggunakan urutan lexicographical: pertama dua item pertama dibandingkan, dan jika mereka berbeda ini menentukan hasil perbandingan; jika mereka sama, dua item berikutnya dibandingkan, dan seterusnya, sampai urutan mana pun habis. Jika dua item yang akan dibandingkan adalah sendiri urutan dari jenis yang sama, perbandingan leksikografis dilakukan secara rekursif. Jika semua item dari dua urutan membandingkan sama, urutan dianggap sama. Jika satu urutan adalah sub-urutan awal dari yang lain, urutan yang lebih pendek adalah yang lebih kecil(lebih kecil). Pemesanan leksikografis untuk string menggunakan nomor titik kode Unicode untuk memesan masing-masing karakter.

Perhatikan bahwa membandingkan objek dengan tipe yang berbeda dengan < or > sah asalkan objek memiliki metode perbandingan yang sesuai. Misalnya, tipe numerik campuran dibandingkan menurut nilai numeriknya, jadi 0 sama dengan 0,0, dll. Jika tidak, alih-alih memberikan pemesanan acak, interpreter akan meningkatkan TypeError exception.
