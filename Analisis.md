#  Laporan Analisis 1-6

Dokumen ini berisi rangkuman hasil analisis dari setiap tugas praktikum yang telah dilakukan, mencakup konsep Dasar Objek, Inheritance, Encapsulation, Abstraction, hingga Polymorphism.

---

##  Tugas Analisis 1: Dasar Objek & Atribut
**Pertanyaan:** Apa yang terjadi jika kamu mengubah `hero1.hp` menjadi 500 setelah instansiasi?

* **Analisis:** Jika kamu menulis `hero1.hp = 500`, maka nilai atribut `hp` pada objek `hero1` akan langsung berubah menjadi 500. Saat kamu melakukan `print(hero1.hp)`, output yang keluar adalah 500.
* **Kesimpulan:** Secara default, atribut di Python bersifat **public**, artinya bisa diakses dan diubah secara bebas dari luar class tanpa validasi.

---

##  Tugas Analisis 2: Interaksi Antar Objek
**Pertanyaan:** Mengapa parameter `lawan` menerima objek utuh, bukan hanya string nama?

* **Analisis:** Jika hanya menerima string nama, kita tidak bisa memanipulasi data "lawan" tersebut. Dengan menerima **Objek Utuh**, kita bisa mengakses semua atribut dan method milik lawan.
* **Pentingnya:** Hal ini memungkinkan interaksi yang nyata. Saat `hero1.serang(hero2)` dipanggil, program bisa langsung memicu `hero2.diserang(damage)` yang secara otomatis mengurangi hp milik hero2.

---

##  Tugas Analisis 3: Pewarisan (Inheritance & super())
**Percobaan:** Menghapus `super().__init__(name, hp, attack_power)`.

* **Error:** `AttributeError: 'Mage' object has no attribute 'name'.`
* **Analisis:** Saat kita membuat constructor (`__init__`) di class Anak (Mage), constructor milik class Induk (Hero) tertimpa. Tanpa `super()`, variabel dasar tidak pernah dibuat di dalam memori untuk objek Mage tersebut.
* **Peran super():** Sebagai jembatan untuk memanggil fungsi milik Induk agar kita tidak perlu menulis ulang kode inisialisasi yang sama (mencegah duplikasi).

---

##  Tugas Analisis 4: Enkapsulasi (Private & Safety)
**1. Percobaan Hacking (`_Hero__hp`):**
* **Analisis:** Nilai HP akan tetap muncul (tidak Error) karena Python menggunakan sistem *Name Mangling*. Namun, secara standar kita dilarang mengaksesnya karena melanggar prinsip "data hiding".

**2. Uji Validasi:**
* **Analisis:** Tanpa logika `if` pada Setter, data bisa menjadi tidak logis (seperti HP negatif).
* **Pentingnya Setter:** Bertindak sebagai satpam/filter untuk menjaga integritas data agar tetap berada dalam rentang yang diizinkan.

---

##  Tugas Analisis 5: Abstraction (Blueprint & Kontrak)
**1. Melanggar Kontrak (Hapus method serang):**
* **Error:** `TypeError: Can't instantiate abstract class Hero with abstract method serang.`
* **Analisis:** Program menolak membuat objek karena class Hero dianggap "tidak lengkap". Ini memaksa programmer untuk selalu konsisten mengikuti standar `GameUnit`.

**2. Mencetak Cetakan (`unit = GameUnit()`):**
* **Analisis:** `GameUnit` dilarang dibuat objeknya karena ia hanyalah konsep (abstrak). Kita tidak bisa membuat "Unit" tanpa tahu identitas pastinya (Hero atau Monster).

---

##  Tugas Analisis 6: Polymorphism (Banyak Bentuk)
**1. Uji Skalabilitas:**
* **Analisis:** Kita bisa menambah ratusan jenis Hero baru (seperti Healer), dan fungsi "Perang" akan tetap bekerja tanpa perlu mengubah kode loop utama.

**2. Konsistensi Penamaan:**
* **Error:** Terjadi `AttributeError` jika nama method berbeda (misal: `tembak_panah` vs `serang`).
* **Kesimpulan:** Nama method harus seragam agar objek yang berbeda jenis bisa diperlakukan dengan cara yang sama (Interface konsisten).

---
<div align="center">
  <i>Laporan Analisis Selesai</i>
</div>
