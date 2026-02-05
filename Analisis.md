<div align="center">

# 🎓 Modul Ajar: Koding & Kecerdasan Artifisial
### Rekayasa Perangkat Lunak (RPL) - Fase F (Kelas XI)

![Python](https://img.shields.io/badge/Language-Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Topic](https://img.shields.io/badge/Topic-Object_Oriented_Programming-orange?style=for-the-badge)
![Level](https://img.shields.io/badge/Level-Intermediate-blue?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)

<p align="center">
  <b>Prepared By:</b> MGMP RPL<br>
  <i>Membangun fondasi AI melalui konsep Pemrograman Berorientasi Objek.</i>
</p>

[Tujuan Pembelajaran](#-tujuan-pembelajaran) •
[Dasar Teori](#-dasar-teori) •
[Praktikum](#-kegiatan-praktikum) •
[Final Project](#-tugas-proyek-integrasi-challenge)

</div>

---

## 🎯 Tujuan Pembelajaran

Setelah menyelesaikan modul ini, siswa diharapkan mampu:
1.  🧠 Memahami konsep dasar **Pemrograman Berorientasi Objek (PBO/OOP)**.
2.  ⚖️ Membandingkan paradigma **OOP** vs **Procedural**.
3.  💻 Menerapkan aturan dasar penulisan koding pada PBO.

---

## 📚 Dasar Teori

### 1. Apa itu OOP?
**Object-Oriented Programming (OOP)** adalah metode pemrograman yang berpusat pada **Objek**. Jika pemrograman biasa adalah sekumpulan instruksi baris demi baris, OOP adalah sekumpulan objek yang saling berinteraksi.

> **Analogi Pabrik Mobil 🚗**
> * **Class (Blueprint):** Desain teknis/cetakan (Roda, Mesin, Warna).
> * **Object (Instance):** Mobil nyata yang keluar dari pabrik (Jeep, Sedan, Bus).

### 2. Komponen Utama
| Komponen | Deskripsi | Analogi |
| :--- | :--- | :--- |
| **Class** | Template/cetakan untuk membuat objek. | Cetakan Kue 🍪 |
| **Object** | Hasil cetakan dari class. | Kue yang sudah jadi 🍩 |
| **Attribute** | Data/karakteristik (Variabel). | Rasa, Warna, Topping 🍓 |
| **Method** | Perilaku/fungsi (Function). | Dimakan, Dijual, Dipotong 🔪 |

### 3. Empat Pilar Utama OOP (The Big Four)

<details>
<summary><b>🧬 1. Inheritance (Pewarisan)</b> - <i>Klik untuk detail</i></summary>
<br>
Memungkinkan class baru (Child) mengambil atribut dan method dari class lain (Parent). Mencegah pengulangan kode.

* **Analogi:** Anak mewarisi warna mata orang tua, tapi bisa belajar skill baru.
</details>

<details>
<summary><b>💊 2. Encapsulation (Pembungkusan)</b> - <i>Klik untuk detail</i></summary>
<br>
Membatasi akses langsung ke variabel untuk keamanan data (Private variable).

* **Analogi:** Remote TV. Kamu hanya butuh tombol, tidak perlu tahu rumitnya kabel di dalam remote.
* **Kode:** Menggunakan `__variable` (double underscore).
</details>

<details>
<summary><b>🎭 3. Polymorphism (Banyak Bentuk)</b> - <i>Klik untuk detail</i></summary>
<br>
Satu nama method yang sama, tapi perilakunya berbeda tergantung objeknya.

* **Analogi:** Tombol "Play". Di YouTube memutar video, di Spotify memutar musik.
</details>

<details>
<summary><b>👻 4. Abstraction (Abstraksi)</b> - <i>Klik untuk detail</i></summary>
<br>
Menyembunyikan detail rumit dan hanya menampilkan fungsi penting. Menggunakan <code>Abstract Base Class (ABC)</code>.

* **Analogi:** Menyetir mobil. Kamu cukup tahu gas & rem, tidak perlu tahu cara kerja piston mesin.
</details>

---

## 🧪 Kegiatan Praktikum

Kita akan membangun **Sistem Pertarungan Game RPG (Role Playing Game)** sederhana.
*Siapkan Text Editor (VS Code/PyCharm) dan buat file `game_rpg.py`.*

### 🔥 Latihan 1-3: Dasar, Interaksi & Pewarisan
Membuat Hero, membuatnya saling serang, dan membuat Job Class (Mage).

<details>
<summary><b>Lihat Kode Latihan</b></summary>

```python
class Hero:
    def __init__(self, name, hp, attack_power):
        self.name = name
        self.hp = hp
        self.attack_power = attack_power

    def serang(self, lawan):
        print(f"{self.name} menyerang {lawan.name}!")
        lawan.diserang(self.attack_power)

    def diserang(self, damage):
        self.hp -= damage
        print(f"{self.name} terkena damage {damage}. Sisa HP: {self.hp}")

# Inheritance
class Mage(Hero):
    def __init__(self, name, hp, attack_power, mana):
        super().__init__(name, hp, attack_power)
        self.mana = mana

    def skill_fireball(self, lawan):
        if self.mana >= 20:
            print(f"{self.name} melempar Fireball ke {lawan.name}!")
            self.mana -= 20
            lawan.diserang(self.attack_power * 2)
        else:
            print("Mana tidak cukup!")

# Main Program
hero1 = Hero("Layla", 100, 15)
mage1 = Mage("Eudora", 80, 30, 100)

mage1.skill_fireball(hero1)
